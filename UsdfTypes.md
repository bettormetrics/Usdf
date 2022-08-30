# Usdf Types
- [UsdfEvent](#usdfevent)
- [UsdfHeader](#usdfheader)
- [UsdfFixture](#usdffixture)
- [UsdfParticipant](#usdfparticipant)
- [UsdfMarket](#usdfmarket)
- [UsdfSelection](#usdfselection)
- [UsdfSourceSelection](#usdfsourceselection)
- [UsdfBet](#usdfbet)
- [UsdfOptional](#usdfoptional)
- [UsdfFixtureStatus](#usdffixturestatus)
## UsdfEvent
Encapsulates a single unified sports data format event (a fact).
| Name | Minified | Type | Description |
| - | - | - | - |
| Header | H | [UsdfHeader](#usdfheader) | Contains high level ordering, synchronisation, and origin data for the event. |
| Fixture | F | [UsdfFixture](#usdffixture) | Contains data pertaining to the state of fixtures. |
| Market | M | [UsdfMarket](#usdfmarket) | Contains data pertaining to the state of markets. |
| Selection | SL | [UsdfSelection](#usdfselection) | Contains data pertaining to the state of selections. |
| SourceSelection | SS | [UsdfSourceSelection](#usdfsourceselection) | Contains data pertaining to the state of selections from a single source. |
| Bets | B | [UsdfBet](#usdfbet) | Contains data pertaining to the state of bets. |
## UsdfHeader
Contains high level ordering, synchronisation, and origin data for the event.
| Name | Minified | Type | Description |
| - | - | - | - |
| PartitionKey | PK | String | The partition key for this event, often, but not always, the unique id of the fixture. |
| ProviderId | PI | Integer | The unique identifier of the provider of the data required to generate this event. |
| VentId | VI | String | The origin of the data required to generate this event within the provider system. |
| UtcTimestamp | UT | Date | The time at which the data required to generate this event was constituted. |
## UsdfFixture
Contains data pertaining to the state of a fixture.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the fixture. |
| SportId | SI | [UsdfOptional](#usdfoptional)\<String> | The unique identifier of the sport of this fixture (optional). |
| SportName | SN | [UsdfOptional](#usdfoptional)\<String> | The name of the sport of this fixture (optional). |
| RegionId | RI | [UsdfOptional](#usdfoptional)\<String> | The unique identifier of the region of this fixture (optional). |
| RegionName | RN | [UsdfOptional](#usdfoptional)\<String> | The name of the region of this fixture (optional). |
| CompetitionId | CI | [UsdfOptional](#usdfoptional)\<String> | The unique identifier of the competition of this fixture (optional). |
| CompetitionName | CN | [UsdfOptional](#usdfoptional)\<String> | The name of the competition of this fixture (optional). |
| Participant | P | [UsdfParticipant](#usdfparticipant) | Contains data pertaining to the state of participants in this fixture. |
| UtcStart | US | [UsdfOptional](#usdfoptional)\<Date> | The time at which this fixture is due to start (optional). |
| IsSuspendedUntilPriced | ISUP | [UsdfOptional](#usdfoptional)\<Boolean> | Whether all markets in this fixture are suspended until subsequent prices are received (optional). |
| FixtureStatus | FS | [UsdfOptional](#usdfoptional)\<UsdfFixtureStatus> | The lifecycle status of this fixture (optional). |
| IsVirtual | IV | [UsdfOptional](#usdfoptional)\<Boolean> | Whether this is a simulated virtual fixture (optional). |
| IsDeleted | D | [UsdfOptional](#usdfoptional)\<Boolean> | Whether the entity has been deleted (optional). |
## UsdfParticipant
Contains data pertaining to the state of a participant.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the participant. |
| Name | N | [UsdfOptional](#usdfoptional)\<String> | The name of the participant (optional). |
| IsDeleted | D | [UsdfOptional](#usdfoptional)\<Boolean> | Whether the entity has been deleted (optional). |
## UsdfMarket
Contains data pertaining to the state of a market.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the market. |
| FixtureId | FI | String | The unique identifier of the fixture. |
| TypeId | TI | [UsdfOptional](#usdfoptional)\<String> | The type of the market (optional). |
| Name | N | [UsdfOptional](#usdfoptional)\<String> | The name of the market (optional). |
| IsDeleted | D | [UsdfOptional](#usdfoptional)\<Boolean> | Whether the entity has been deleted (optional). |
## UsdfSelection
Contains data pertaining to the state of a selection.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the selection. |
| FixtureId | FI | [UsdfOptional](#usdfoptional)\<String> | The unique identifier of the fixture (optional). |
| MarketId | MI | String | The unique identifier of the market. |
| Line | L | [UsdfOptional](#usdfoptional)\<String> | The line the selection pertains to (optional). |
| Name | N | [UsdfOptional](#usdfoptional)\<String> | The name of the selection (optional). |
| IsDeleted | D | [UsdfOptional](#usdfoptional)\<Boolean> | Whether the entity has been deleted (optional). |
## UsdfSourceSelection
Contains data pertaining to the state of a selection from a single source.
| Name | Minified | Type | Description |
| - | - | - | - |
| SelectionId | SI | String | The unique identifier of the selection. |
| SourceId | SO | String | The unique identifier of the source. |
| FixtureId | FI | [UsdfOptional](#usdfoptional)\<String> | The unique identifier of the fixture (optional). |
| MarketId | MI | [UsdfOptional](#usdfoptional)\<String> | The unique identifier of the market (optional). |
| SourceName | SN | [UsdfOptional](#usdfoptional)\<String> | The name of the source (optional). |
| IsSuspended | IS | [UsdfOptional](#usdfoptional)\<Boolean> | Whether the source selection is suspended (optional). |
| Price | P | [UsdfOptional](#usdfoptional)\<Double> | The price of the source selection (optional). |
| PriceVolume | PV | [UsdfOptional](#usdfoptional)\<Double> | The price volume of the source selection (optional). |
| LayPriceVolume | LPV | [UsdfOptional](#usdfoptional)\<Double> | The lay price volume of the source selection (optional). |
| BackLiquidity | BL | [UsdfOptional](#usdfoptional)\<Double> | The back liquidity of the source selection (optional). |
| UtcUpdatedFromSource | UU | [UsdfOptional](#usdfoptional)\<Date> | The time when the source selection was updated from the source (optional). |
| IsDeleted | D | [UsdfOptional](#usdfoptional)\<Boolean> | Whether the entity has been deleted (optional). |
## UsdfBet
Contains data pertaining to the state of a bet.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String | The unique identifier of the bet. |
| CustomerId | CI | String | The unique identifier of the customer. |
| UtcPlaced | UP | Date | The time when the bet was placed. |
| UtcAccepted | UA | Date | The time when the bet was accepted. |
| FixtureId | FI | [UsdfOptional](#usdfoptional)\<String> | The unique identifier of the fixture (optional). |
| MarketId | MI | [UsdfOptional](#usdfoptional)\<String> | The unique identifier of the market (optional). |
| SelectionId | SI | String | The unique identifier of the selection. |
| Price | P | Double | The price at which the bet was accepted. |
| Stake | S | Double | The stake at which the bet was accepted. |
| Return | R | [UsdfOptional](#usdfoptional)\<Double> | The return from the bet (optional). |
| Tags | T | HashMap\<String,String> | Tags providing weakly typed meta context around the bet. |
| IsDeleted | D | [UsdfOptional](#usdfoptional)\<Boolean> | Whether the entity has been deleted (optional). |
## UsdfOptional
Provides the ability to distinguish between a property being unavailable or explicitly null.
| Name | Minified | Type | Description |
| - | - | - | - |
| ExplicitNull | EN | Nullable\<Boolean> | Whether this property has been explicitly defined as null. |
| Value | V | T | The provided value of this property (must be set if the UsdfOptional is not null. |
## UsdfFixtureStatus
Represents the lifecycle status of a fixture.
| Name | Value | Description |
| - | - | - |
| Pregame | 0 | Fixture has not started. |
| Inplay | 1 | Fixture is in progress. |
| Completed | 2 | Fixture is completed. |
| SweeperCompleted | 3 | Fixture has been swept (cleaned up). |
