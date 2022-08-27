# Usmf Types
- [UsmfEvent](#usmfevent)
- [UsmfHeader](#usmfheader)
- [UsmfFixture](#usmffixture)
- [UsmfFixtureParticipant](#usmffixtureparticipant)
- [UsmfMarket](#usmfmarket)
- [UsmfSelection](#usmfselection)
- [UsmfSourceSelection](#usmfsourceselection)
- [UsmfFixtureStatus](#usmffixturestatus)
- [UsmfFixtureNode](#usmffixturenode)
- [UsmfMarketNode](#usmfmarketnode)
- [UsmfSelectionNode](#usmfselectionnode)
- [UsmfBookStateNode](#usmfbookstatenode)
- [UsmfFixtureStateNode](#usmffixturestatenode)
- [UsmfMarketStateNode](#usmfmarketstatenode)
- [UsmfSelectionStateNode](#usmfselectionstatenode)
- [UsmfSourceSelectionStateNode](#usmfsourceselectionstatenode)
- [UsmfFixtureParticipantStateNode](#usmffixtureparticipantstatenode)
## UsmfEvent
Encapsulates a single unified sports materialized format event (a fact).
| Name | Minified | Type | Description |
| - | - | - | - |
| Header | H | [UsmfHeader](#usmfheader) | Contains high level ordering, synchronisation, and origin data for the event. |
| Fixtures | F | [UsmfFixtureNode](#usmffixturenode) | Contains data pertaining to the materialized state of fixtures. |
## UsmfHeader
Contains high level ordering, synchronisation, and origin data for the event.
| Name | Minified | Type | Description |
| - | - | - | - |
| UtcTimestamp | UT | Date | The time at which the data required to generate this event was constituted. |
## UsmfFixture
Contains data pertaining to the state of a fixture.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the fixture. |
| SportId | SI | String | The unique identifier of the sport of this fixture. |
| SportName | SN | String | The name of the sport of this fixture. |
| RegionId | RI | String | The unique identifier of the region of this fixture. |
| RegionName | RN | String | The name of the region of this fixture. |
| CompetitionId | CI | String | The unique identifier of the competition of this fixture. |
| CompetitionName | CN | String | The name of the competition of this fixture. |
| UtcStart | US | Nullable\<Date> | The time at which this fixture is due to start. |
| Participants | P | [UsmfFixtureParticipant](#usmffixtureparticipant) | Contains data pertaining to the state of participants in this fixture. |
| FixtureStatus | FS | Nullable\<UsmfFixtureStatus> | The lifecycle status of this fixture. |
| IsVirtual | IV | Boolean | Whether this is a simulated virtual fixture. |
## UsmfFixtureParticipant
Contains data pertaining to the state of a participant.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the participant. |
| Name | N | String | The name of the participant. |
## UsmfMarket
Contains data pertaining to the state of a market.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the market. |
| FixtureId | FI | String | The unique identifier of the fixture. |
| TypeId | TI | String | The type of the market. |
| Name | N | String | The name of the market. |
## UsmfSelection
Contains data pertaining to the state of a selection.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the selection. |
| FixtureId | FI | String | The unique identifier of the fixture. |
| MarketId | MI | String | The unique identifier of the market. |
| Line | L | String | The line the selection pertains to. |
| Name | N | String | The name of the selection. |
## UsmfSourceSelection
Contains data pertaining to the state of a selection from a single source.
| Name | Minified | Type | Description |
| - | - | - | - |
| SelectionId | SI | String | The unique identifier of the selection. |
| SourceId | SO | String | The unique identifier of the source. |
| FixtureId | FI | String | The unique identifier of the fixture. |
| MarketId | MI | String | The unique identifier of the market. |
| Price | P | Double | The price of the source selection. |
| PriceVolume | PV | Double | The price volume of the source selection. |
| LayPriceVolume | LPV | Double | The lay price volume of the source selection. |
| BackLiquidity | BL | Double | The back liquidity of the source selection. |
| UtcUpdatedFromSource | UU | Date | The time when the source selection was updated from the source. |
## UsmfFixtureStatus
Represents the lifecycle status of a fixture.
| Name | Value | Description |
| - | - | - |
| Pregame | 0 | Fixture has not started. |
| Inplay | 1 | Fixture is in progress. |
| Completed | 2 | Fixture is completed. |
| SweeperCompleted | 3 | Fixture has been swept (cleaned up). |
## UsmfFixtureNode
Represents the fixture level of an acyclic sportsbook hierarchy in a single materialized Usmf event.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String | The unique identifier of the fixture. |
| Fixture | - | [UsmfFixture](#usmffixture) | The fixture entity associated with this node. |
| Markets | - | [UsmfMarketNode](#usmfmarketnode) | Market nodes within this fixture. |
## UsmfMarketNode
Represents the market level of an acyclic sportsbook hierarchy in a single materialized Usmf event.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String | The unique identifier of the market. |
| Market | - | [UsmfMarket](#usmfmarket) | The market entity associated with this node. |
| Selections | - | [UsmfSelectionNode](#usmfselectionnode) | Selection nodes within this market. |
## UsmfSelectionNode
Represents the selection level of an acyclic sportsbook hierarchy in a single materialized Usmf event.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String | The unique identifier of the selection. |
| Selection | - | [UsmfSelection](#usmfselection) | The selection entity associated with this node. |
| SourceSelections | - | [UsmfSourceSelection](#usmfsourceselection) | Source selection nodes within this selection. |
## UsmfBookStateNode
Represents the root level of a stateful, patchable acyclic sportsbook hierarchy which can emit events on mutation.
| Name | Minified | Type | Description |
| - | - | - | - |
| Children | - | HashMap\<String,UsmfFixtureStateNode> |  |
## UsmfFixtureStateNode
Represents the fixture level of a stateful, patchable acyclic sportsbook hierarchy which can emit events on mutation.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String | The unique identifier of the fixture. |
| SportId | - | String | The unique identifier of the sport of this fixture. |
| SportName | - | String | The name of the sport of this fixture. |
| RegionId | - | String | The unique identifier of the region of this fixture. |
| RegionName | - | String | The name of the region of this fixture. |
| CompetitionId | - | String | The unique identifier of the competition of this fixture. |
| CompetitionName | - | String | The name of the competition of this fixture. |
| UtcStart | - | Nullable\<Date> | The time at which this fixture is due to start. |
| Participants | - | HashMap\<String,UsmfFixtureParticipantStateNode> | Participant nodes subordinate to the fixture level of a stateful, patchable acyclic sportsbook hierarchy which can emit events on mutation. |
| FixtureStatus | - | Nullable\<UsmfFixtureStatus> | The lifecycle status of this fixture. |
| IsVirtual | - | Boolean | Whether this is a simulated virtual fixture. |
| Children | - | HashMap\<String,UsmfMarketStateNode> |  |
## UsmfMarketStateNode
Represents the market level of a stateful, patchable acyclic sportsbook hierarchy which can emit events on mutation.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String | The unique identifier of the market. |
| FixtureId | - | String | The unique identifier of the fixture. |
| TypeId | - | String | The type of the market. |
| Name | - | String | The name of the market. |
| Children | - | HashMap\<String,UsmfSelectionStateNode> |  |
## UsmfSelectionStateNode
Represents the selection level of a stateful, patchable acyclic sportsbook hierarchy which can emit events on mutation.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String | The unique identifier of the selection. |
| FixtureId | - | String | The unique identifier of the fixture. |
| MarketId | - | String | The unique identifier of the market. |
| Line | - | String | The line the selection pertains to. |
| Name | - | String | The name of the selection. |
| Children | - | HashMap\<ValueTuple`2,UsmfSourceSelectionStateNode> |  |
## UsmfSourceSelectionStateNode
Represents the selection level from a single source of a stateful, patchable acyclic sportsbook hierarchy which can emit events on mutation.
| Name | Minified | Type | Description |
| - | - | - | - |
| SelectionId | - | String | The unique identifier of the selection. |
| SourceId | - | String | The unique identifier of the source. |
| FixtureId | - | String | The unique identifier of the fixture. |
| MarketId | - | String | The unique identifier of the market. |
| IsSuspended | - | Boolean | Whether this source selection is suspended. |
| Price | - | Double | The price of the source selection. |
| PriceVolume | - | Double | The price volume of the source selection. |
| LayPriceVolume | - | Double | The lay price volume of the source selection. |
| BackLiquidity | - | Double | The back liquidity of the source selection. |
| UtcUpdatedFromSource | - | Date | The time when the source selection was updated from the source. |
## UsmfFixtureParticipantStateNode
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String |  |
| Name | - | String |  |
