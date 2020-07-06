---
ms.openlocfilehash: 150b98255b3075a8fe8cad60ce234206b788a5f5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617188"
---
### <a name="multi-line-aspnet-textbox-spacing-changed-when-using-antixssencoder"></a><span data-ttu-id="e1b62-101">Der Abstand für mehrzeilige ASP.NET-Textfelder (TextBox) wurde bei der Verwendung von AntiXSSEncoder geändert</span><span class="sxs-lookup"><span data-stu-id="e1b62-101">Multi-line ASP.Net TextBox spacing changed when using AntiXSSEncoder</span></span>

#### <a name="details"></a><span data-ttu-id="e1b62-102">Details</span><span class="sxs-lookup"><span data-stu-id="e1b62-102">Details</span></span>

<span data-ttu-id="e1b62-103">In .NET Framework 4.0 wurden zwischen Zeilen eines mehrzeiligen Textfelds beim Postback zusätzliche Zeilen eingefügt, wenn <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e1b62-103">In .NET Framework 4.0, extra lines were inserted between lines of a multi-line text box on postback, if using the <xref:System.Web.Security.AntiXss.AntiXssEncoder?displayProperty=fullName>.</span></span> <span data-ttu-id="e1b62-104">In .NET Framework 4.5 sind diese zusätzlichen Zeilenumbrüche nicht enthalten, wenn die Web-App auf .NET Framework 4.5 ausgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e1b62-104">In .NET Framework 4.5, those extra line breaks are not included, but only if the web app is targeting .NET Framework 4.5</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e1b62-105">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="e1b62-105">Suggestion</span></span>

<span data-ttu-id="e1b62-106">Beachten Sie, dass bei Web-Apps der Version 4.0, die auf .NET Framework 4.5 neu ausgelegt wurden, mehrzeilige Textfelder möglicherweise verbessert wurden, damit diese keine zusätzlichen Zeilenumbrüche mehr einfügen.</span><span class="sxs-lookup"><span data-stu-id="e1b62-106">Be aware that 4.0 web apps retargeted to .NET Framework 4.5 may have multi-line text boxes improved to no longer insert extra line breaks.</span></span> <span data-ttu-id="e1b62-107">Wenn dies nicht erwünscht ist, kann die App das alte Verhalten verwenden, wenn sie unter .NET Framework 4.5 ausgeführt wird, indem sie auf .NET Framework 4.0 ausgerichtet wird.</span><span class="sxs-lookup"><span data-stu-id="e1b62-107">If this is not desirable, the app  can have the old behavior when running on .NET Framework 4.5 by targeting the .NET Framework 4.0.</span></span>

| <span data-ttu-id="e1b62-108">name</span><span class="sxs-lookup"><span data-stu-id="e1b62-108">Name</span></span>    | <span data-ttu-id="e1b62-109">Wert</span><span class="sxs-lookup"><span data-stu-id="e1b62-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e1b62-110">Bereich</span><span class="sxs-lookup"><span data-stu-id="e1b62-110">Scope</span></span>   | <span data-ttu-id="e1b62-111">Gering</span><span class="sxs-lookup"><span data-stu-id="e1b62-111">Minor</span></span>       |
| <span data-ttu-id="e1b62-112">Version</span><span class="sxs-lookup"><span data-stu-id="e1b62-112">Version</span></span> | <span data-ttu-id="e1b62-113">4.5</span><span class="sxs-lookup"><span data-stu-id="e1b62-113">4.5</span></span>         |
| <span data-ttu-id="e1b62-114">Typ</span><span class="sxs-lookup"><span data-stu-id="e1b62-114">Type</span></span>    | <span data-ttu-id="e1b62-115">Neuzuweisung</span><span class="sxs-lookup"><span data-stu-id="e1b62-115">Retargeting</span></span> |
