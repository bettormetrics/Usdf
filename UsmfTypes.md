# Usmf Types
- [UsmfEvent](#usmfevent)
- [UsmfHeader](#usmfheader)
- [UsmfFixture](#usmffixture)
- [UsmfBet](#usmfbet)
- [UsmfFixtureParticipant](#usmffixtureparticipant)
- [UsmfMarket](#usmfmarket)
- [UsmfSelection](#usmfselection)
- [UsmfSourceSelection](#usmfsourceselection)
- [UsmfFixtureStatus](#usmffixturestatus)
- [UsmfSelectionStatus](#usmfselectionstatus)
- [UsmfFixtureNode](#usmffixturenode)
- [UsmfMarketNode](#usmfmarketnode)
- [UsmfSelectionNode](#usmfselectionnode)
## UsmfEvent
Encapsulates a single unified sports materialized format event (a fact).
| Name | Minified | Type | Description |
| - | - | - | - |
| Header | H | [UsmfHeader](#usmfheader) | Contains high level ordering, synchronisation, and origin data for the event. |
| Fixtures | FN | [UsmfFixtureNode](#usmffixturenode) | Contains data pertaining to the materialized state of fixtures. |
## UsmfHeader
Contains high level ordering, synchronisation, and origin data for the event.
| Name | Minified | Type | Description |
| - | - | - | - |
| UtcTimestamp | UT | Date | The time at which the data required to generate this event was constituted. |
| PrimaryProviderId | PPI | Integer | The unique identifier of the primary provider of the data required to generate this event. |
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
## UsmfBet
Contains data pertaining to a placed bet.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the bet. |
| CustomerId | CI | String | The unique identifier of the customer. |
| UtcPlaced | UP | Date | The time when the bet was placed. |
| UtcAccepted | UA | Date | The time when the bet was accepted. |
| FixtureId | FI | String | The unique identifier of the fixture. |
| MarketId | MI | String | The unique identifier of the market. |
| SelectionId | SI | String | The unique identifier of the selection. |
| Price | P | Double | The price at which the bet was accepted. |
| Stake | S | Double | The stake at which the bet was accepted. |
| Return | R | Double | The return from the bet. |
| Tags | T | HashMap\<String,String> | Tags providing weakly typed meta context around the bet. |
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
| BetDelaySeconds | BD | Nullable\<Integer> | The bet delay for this market. |
## UsmfSelection
Contains data pertaining to the state of a selection.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the selection. |
| FixtureId | FI | String | The unique identifier of the fixture. |
| MarketId | MI | String | The unique identifier of the market. |
| Line | L | String | The line the selection pertains to. |
| Name | N | String | The name of the selection. |
| Status | S | Nullable\<UsmfSelectionStatus> | The status of the selection. |
## UsmfSourceSelection
Contains data pertaining to the state of a selection from a single source.
| Name | Minified | Type | Description |
| - | - | - | - |
| SelectionId | SI | String | The unique identifier of the selection. |
| SourceId | SO | String | The unique identifier of the source. |
| SourceName | SN | String | The name of the source. |
| FixtureId | FI | String | The unique identifier of the fixture. |
| MarketId | MI | String | The unique identifier of the market. |
| ProviderId | PI | Integer | The unique identifier of the provider. |
| ProviderFixtureId | PFI | String | The unique identifier of the fixture from the original provider. |
| ProviderMarketId | PMI | String | The unique identifier of the market from the original provider. |
| ProviderSelectionId | PSI | String | The unique identifier of the selection from the original provider. |
| Price | P | Double | The price of the source selection. |
| PriceVolume | PV | Double | The price volume of the source selection. |
| Liquidity | L | Double | The back liquidity of the source selection. |
| UtcUpdatedFromSource | UU | Date | The time when the source selection was updated from the source. |
## UsmfFixtureStatus
Represents the lifecycle status of a fixture.
| Name | Value | Description |
| - | - | - |
| Pregame | 0 | Fixture has not started. |
| Inplay | 1 | Fixture is in progress. |
| Completed | 2 | Fixture is completed. |
| SweeperCompleted | 3 | Fixture has been swept (cleaned up). |
## UsmfSelectionStatus
Represents the status of a selection.
| Name | Value | Description |
| - | - | - |
| Active | 0 | The selection is active. |
| Removed | 1 | The selection has been removed. |
## UsmfFixtureNode
Represents the fixture level of an acyclic sportsbook hierarchy in a single materialized Usmf event.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the fixture. |
| Fixture | F | [UsmfFixture](#usmffixture) | The fixture entity associated with this node. |
| Markets | MN | [UsmfMarketNode](#usmfmarketnode) | Market nodes within this fixture. |
| Bets | B | [UsmfBet](#usmfbet) | Contains data pertaining to the materialized state of bets. |
## UsmfMarketNode
Represents the market level of an acyclic sportsbook hierarchy in a single materialized Usmf event.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the market. |
| Market | M | [UsmfMarket](#usmfmarket) | The market entity associated with this node. |
| Selections | SN | [UsmfSelectionNode](#usmfselectionnode) | Selection nodes within this market. |
## UsmfSelectionNode
Represents the selection level of an acyclic sportsbook hierarchy in a single materialized Usmf event.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the selection. |
| Selection | S | [UsmfSelection](#usmfselection) | The selection entity associated with this node. |
| SourceSelections | SSN | [UsmfSourceSelection](#usmfsourceselection) | Source selection nodes within this selection. |
