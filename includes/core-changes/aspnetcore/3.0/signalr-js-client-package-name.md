---
ms.openlocfilehash: f202b39f1a45f740625827be25e72df0e403d605
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901997"
---
### <a name="signalr-javascript-client-package-name-changed"></a><span data-ttu-id="95518-101">SignalR: Name des JavaScript-Clientpakets geändert</span><span class="sxs-lookup"><span data-stu-id="95518-101">SignalR: JavaScript client package name changed</span></span>

<span data-ttu-id="95518-102">In ASP.NET Core 3.0 Preview 7 wurde der Name des SignalR-JavaScript-Clientpakets von `@aspnet/signalr` in `@microsoft/signalr` geändert.</span><span class="sxs-lookup"><span data-stu-id="95518-102">In ASP.NET Core 3.0 Preview 7, the SignalR JavaScript client package name changed from `@aspnet/signalr` to `@microsoft/signalr`.</span></span> <span data-ttu-id="95518-103">Die Namensänderung spiegelt die Tatsache wider, dass SignalR dank Azure SignalR Service für mehr als nur ASP.NET Core-Apps nützlich ist.</span><span class="sxs-lookup"><span data-stu-id="95518-103">The name change reflects the fact that SignalR is useful in more than just ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

<span data-ttu-id="95518-104">Um auf diese Änderung zu reagieren, ändern Sie die Verweise in Ihren *package.json*-Dateien, `require`-Anweisungen und ECMAScript-`import`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="95518-104">To react to this change, change references in your *package.json* files, `require` statements, and ECMAScript `import` statements.</span></span> <span data-ttu-id="95518-105">Im Rahmen dieser Umbenennung werden keine APIs geändert.</span><span class="sxs-lookup"><span data-stu-id="95518-105">No API will change as part of this rename.</span></span>

<span data-ttu-id="95518-106">Weitere Informationen finden Sie unter [dotnet/aspnetcore#11637](https://github.com/dotnet/aspnetcore/issues/11637).</span><span class="sxs-lookup"><span data-stu-id="95518-106">For discussion, see [dotnet/aspnetcore#11637](https://github.com/dotnet/aspnetcore/issues/11637).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="95518-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="95518-107">Version introduced</span></span>

<span data-ttu-id="95518-108">3.0</span><span class="sxs-lookup"><span data-stu-id="95518-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="95518-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="95518-109">Old behavior</span></span>

<span data-ttu-id="95518-110">Das Clientpaket hatte den Namen `@aspnet/signalr`.</span><span class="sxs-lookup"><span data-stu-id="95518-110">The client package was named `@aspnet/signalr`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="95518-111">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="95518-111">New behavior</span></span>

<span data-ttu-id="95518-112">Das Clientpaket hat jetzt den Namen `@microsoft/signalr`.</span><span class="sxs-lookup"><span data-stu-id="95518-112">The client package is named `@microsoft/signalr`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="95518-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="95518-113">Reason for change</span></span>

<span data-ttu-id="95518-114">Die Namensänderung macht deutlich, dass SignalR dank Azure SignalR Service für mehr als nur ASP.NET Core-Apps nützlich ist.</span><span class="sxs-lookup"><span data-stu-id="95518-114">The name change clarifies that SignalR is useful beyond ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="95518-115">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="95518-115">Recommended action</span></span>

<span data-ttu-id="95518-116">Stellen Sie auf das neue Paket `@microsoft/signalr` um.</span><span class="sxs-lookup"><span data-stu-id="95518-116">Switch to the new package `@microsoft/signalr`.</span></span>

#### <a name="category"></a><span data-ttu-id="95518-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="95518-117">Category</span></span>

<span data-ttu-id="95518-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="95518-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="95518-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="95518-119">Affected APIs</span></span>

<span data-ttu-id="95518-120">Keine</span><span class="sxs-lookup"><span data-stu-id="95518-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
