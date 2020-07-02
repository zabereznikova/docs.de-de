---
ms.openlocfilehash: 6af8e97423c04abca25feb8d77ea9ab6e198a4f0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620332"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>ObjectContext.Translate und ObjectContext.ExecuteStoreQuery unterstützen jetzt den Enumerationstyp

#### <a name="details"></a>Details

In .NET Framework 4.0 konnte der generische Parameter <code>T</code> von <code>ObjectContext.Translate</code>- und <code>ObjectContext.ExecuteStoreQuery</code>-Methoden kein Enumerationstyp sein. Dieses Szenario wird jetzt unterstützt.

#### <a name="suggestion"></a>Vorschlag

Wenn für einen Enumerationstyp in .NET Framework 4.0 „Translate“ oder „ExecuteStoreQuery“ aufgerufen wurde, wurde „0“ zurückgegeben. Wenn dieses Verhalten erwünscht war, sollten die Aufrufe durch eine konstante 0 (oder das entsprechende Enum-Äquivalent) ersetzt werden.

| name    | Wert       |
|:--------|:------------|
| Bereich   |Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|

#### <a name="affected-apis"></a>Betroffene APIs

-<xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
