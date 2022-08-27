# Usmf Types
- [UsmfDictionary`2](#usmfdictionary`2)
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
- [UsmfStateNode](#usmfstatenode)
- [UsmfStateNode](#usmfstatenode)
- [UsmfStateNode`3](#usmfstatenode`3)
- [UsmfBookStateNode](#usmfbookstatenode)
- [UsmfFixtureStateNode](#usmffixturestatenode)
- [UsmfMarketStateNode](#usmfmarketstatenode)
- [UsmfSelectionStateNode](#usmfselectionstatenode)
- [UsmfSourceSelectionStateNode](#usmfsourceselectionstatenode)
- [UsmfFixtureParticipantStateNode](#usmffixtureparticipantstatenode)
## UsmfDictionary`2
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
| Header | - | [UsmfHeader](#usmfheader) |  |
| Fixtures | - | [UsmfFixtureNode](#usmffixturenode) |  |
## UsmfHeader
| Name | Minified | Type | Description |
| - | - | - | - |
| UtcTimestamp | - | Date |  |
## UsmfFixture
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
| Participants | - | [UsmfFixtureParticipant](#usmffixtureparticipant) |  |
| FixtureStatus | - | Nullable\<UsmfFixtureStatus> |  |
| IsVirtual | - | Boolean |  |
## UsmfFixtureParticipant
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String |  |
| Name | - | String |  |
## UsmfMarket
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String |  |
| FixtureId | - | String |  |
| TypeId | - | String |  |
| Name | - | String |  |
## UsmfSelection
| Name | Minified | Type | Description |
| - | - | - | - |
| Id | - | String |  |
| FixtureId | - | String |  |
| MarketId | - | String |  |
| Line | - | String |  |
| Name | - | String |  |
## UsmfSourceSelection
| Name | Minified | Type | Description |
| - | - | - | - |
| SelectionId | - | String |  |
| SourceId | - | String |  |
| FixtureId | - | String |  |
| MarketId | - | String |  |
| Price | - | Double |  |
| PriceVolume | - | Double |  |
| LayPriceVolume | - | Double |  |
| BackLiquidity | - | Double |  |
| UtcUpdatedFromSource | - | Date |  |
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
## UsmfStateNode
## UsmfStateNode
## UsmfStateNode`3
| Name | Minified | Type | Description |
| - | - | - | - |
| Children | - | HashMap\<TChildEntityKey,TChildEntityNode> |  |
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
| Participants | - | [UsmfDictionary`2](#usmfdictionary`2)\<String,UsmfFixtureParticipantStateNode> |  |
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
