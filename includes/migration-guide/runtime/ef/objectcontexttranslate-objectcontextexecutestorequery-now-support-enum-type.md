---
ms.openlocfilehash: 6af8e97423c04abca25feb8d77ea9ab6e198a4f0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620332"
---
### <a name="objectcontexttranslate-and-objectcontextexecutestorequery-now-support-enum-type"></a><span data-ttu-id="6fe8c-101">ObjectContext.Translate und ObjectContext.ExecuteStoreQuery unterstützen jetzt den Enumerationstyp</span><span class="sxs-lookup"><span data-stu-id="6fe8c-101">ObjectContext.Translate and ObjectContext.ExecuteStoreQuery now support enum type</span></span>

#### <a name="details"></a><span data-ttu-id="6fe8c-102">Details</span><span class="sxs-lookup"><span data-stu-id="6fe8c-102">Details</span></span>

<span data-ttu-id="6fe8c-103">In .NET Framework 4.0 konnte der generische Parameter <code>T</code> von <code>ObjectContext.Translate</code>- und <code>ObjectContext.ExecuteStoreQuery</code>-Methoden kein Enumerationstyp sein.</span><span class="sxs-lookup"><span data-stu-id="6fe8c-103">In .NET Framework 4.0, the generic parameter <code>T</code> of <code>ObjectContext.Translate</code> and <code>ObjectContext.ExecuteStoreQuery</code> methods could not be an enum.</span></span> <span data-ttu-id="6fe8c-104">Dieses Szenario wird jetzt unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6fe8c-104">That scenario is now supported.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="6fe8c-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="6fe8c-105">Suggestion</span></span>

<span data-ttu-id="6fe8c-106">Wenn für einen Enumerationstyp in .NET Framework 4.0 „Translate“ oder „ExecuteStoreQuery“ aufgerufen wurde, wurde „0“ zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6fe8c-106">If Translate or ExecuteStoreQuery was called on an enum type in .NET Framework 4.0, '0' was returned.</span></span> <span data-ttu-id="6fe8c-107">Wenn dieses Verhalten erwünscht war, sollten die Aufrufe durch eine konstante 0 (oder das entsprechende Enum-Äquivalent) ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="6fe8c-107">If that behavior was desirable, the calls should be replaced with a constant 0 (or the enum equivalent of it).</span></span>

| <span data-ttu-id="6fe8c-108">name</span><span class="sxs-lookup"><span data-stu-id="6fe8c-108">Name</span></span>    | <span data-ttu-id="6fe8c-109">Wert</span><span class="sxs-lookup"><span data-stu-id="6fe8c-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="6fe8c-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="6fe8c-110">Scope</span></span>   |<span data-ttu-id="6fe8c-111">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6fe8c-111">Edge</span></span>|
|<span data-ttu-id="6fe8c-112">Version</span><span class="sxs-lookup"><span data-stu-id="6fe8c-112">Version</span></span>|<span data-ttu-id="6fe8c-113">4.5</span><span class="sxs-lookup"><span data-stu-id="6fe8c-113">4.5</span></span>|
|<span data-ttu-id="6fe8c-114">Typ</span><span class="sxs-lookup"><span data-stu-id="6fe8c-114">Type</span></span>|<span data-ttu-id="6fe8c-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="6fe8c-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="6fe8c-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6fe8c-116">Affected APIs</span></span>

-<xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.Translate%60%601(System.Data.Common.DbDataReader,System.String,System.Data.Objects.MergeOption)?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.Object[])?displayProperty=nameWithType></li><li><xref:System.Data.Objects.ObjectContext.ExecuteStoreQuery%60%601(System.String,System.String,System.Data.Objects.MergeOption,System.Object[])?displayProperty=nameWithType></li></ul>|
