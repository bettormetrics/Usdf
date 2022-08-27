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
Represents the fixture level in an acyclic sportsbook hierarchy.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String | The unique identifier of the fixture. |
| Fixture | - | [UsmfFixture](#usmffixture) | The fixture entity associated with this node. |
| Markets | - | [UsmfMarketNode](#usmfmarketnode) | Market nodes within this fixture. |
## UsmfMarketNode
Represents the market level in an acyclic sportsbook hierarchy.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String | The unique identifier of the market. |
| Market | - | [UsmfMarket](#usmfmarket) | The market entity associated with this node. |
| Selections | - | [UsmfSelectionNode](#usmfselectionnode) | Selection nodes within this market. |
## UsmfSelectionNode
Represents the selection level in an acyclic sportsbook hierarchy.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String | The unique identifier of the selection. |
| Selection | - | [UsmfSelection](#usmfselection) | The selection entity associated with this node. |
| SourceSelections | - | [UsmfSourceSelection](#usmfsourceselection) | Source selection nodes within this selection. |
## UsmfBookStateNode
| Name | Minified | Type | Description |
| - | - | - | - |
| Children | - | HashMap\<String,UsmfFixtureStateNode> |  |
## UsmfFixtureStateNode
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String |  |
| SportId | - | String |  |
| SportName | - | String |  |
| RegionId | - | String |  |
| RegionName | - | String |  |
| CompetitionId | - | String |  |
| CompetitionName | - | String |  |
| UtcStart | - | Nullable\<Date> |  |
| Participants | - | HashMap\<String,UsmfFixtureParticipantStateNode> |  |
| FixtureStatus | - | Nullable\<UsmfFixtureStatus> |  |
| IsVirtual | - | Boolean |  |
| Children | - | HashMap\<String,UsmfMarketStateNode> |  |
## UsmfMarketStateNode
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String |  |
| FixtureId | - | String |  |
| TypeId | - | String |  |
| Name | - | String |  |
| Children | - | HashMap\<String,UsmfSelectionStateNode> |  |
## UsmfSelectionStateNode
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String |  |
| FixtureId | - | String |  |
| MarketId | - | String |  |
| Line | - | String |  |
| Name | - | String |  |
| Children | - | HashMap\<ValueTuple`2,UsmfSourceSelectionStateNode> |  |
## UsmfSourceSelectionStateNode
| Name | Minified | Type | Description |
| - | - | - | - |
| SelectionId | - | String |  |
| SourceId | - | String |  |
| FixtureId | - | String |  |
| MarketId | - | String |  |
| IsSuspended | - | Boolean |  |
| Price | - | Double |  |
| PriceVolume | - | Double |  |
| LayPriceVolume | - | Double |  |
| BackLiquidity | - | Double |  |
| UtcUpdatedFromSource | - | Date |  |
## UsmfFixtureParticipantStateNode
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String |  |
| Name | - | String |  |
