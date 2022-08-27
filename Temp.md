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
| Header | H | [UsdfHeader](#usdfheader) |  |
| Fixture | F | [UsdfFixture](#usdffixture) |  |
| Market | M | [UsdfMarket](#usdfmarket) |  |
| Selection | SL | [UsdfSelection](#usdfselection) |  |
| SourceSelection | SS | [UsdfSourceSelection](#usdfsourceselection) |  |
| Bets | B | [UsdfBet](#usdfbet) |  |
## UsdfHeader
Contains high level ordering, synchronisation, and origin data for the event.
| Name | Minified | Type | Description |
| - | - | - | - |
| PartitionKey | PK | String |  |
| ProviderId | PI | Integer |  |
| VentId | VI | String |  |
| UtcTimestamp | UT | Date |  |
## UsdfFixture
Contains data pertaining to the state of a fixture.
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String |  |
| SportId | SI | [UsdfOptional](#usdfoptional)\<String> |  |
| SportName | SN | [UsdfOptional](#usdfoptional)\<String> |  |
| RegionId | RI | [UsdfOptional](#usdfoptional)\<String> |  |
| RegionName | RN | [UsdfOptional](#usdfoptional)\<String> |  |
| CompetitionId | CI | [UsdfOptional](#usdfoptional)\<String> |  |
| CompetitionName | CN | [UsdfOptional](#usdfoptional)\<String> |  |
| Participant | P | [UsdfParticipant](#usdfparticipant) |  |
| UtcStart | US | [UsdfOptional](#usdfoptional)\<Date> |  |
| IsSuspendedUntilPriced | ISUP | [UsdfOptional](#usdfoptional)\<Boolean> |  |
| FixtureStatus | FS | [UsdfOptional](#usdfoptional)\<UsdfFixtureStatus> |  |
| IsVirtual | IV | [UsdfOptional](#usdfoptional)\<Boolean> |  |
| IsDeleted | D | [UsdfOptional](#usdfoptional)\<Boolean> |  |
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
| UtcPlaced | UP | Date |  |
| UceAccepted | UA | Date |  |
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
