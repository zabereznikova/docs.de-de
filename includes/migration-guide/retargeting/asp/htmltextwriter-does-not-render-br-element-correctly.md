---
ms.openlocfilehash: 8f03e5166e7f1f598e9bba7fb8c550809f287b82
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85615650"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="4f88b-101">HtmlTextWriter rendert das Element `<br/>` nicht ordnungsgemäß</span><span class="sxs-lookup"><span data-stu-id="4f88b-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

#### <a name="details"></a><span data-ttu-id="4f88b-102">Details</span><span class="sxs-lookup"><span data-stu-id="4f88b-102">Details</span></span>

<span data-ttu-id="4f88b-103">Ab .NET Framework 4.6 fügt der Aufruf von <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> und <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> mit einem `<BR />`-Element ordnungsgemäß nur ein (anstatt zwei) `<BR />` ein.</span><span class="sxs-lookup"><span data-stu-id="4f88b-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a `<BR />` element will correctly insert only one `<BR />` (instead of two)</span></span>

#### <a name="suggestion"></a><span data-ttu-id="4f88b-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="4f88b-104">Suggestion</span></span>

<span data-ttu-id="4f88b-105">Wenn eine App vom zusätzlichen `<BR />`-Tag abhängig ist, sollte <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> ein zweites Mal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="4f88b-105">If an app depended on the extra `<BR />` tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="4f88b-106">Beachten Sie, das sich diese Verhaltensänderung nur auf Apps mit der Zielplattform .NET Framework 4.6 oder höher auswirkt. Eine weitere Möglichkeit ist daher die Ausrichtung auf eine vorherige Version von .NET Framework, mit der das alte Verhalten genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="4f88b-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>

| <span data-ttu-id="4f88b-107">name</span><span class="sxs-lookup"><span data-stu-id="4f88b-107">Name</span></span>    | <span data-ttu-id="4f88b-108">Wert</span><span class="sxs-lookup"><span data-stu-id="4f88b-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="4f88b-109">Bereich</span><span class="sxs-lookup"><span data-stu-id="4f88b-109">Scope</span></span>   | <span data-ttu-id="4f88b-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4f88b-110">Edge</span></span>        |
| <span data-ttu-id="4f88b-111">Version</span><span class="sxs-lookup"><span data-stu-id="4f88b-111">Version</span></span> | <span data-ttu-id="4f88b-112">4.6</span><span class="sxs-lookup"><span data-stu-id="4f88b-112">4.6</span></span>         |
| <span data-ttu-id="4f88b-113">Typ</span><span class="sxs-lookup"><span data-stu-id="4f88b-113">Type</span></span>    | <span data-ttu-id="4f88b-114">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="4f88b-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="4f88b-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="4f88b-115">Affected APIs</span></span>

- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType>
- <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType>
