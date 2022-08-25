# Commands
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
| IsDeleted | D | [UsdfOptional](#usdfoptional)\<Boolean> | Whether this fixture has been deleted (optional). |
| IsSuspendedUntilPriced | ISUP | [UsdfOptional](#usdfoptional)\<Boolean> | Whether all markets in this fixture are suspended until subsequent prices are received (optional). |
| FixtureStatus | FS | [UsdfOptional](#usdfoptional)\<UsdfFixtureStatus> | The lifecycle status of this fixture (optional). |
| IsVirtual | IV | [UsdfOptional](#usdfoptional)\<Boolean> | Whether this is a simulated virtual fixture (optional). |
## UsdfParticipant
Contains data pertaining to the state of a participant.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String |  |
| Name | N | [UsdfOptional](#usdfoptional)\<String> |  |
| IsDeleted | D | [UsdfOptional](#usdfoptional)\<Boolean> |  |
## UsdfMarket
Contains data pertaining to the state of a market.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String |  |
| FixtureId | FI | String |  |
| TypeId | TI | [UsdfOptional](#usdfoptional)\<String> |  |
| Name | N | [UsdfOptional](#usdfoptional)\<String> |  |
| IsDeleted | D | [UsdfOptional](#usdfoptional)\<Boolean> |  |
## UsdfSelection
Contains data pertaining to the state of a selection.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String |  |
| FixtureId | FI | [UsdfOptional](#usdfoptional)\<String> |  |
| MarketId | MI | String |  |
| Line | L | [UsdfOptional](#usdfoptional)\<String> |  |
| Name | N | [UsdfOptional](#usdfoptional)\<String> |  |
| IsDeleted | D | [UsdfOptional](#usdfoptional)\<Boolean> |  |
## UsdfSourceSelection
Contains data pertaining to the state of a selection from a single source.
| Name | Minified | Type | Description |
| - | - | - | - |
| SelectionId | SI | String |  |
| SourceId | SO | String |  |
| FixtureId | FI | [UsdfOptional](#usdfoptional)\<String> |  |
| MarketId | MI | [UsdfOptional](#usdfoptional)\<String> |  |
| SourceName | SN | [UsdfOptional](#usdfoptional)\<String> |  |
| IsSuspended | IS | [UsdfOptional](#usdfoptional)\<Boolean> |  |
| Price | P | [UsdfOptional](#usdfoptional)\<Double> |  |
| PriceVolume | PV | [UsdfOptional](#usdfoptional)\<Double> |  |
| LayPriceVolume | LPV | [UsdfOptional](#usdfoptional)\<Double> |  |
| BackLiquidity | BL | [UsdfOptional](#usdfoptional)\<Double> |  |
| UtcUpdatedFromSource | UU | [UsdfOptional](#usdfoptional)\<Date> |  |
| IsDeleted | D | [UsdfOptional](#usdfoptional)\<Boolean> |  |
## UsdfBet
Contains data pertaining to the state of a bet.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String |  |
| CustomerId | CI | String |  |
| UtcPlacement | UP | Date |  |
| FixtureId | FI | [UsdfOptional](#usdfoptional)\<String> |  |
| MarketId | MI | [UsdfOptional](#usdfoptional)\<String> |  |
| SelectionId | SI | String |  |
| Price | P | Double |  |
| Stake | S | Double |  |
| Return | R | [UsdfOptional](#usdfoptional)\<Double> |  |
| Tags | T | HashMap\<String,String> |  |
| IsDeleted | D | [UsdfOptional](#usdfoptional)\<Boolean> |  |
## UsdfOptional
Provides the ability to distinguish between a property being unavailable or explicitly null.
| Name | Minified | Type | Description |
| - | - | - | - |
| ExplicitNull | EN | Nullable\<Boolean> |  |
| Value | V | T |  |
## UsdfFixtureStatus
Represents the lifecycle status of a fixture.
