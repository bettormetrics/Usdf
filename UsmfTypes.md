# Usmf Types
- [UsmfEvent](#usmfevent)
- [UsmfHeader](#usmfheader)
- [UsmfFixture](#usmffixture)
- [UsmfFixtureProviderScoreboard](#usmffixtureproviderscoreboard)
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
| CheckpointIdentifier | CI | Nullable\<Guid> | If populated, indicates that a significant checkpoint has been reached in the data e.g. the fixture has finished and all data is available. |
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
| IsVirtual | IV | Boolean | Whether this is a simulated virtual fixture. |
## UsmfFixtureProviderScoreboard
Contains data pertaining to the state of a scoreboard.
| Name | Minified | Type | Description |
| - | - | - | - |
| ProviderId | PI | Integer | The unique identifier of the provider of the data required to generate this event. |
| FixtureStatus | FS | Nullable\<UsmfFixtureStatus> | The lifecycle status of this fixture. |
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
| ProviderId | PI | Integer | The unique identifier of the provider for this market. |
| FixtureId | FI | String | The unique identifier of the fixture. |
| TypeId | TI | String | The type of the market. |
| SubTypeId | STI | String | The sub type of the market. |
| Name | N | String | The name of the market. |
| IsVirtual | IV | Nullable\<Boolean> | Defines whether this market has been virtually projected. |
| BetDelaySeconds | BD | Nullable\<Integer> | The bet delay for this market. |
## UsmfSelection
Contains data pertaining to the state of a selection.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the selection. |
| ProviderId | PI | Integer | The unique identifier of the provider for this selection. |
| FixtureId | FI | String | The unique identifier of the fixture. |
| MarketId | MI | String | The unique identifier of the market. |
| Type | T | String | The type of the selection. |
| Line | L | String | The line the selection pertains to. |
| Name | N | String | The name of the selection. |
| IsVirtual | IV | Nullable\<Boolean> | Defines whether this selection has been virtually projected. |
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
| Finalized | 3 | Fixture has been finalized.
            A fixture can be finalized in the event that a completion is not received from the provider. |
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
| ProviderScoreboards | PS | [UsmfFixtureProviderScoreboard](#usmffixtureproviderscoreboard) | The provider scoreboard entities associated with this node. |
| Markets | MN | [UsmfMarketNode](#usmfmarketnode) | Market nodes within this fixture. |
| Bets | B | [UsmfBet](#usmfbet) | Contains data pertaining to the materialized state of bets. |
## UsmfMarketNode
Represents the market level of an acyclic sportsbook hierarchy in a single materialized Usmf event.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the market. |
| ProviderMarkets | PM | [UsmfMarket](#usmfmarket) | The provider market entities associated with this node. |
| Selections | SN | [UsmfSelectionNode](#usmfselectionnode) | Selection nodes within this market. |
## UsmfSelectionNode
Represents the selection level of an acyclic sportsbook hierarchy in a single materialized Usmf event.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the selection. |
| ProviderSelections | PS | [UsmfSelection](#usmfselection) | The provider selection entities associated with this node. |
| SourceSelections | SSN | [UsmfSourceSelection](#usmfsourceselection) | Source selection nodes within this selection. |
