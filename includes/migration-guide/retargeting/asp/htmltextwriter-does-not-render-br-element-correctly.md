---
ms.openlocfilehash: 0ab6be6f2c6d8ebbe67051e4e3f967a325e654c8
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761089"
---
### <a name="htmltextwriter-does-not-render-br-element-correctly"></a><span data-ttu-id="1d099-101">HtmlTextWriter rendert das Element `<br/>` nicht ordnungsgemäß</span><span class="sxs-lookup"><span data-stu-id="1d099-101">HtmlTextWriter does not render `<br/>` element correctly</span></span>

|   |   |
|---|---|
|<span data-ttu-id="1d099-102">Details</span><span class="sxs-lookup"><span data-stu-id="1d099-102">Details</span></span>|<span data-ttu-id="1d099-103">Ab .NET Framework 4.6 fügt der Aufruf von <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> und <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> mit einem <code>&lt;BR /&gt;</code>-Element ordnungsgemäß nur ein (anstatt zwei) <code>&lt;BR /&gt;</code> ein.</span><span class="sxs-lookup"><span data-stu-id="1d099-103">Beginning in the .NET Framework 4.6, calling <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> and <xref:System.Web.UI.HtmlTextWriter.RenderEndTag> with a <code>&lt;BR /&gt;</code> element will correctly insert only one <code>&lt;BR /&gt;</code> (instead of two)</span></span>|
|<span data-ttu-id="1d099-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="1d099-104">Suggestion</span></span>|<span data-ttu-id="1d099-105">Wenn eine App vom zusätzlichen <code>&lt;BR /&gt;</code>-Tag abhängig ist, sollte <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> ein zweites Mal aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1d099-105">If an app depended on the extra <code>&lt;BR /&gt;</code> tag, <xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)> should be called a second time.</span></span> <span data-ttu-id="1d099-106">Beachten Sie, das sich diese Verhaltensänderung nur auf Apps mit der Zielplattform .NET Framework 4.6 oder höher auswirkt. Eine weitere Möglichkeit ist daher die Ausrichtung auf eine vorherige Version von .NET Framework, mit der das alte Verhalten genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1d099-106">Note that this behavior change only affects apps that target the .NET Framework 4.6 or later, so another option is to target a previous version of the .NET Framework in order to get the old behavior.</span></span>|
|<span data-ttu-id="1d099-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="1d099-107">Scope</span></span>|<span data-ttu-id="1d099-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="1d099-108">Edge</span></span>|
|<span data-ttu-id="1d099-109">Version</span><span class="sxs-lookup"><span data-stu-id="1d099-109">Version</span></span>|<span data-ttu-id="1d099-110">4.6</span><span class="sxs-lookup"><span data-stu-id="1d099-110">4.6</span></span>|
|<span data-ttu-id="1d099-111">Typ</span><span class="sxs-lookup"><span data-stu-id="1d099-111">Type</span></span>|<span data-ttu-id="1d099-112">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="1d099-112">Retargeting</span></span>|
|<span data-ttu-id="1d099-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1d099-113">Affected APIs</span></span>|<ul><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.String)?displayProperty=nameWithType></li><li><xref:System.Web.UI.HtmlTextWriter.RenderBeginTag(System.Web.UI.HtmlTextWriterTag)?displayProperty=nameWithType></li></ul>|

