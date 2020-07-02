---
ms.openlocfilehash: 3b329bf5ba2af4d3ab9c3e203e99daba8ca0d0c0
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620141"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a><span data-ttu-id="b9d5f-101">GridView-Steuerelemente, bei denen „AllowCustomPaging“ auf TRUE festgelegt ist, kann das Ereignis „PageIndexChanging“ ausgelöst werden, wenn die letzte Seite der Ansicht verlassen wird</span><span class="sxs-lookup"><span data-stu-id="b9d5f-101">GridViews with AllowCustomPaging set to true may fire the PageIndexChanging event when leaving the final page of the view</span></span>

#### <a name="details"></a><span data-ttu-id="b9d5f-102">Details</span><span class="sxs-lookup"><span data-stu-id="b9d5f-102">Details</span></span>

<span data-ttu-id="b9d5f-103">Ein Fehler in .NET Framework 4.5 führt dazu, dass <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> für <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>-Steuerelemente, bei denen <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName> nicht aktiviert ist, manchmal nicht ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="b9d5f-103">A bug in the .NET Framework 4.5 causes <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> to sometimes not fire for <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>s that have enabled <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b9d5f-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="b9d5f-104">Suggestion</span></span>

<span data-ttu-id="b9d5f-105">Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="b9d5f-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span> <span data-ttu-id="b9d5f-106">Das Problem kann umgangen werden, indem die App eine explizite BindGrid-Bindung an eine beliebige <code>Page_Load</code>-Methode durchführt, die diese Bedingungen erfüllt (<xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> befindet sich auf der letzten Seite und Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> unterscheidet sich von <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="b9d5f-106">As a work-around, the app can do an explicit BindGrid on any <code>Page_Load</code> that would hit these conditions (the <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> is on the last page and Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> is different from <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span></span> <span data-ttu-id="b9d5f-107">Alternativ kann die App geändert werden, um Paging (statt benutzerdefiniertem Paging) zuzulassen, da das Problem in diesem Szenario nicht auftritt.</span><span class="sxs-lookup"><span data-stu-id="b9d5f-107">Alternatively, the app can be modified to allow paging (instead of custom paging), as that scenario does not demonstrate the problem.</span></span>

| <span data-ttu-id="b9d5f-108">name</span><span class="sxs-lookup"><span data-stu-id="b9d5f-108">Name</span></span>    | <span data-ttu-id="b9d5f-109">Wert</span><span class="sxs-lookup"><span data-stu-id="b9d5f-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b9d5f-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="b9d5f-110">Scope</span></span>   |<span data-ttu-id="b9d5f-111">Gering</span><span class="sxs-lookup"><span data-stu-id="b9d5f-111">Minor</span></span>|
|<span data-ttu-id="b9d5f-112">Version</span><span class="sxs-lookup"><span data-stu-id="b9d5f-112">Version</span></span>|<span data-ttu-id="b9d5f-113">4.5</span><span class="sxs-lookup"><span data-stu-id="b9d5f-113">4.5</span></span>|
|<span data-ttu-id="b9d5f-114">Typ</span><span class="sxs-lookup"><span data-stu-id="b9d5f-114">Type</span></span>|<span data-ttu-id="b9d5f-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b9d5f-115">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b9d5f-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="b9d5f-116">Affected APIs</span></span>

-<xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType></li></ul>|
