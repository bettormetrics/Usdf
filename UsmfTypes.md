# Usmf Types
- [UsmfDictionary](#usmfdictionary)
- [UsmfEvent](#usmfevent)
- [UsmfHeader](#usmfheader)
- [UsmfFixture](#usmffixture)
- [UsmfFixtureParticipant](#usmffixtureparticipant)
- [UsmfMarket](#usmfmarket)
- [UsmfSelection](#usmfselection)
- [UsmfSourceSelection](#usmfsourceselection)
- [UsmfFixtureStatus](#usmffixturestatus)
- [UsmfEventBuilder](#usmfeventbuilder)
- [UsmfHashSet](#usmfhashset)
- [UsmfMaterializer](#usmfmaterializer)
- [UsmfFixtureNode](#usmffixturenode)
- [UsmfMarketNode](#usmfmarketnode)
- [UsmfSelectionNode](#usmfselectionnode)
- [UsmfBookStateNode](#usmfbookstatenode)
- [UsmfFixtureStateNode](#usmffixturestatenode)
- [UsmfMarketStateNode](#usmfmarketstatenode)
- [UsmfSelectionStateNode](#usmfselectionstatenode)
- [UsmfSourceSelectionStateNode](#usmfsourceselectionstatenode)
- [UsmfFixtureParticipantStateNode](#usmffixtureparticipantstatenode)
## UsmfDictionary
| Name | Minified | Type | Description |
| - | - | - | - |
| Order | - | List\<TKey> |  |
| Comparer | - | IEqualityComparer\<TKey> |  |
| Count | - | Integer |  |
| Keys | - | KeyCollection\<TKey,TValue> |  |
| Values | - | ValueCollection\<TKey,TValue> |  |
| Item | - | TValue |  |
## UsmfEvent
| Name | Minified | Type | Description |
| - | - | - | - |
| Header | H | [UsmfHeader](#usmfheader) |  |
| Fixtures | F | [UsmfFixtureNode](#usmffixturenode) |  |
## UsmfHeader
| Name | Minified | Type | Description |
| - | - | - | - |
| UtcTimestamp | UT | Date |  |
## UsmfFixture
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String |  |
| SportId | SI | String |  |
| SportName | SN | String |  |
| RegionId | RI | String |  |
| RegionName | RN | String |  |
| CompetitionId | CI | String |  |
| CompetitionName | CN | String |  |
| UtcStart | US | Nullable\<Date> |  |
| Participants | P | [UsmfFixtureParticipant](#usmffixtureparticipant) |  |
| FixtureStatus | FS | Nullable\<UsmfFixtureStatus> |  |
| IsVirtual | IV | Boolean |  |
## UsmfFixtureParticipant
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String |  |
| Name | N | String |  |
## UsmfMarket
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String |  |
| FixtureId | FI | String |  |
| TypeId | TI | String |  |
| Name | N | String |  |
## UsmfSelection
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | I | String |  |
| FixtureId | FI | String |  |
| MarketId | MI | String |  |
| Line | L | String |  |
| Name | N | String |  |
## UsmfSourceSelection
| Name | Minified | Type | Description |
| - | - | - | - |
| SelectionId | SI | String |  |
| SourceId | SO | String |  |
| FixtureId | FI | String |  |
| MarketId | MI | String |  |
| Price | P | Double |  |
| PriceVolume | PV | Double |  |
| LayPriceVolume | LPV | Double |  |
| BackLiquidity | BL | Double |  |
| UtcUpdatedFromSource | UU | Date |  |
## UsmfFixtureStatus
| Name | Value | Description |
| - | - | - |
| Pregame | 0 |  |
| Inplay | 1 |  |
| Completed | 2 |  |
| SweeperCompleted | 3 |  |
## UsmfEventBuilder
## UsmfHashSet
| Name | Minified | Type | Description |
| - | - | - | - |
| Order | - | List\<T> |  |
| Count | - | Integer |  |
| Comparer | - | IEqualityComparer\<T> |  |
## UsmfMaterializer
## UsmfFixtureNode
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String |  |
| Fixture | - | [UsmfFixture](#usmffixture) |  |
| Markets | - | [UsmfMarketNode](#usmfmarketnode) |  |
## UsmfMarketNode
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String |  |
| Market | - | [UsmfMarket](#usmfmarket) |  |
| Selections | - | [UsmfSelectionNode](#usmfselectionnode) |  |
## UsmfSelectionNode
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String |  |
| Selection | - | [UsmfSelection](#usmfselection) |  |
| SourceSelections | - | [UsmfSourceSelection](#usmfsourceselection) |  |
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
