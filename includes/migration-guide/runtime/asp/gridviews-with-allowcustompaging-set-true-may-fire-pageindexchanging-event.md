---
ms.openlocfilehash: 4d210eeedd2f228017634d29f11554deb6ed8079
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496715"
---
### <a name="gridviews-with-allowcustompaging-set-to-true-may-fire-the-pageindexchanging-event-when-leaving-the-final-page-of-the-view"></a><span data-ttu-id="0cebf-101">GridView-Steuerelemente, bei denen „AllowCustomPaging“ auf TRUE festgelegt ist, kann das Ereignis „PageIndexChanging“ ausgelöst werden, wenn die letzte Seite der Ansicht verlassen wird</span><span class="sxs-lookup"><span data-stu-id="0cebf-101">GridViews with AllowCustomPaging set to true may fire the PageIndexChanging event when leaving the final page of the view</span></span>

#### <a name="details"></a><span data-ttu-id="0cebf-102">Details</span><span class="sxs-lookup"><span data-stu-id="0cebf-102">Details</span></span>

<span data-ttu-id="0cebf-103">Ein Fehler in .NET Framework 4.5 führt dazu, dass <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> für <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>-Steuerelemente, bei denen <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName> nicht aktiviert ist, manchmal nicht ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="0cebf-103">A bug in the .NET Framework 4.5 causes <xref:System.Web.UI.WebControls.GridView.PageIndexChanging?displayProperty=fullName> to sometimes not fire for <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName>s that have enabled <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=fullName>.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0cebf-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="0cebf-104">Suggestion</span></span>

<span data-ttu-id="0cebf-105">Dieses Problem wurde in .NET Framework 4.6 behoben und kann durch ein Upgrade auf diese Version von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="0cebf-105">This issue has been fixed in the .NET Framework 4.6 and may be addressed by upgrading to that version of the .NET Framework.</span></span> <span data-ttu-id="0cebf-106">Das Problem kann umgangen werden, indem die App eine explizite BindGrid-Bindung an eine beliebige <code>Page_Load</code>-Methode durchführt, die diese Bedingungen erfüllt (<xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> befindet sich auf der letzten Seite und Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> unterscheidet sich von <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span><span class="sxs-lookup"><span data-stu-id="0cebf-106">As a work-around, the app can do an explicit BindGrid on any <code>Page_Load</code> that would hit these conditions (the <xref:System.Web.UI.WebControls.GridView?displayProperty=fullName> is on the last page and Last<xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName> is different from <xref:System.Web.UI.WebControls.GridView.PageSize?displayProperty=fullName>).</span></span> <span data-ttu-id="0cebf-107">Alternativ kann die App geändert werden, um Paging (statt benutzerdefiniertem Paging) zuzulassen, da das Problem in diesem Szenario nicht auftritt.</span><span class="sxs-lookup"><span data-stu-id="0cebf-107">Alternatively, the app can be modified to allow paging (instead of custom paging), as that scenario does not demonstrate the problem.</span></span>

| <span data-ttu-id="0cebf-108">name</span><span class="sxs-lookup"><span data-stu-id="0cebf-108">Name</span></span>    | <span data-ttu-id="0cebf-109">Wert</span><span class="sxs-lookup"><span data-stu-id="0cebf-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0cebf-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="0cebf-110">Scope</span></span>   |<span data-ttu-id="0cebf-111">Gering</span><span class="sxs-lookup"><span data-stu-id="0cebf-111">Minor</span></span>|
|<span data-ttu-id="0cebf-112">Version</span><span class="sxs-lookup"><span data-stu-id="0cebf-112">Version</span></span>|<span data-ttu-id="0cebf-113">4.5</span><span class="sxs-lookup"><span data-stu-id="0cebf-113">4.5</span></span>|
|<span data-ttu-id="0cebf-114">Typ</span><span class="sxs-lookup"><span data-stu-id="0cebf-114">Type</span></span>|<span data-ttu-id="0cebf-115">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="0cebf-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0cebf-116">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="0cebf-116">Affected APIs</span></span>

- <xref:System.Web.UI.WebControls.GridView.AllowCustomPaging?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.Web.UI.WebControls.GridView.AllowCustomPaging`

-->
