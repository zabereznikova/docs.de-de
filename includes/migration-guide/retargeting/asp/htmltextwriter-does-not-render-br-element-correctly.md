---
ms.openlocfilehash: e600b8249096eecb13f63ea00343a771a8c12b60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804524"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="d88c6-101">HtmlTextWriter rendert das Element `<br/>` nicht ordnungsgemäß</span><span class="sxs-lookup"><span data-stu-id="d88c6-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d88c6-102">Details</span><span class="sxs-lookup"><span data-stu-id="d88c6-102">Details</span></span>|<span data-ttu-id="d88c6-103">Ab .NET Framework 4.6 fügt der Aufruf von <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> und <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> mit einem <code>&lt;BR /&gt;</code>-Element ordnungsgemäß nur ein (anstatt zwei) <code>&lt;BR /&gt;</code> ein.</span><span class="sxs-lookup"><span data-stu-id="d88c6-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a <code>&lt;BR /&gt;</code> element will correctly insert only one <code>&lt;BR /&gt;</code> (instead of two)</span></span>|
|<span data-ttu-id="d88c6-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="d88c6-104">Suggestion</span></span>|<span data-ttu-id="d88c6-105">Wenn eine App vom zusätzlichen <code>&lt;BR /&gt;</code>-Tag abhängig ist, sollte <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> ein zweites Mal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d88c6-105">If an app depended on the extra <code>&lt;BR /&gt;</code> tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="d88c6-106">Beachten Sie, das sich diese Verhaltensänderung nur auf Apps mit der Zielplattform .NET Framework 4.6 oder höher auswirkt. Eine weitere Möglichkeit ist daher die Ausrichtung auf eine vorherige Version von .NET Framework, mit der das alte Verhalten genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d88c6-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>|
|<span data-ttu-id="d88c6-107">`Scope`</span><span class="sxs-lookup"><span data-stu-id="d88c6-107">Scope</span></span>|<span data-ttu-id="d88c6-108">Edge</span><span class="sxs-lookup"><span data-stu-id="d88c6-108">Edge</span></span>|
|<span data-ttu-id="d88c6-109">Version</span><span class="sxs-lookup"><span data-stu-id="d88c6-109">Version</span></span>|<span data-ttu-id="d88c6-110">4.6</span><span class="sxs-lookup"><span data-stu-id="d88c6-110">4.6</span></span>|
|<span data-ttu-id="d88c6-111">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d88c6-111">Type</span></span>|<span data-ttu-id="d88c6-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="d88c6-112">Retargeting</span></span>|
|<span data-ttu-id="d88c6-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="d88c6-113">Affected APIs</span></span>|<ul><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType></li></ul>|
