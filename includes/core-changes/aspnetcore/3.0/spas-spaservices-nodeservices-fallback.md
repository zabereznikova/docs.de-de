---
ms.openlocfilehash: e5355387d5cb6d9e6de89f5b85e64bc100b32ae1
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032682"
---
### <a name="spas-spaservices-and-nodeservices-no-longer-fall-back-to-console-logger"></a><span data-ttu-id="1a426-101">SPAs: Kein Fallback für SpaServices und NodeServices mehr auf die Konsolenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="1a426-101">SPAs: SpaServices and NodeServices no longer fall back to console logger</span></span>

<span data-ttu-id="1a426-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> und <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> zeigen nur dann Konsolenprotokolle an, wenn die Protokollierung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="1a426-102"><xref:Microsoft.AspNetCore.SpaServices?displayProperty=nameWithType> and <xref:Microsoft.AspNetCore.NodeServices?displayProperty=nameWithType> won't display console logs unless logging is configured.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1a426-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="1a426-103">Version introduced</span></span>

<span data-ttu-id="1a426-104">3.0</span><span class="sxs-lookup"><span data-stu-id="1a426-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="1a426-105">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="1a426-105">Old behavior</span></span>

<span data-ttu-id="1a426-106">`Microsoft.AspNetCore.SpaServices` und `Microsoft.AspNetCore.NodeServices` erstellten automatisch eine Konsolenprotokollierung, wenn die Protokollierung nicht konfiguriert war.</span><span class="sxs-lookup"><span data-stu-id="1a426-106">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` used to automatically create a console logger when logging isn't configured.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="1a426-107">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="1a426-107">New behavior</span></span>

<span data-ttu-id="1a426-108">`Microsoft.AspNetCore.SpaServices` und `Microsoft.AspNetCore.NodeServices` zeigen nur dann Konsolenprotokolle an, wenn die Protokollierung konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="1a426-108">`Microsoft.AspNetCore.SpaServices` and `Microsoft.AspNetCore.NodeServices` won't display console logs unless logging is configured.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1a426-109">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="1a426-109">Reason for change</span></span>

<span data-ttu-id="1a426-110">Mit dieser Änderung soll eine Anpassung an die Implementierung der Protokollierung in anderen ASP.NET Core-Paketen umgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="1a426-110">There's a need to align with how other ASP.NET Core packages implement logging.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1a426-111">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="1a426-111">Recommended action</span></span>

<span data-ttu-id="1a426-112">Wenn das alte Verhalten erforderlich ist, fügen Sie zum Konfigurieren der Konsolenprotokollierung Ihrer `Setup.ConfigureServices`-Methode `services.AddLogging(builder => builder.AddConsole())` hinzu.</span><span class="sxs-lookup"><span data-stu-id="1a426-112">If the old behavior is required, to configure console logging, add `services.AddLogging(builder => builder.AddConsole())` to your `Setup.ConfigureServices` method.</span></span>

#### <a name="category"></a><span data-ttu-id="1a426-113">Kategorie</span><span class="sxs-lookup"><span data-stu-id="1a426-113">Category</span></span>

<span data-ttu-id="1a426-114">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1a426-114">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1a426-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1a426-115">Affected APIs</span></span>

<span data-ttu-id="1a426-116">Keine</span><span class="sxs-lookup"><span data-stu-id="1a426-116">None</span></span>

<!--

#### Affected APIs

Not detectable via API analysis

-->
