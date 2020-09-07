---
ms.openlocfilehash: 81992e57d7e92b4df92ce68870c0272d6cd5b220
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497362"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a><span data-ttu-id="18bdc-101">ObjectContext.Translate und ObjectContext.ExecuteStoreQuery unterstützen jetzt den Enumerationstyp</span><span class="sxs-lookup"><span data-stu-id="18bdc-101">ObjectContext.Translate and ObjectContext.ExecuteStoreQuery now support enum type</span></span>

#### <a name="details"></a><span data-ttu-id="18bdc-102">Details</span><span class="sxs-lookup"><span data-stu-id="18bdc-102">Details</span></span>

<span data-ttu-id="18bdc-103">In .NET Framework 4.0 konnte der generische Parameter <code>T</code> von <code>ObjectContext.Translate</code>- und <code>ObjectContext.ExecuteStoreQuery</code>-Methoden kein Enumerationstyp sein.</span><span class="sxs-lookup"><span data-stu-id="18bdc-103">In .NET Framework 4.0, the generic parameter <code>T</code> of <code>ObjectContext.Translate</code> and <code>ObjectContext.ExecuteStoreQuery</code> methods could not be an enum.</span></span> <span data-ttu-id="18bdc-104">Dieses Szenario wird jetzt unterstützt.</span><span class="sxs-lookup"><span data-stu-id="18bdc-104">That scenario is now supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="18bdc-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="18bdc-105">Suggestion</span></span>

<span data-ttu-id="18bdc-106">Wenn für einen Enumerationstyp in .NET Framework 4.0 „Translate“ oder „ExecuteStoreQuery“ aufgerufen wurde, wurde „0“ zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="18bdc-106">If Translate or ExecuteStoreQuery was called on an enum type in .NET Framework 4.0, '0' was returned.</span></span> <span data-ttu-id="18bdc-107">Wenn dieses Verhalten erwünscht war, sollten die Aufrufe durch eine konstante 0 (oder das entsprechende Enum-Äquivalent) ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="18bdc-107">If that behavior was desirable, the calls should be replaced with a constant 0 (or the enum equivalent of it).</span></span>

| <span data-ttu-id="18bdc-108">name</span><span class="sxs-lookup"><span data-stu-id="18bdc-108">Name</span></span>    | <span data-ttu-id="18bdc-109">Wert</span><span class="sxs-lookup"><span data-stu-id="18bdc-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="18bdc-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="18bdc-110">Scope</span></span>   |<span data-ttu-id="18bdc-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="18bdc-111">Edge</span></span>|
|<span data-ttu-id="18bdc-112">Version</span><span class="sxs-lookup"><span data-stu-id="18bdc-112">Version</span></span>|<span data-ttu-id="18bdc-113">4.5</span><span class="sxs-lookup"><span data-stu-id="18bdc-113">4.5</span></span>|
|<span data-ttu-id="18bdc-114">Typ</span><span class="sxs-lookup"><span data-stu-id="18bdc-114">Type</span></span>|<span data-ttu-id="18bdc-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="18bdc-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="18bdc-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="18bdc-116">Affected APIs</span></span>

- <xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType>
- <xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType>
- <xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType>
- <xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|

<!--

#### Affected APIs

- ``M:System.Data.Objects.ObjectContext.Translate``1(System.Data.Common.DbDataReader)``
- ``M:System.Data.Objects.ObjectContext.Translate``1(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)``
- ``M:System.Data.Objects.ObjectContext.ExecuteStoreQuery``1(System.String,System.Object[])``
- ``M:System.Data.Objects.ObjectContext.ExecuteStoreQuery``1(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])``

-->
