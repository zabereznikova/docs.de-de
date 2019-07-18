---
ms.openlocfilehash: 1d2d6133683360b97569e49402e7c8c4d182b65d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804016"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a>ObjectContext.Translate und ObjectContext.ExecuteStoreQuery unterstützen jetzt den Enumerationstyp

|   |   |
|---|---|
|Details|In .NET Framework 4.0 konnte der generische Parameter <code>T</code> von <code>ObjectContext.Translate</code>- und <code>ObjectContext.ExecuteStoreQuery</code>-Methoden kein Enumerationstyp sein. Dieses Szenario wird jetzt unterstützt.|
|Vorschlag|Wenn für einen Enumerationstyp in .NET Framework 4.0 „Translate“ oder „ExecuteStoreQuery“ aufgerufen wurde, wurde „0“ zurückgegeben. Wenn dieses Verhalten erwünscht war, sollten die Aufrufe durch eine konstante 0 (oder das entsprechende Enum-Äquivalent) ersetzt werden.|
|Bereich|Microsoft Edge|
|Version|4.5|
|Typ|Laufzeit|
|Betroffene APIs|<ul><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
