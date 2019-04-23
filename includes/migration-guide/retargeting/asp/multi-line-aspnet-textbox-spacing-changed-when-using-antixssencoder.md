---
ms.openlocfilehash: e2bca42daebd25667ab2f312d5e59089b986503c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774361"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a><span data-ttu-id="79b50-101">Der Abstand für mehrzeilige ASP.NET-Textfelder (TextBox) wurde bei der Verwendung von AntiXSSEncoder geändert</span><span class="sxs-lookup"><span data-stu-id="79b50-101">Multi-line ASP.Net TextBox spacing changed when using AntiXSSEncoder</span></span>

|   |   |
|---|---|
|<span data-ttu-id="79b50-102">Details</span><span class="sxs-lookup"><span data-stu-id="79b50-102">Details</span></span>|<span data-ttu-id="79b50-103">In .NET Framework 4.0 wurden zwischen Zeilen eines mehrzeiligen Textfelds beim Postback zusätzliche Zeilen eingefügt, wenn <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="79b50-103">In .NET Framework 4.0, extra lines were inserted between lines of a multi-line text box on postback, if using the <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=name>.</span></span> <span data-ttu-id="79b50-104">In .NET Framework 4.5 sind diese zusätzlichen Zeilenumbrüche nicht enthalten, wenn die Web-App auf .NET Framework 4.5 ausgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="79b50-104">In .NET Framework 4.5, those extra line breaks are not included, but only if the web app is targeting .NET Framework 4.5</span></span>|
|<span data-ttu-id="79b50-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="79b50-105">Suggestion</span></span>|<span data-ttu-id="79b50-106">Beachten Sie, dass bei Web-Apps der Version 4.0, die auf .NET Framework 4.5 neu ausgelegt wurden, mehrzeilige Textfelder möglicherweise verbessert wurden, damit diese keine zusätzlichen Zeilenumbrüche mehr einfügen.</span><span class="sxs-lookup"><span data-stu-id="79b50-106">Be aware that 4.0 web apps retargeted to .NET Framework 4.5 may have multi-line text boxes improved to no longer insert extra line breaks.</span></span> <span data-ttu-id="79b50-107">Wenn dies nicht erwünscht ist, kann die App das alte Verhalten verwenden, wenn sie unter .NET Framework 4.5 ausgeführt wird, indem sie auf .NET Framework 4.0 ausgerichtet wird.</span><span class="sxs-lookup"><span data-stu-id="79b50-107">If this is not desirable, the app  can have the old behavior when running on .NET Framework 4.5 by targeting the .NET Framework 4.0.</span></span>|
|<span data-ttu-id="79b50-108">Bereich</span><span class="sxs-lookup"><span data-stu-id="79b50-108">Scope</span></span>|<span data-ttu-id="79b50-109">Gering</span><span class="sxs-lookup"><span data-stu-id="79b50-109">Minor</span></span>|
|<span data-ttu-id="79b50-110">Version</span><span class="sxs-lookup"><span data-stu-id="79b50-110">Version</span></span>|<span data-ttu-id="79b50-111">4.5</span><span class="sxs-lookup"><span data-stu-id="79b50-111">4.5</span></span>|
|<span data-ttu-id="79b50-112">Typ</span><span class="sxs-lookup"><span data-stu-id="79b50-112">Type</span></span>|<span data-ttu-id="79b50-113">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="79b50-113">Retargeting</span></span>|
