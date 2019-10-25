---
ms.openlocfilehash: acef6d7177ee5ad7e18dc8ba1e383d6f76263623
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394446"
---
### <a name="signalr-javascript-client-package-name-changed"></a><span data-ttu-id="aafb1-101">SignalR: Name des JavaScript-Clientpakets geändert</span><span class="sxs-lookup"><span data-stu-id="aafb1-101">SignalR: JavaScript client package name changed</span></span>

<span data-ttu-id="aafb1-102">In ASP.NET Core 3.0 Preview 7 wurde der Name des SignalR-JavaScript-Clientpakets von `@aspnet/signalr` in `@microsoft/signalr` geändert.</span><span class="sxs-lookup"><span data-stu-id="aafb1-102">In ASP.NET Core 3.0 Preview 7, the SignalR JavaScript client package name changed from `@aspnet/signalr` to `@microsoft/signalr`.</span></span> <span data-ttu-id="aafb1-103">Die Namensänderung spiegelt die Tatsache wider, dass SignalR dank Azure SignalR Service für mehr als nur ASP.NET Core-Apps nützlich ist.</span><span class="sxs-lookup"><span data-stu-id="aafb1-103">The name change reflects the fact that SignalR is useful in more than just ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

<span data-ttu-id="aafb1-104">Um auf diese Änderung zu reagieren, ändern Sie die Verweise in Ihren *package.json*-Dateien, `require`-Anweisungen und ECMAScript-`import`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="aafb1-104">To react to this change, change references in your *package.json* files, `require` statements, and ECMAScript `import` statements.</span></span> <span data-ttu-id="aafb1-105">Im Rahmen dieser Umbenennung werden keine APIs geändert.</span><span class="sxs-lookup"><span data-stu-id="aafb1-105">No API will change as part of this rename.</span></span>

<span data-ttu-id="aafb1-106">Weitere Informationen finden Sie unter [aspnet/AspNetCore#11637](https://github.com/aspnet/AspNetCore/issues/11637).</span><span class="sxs-lookup"><span data-stu-id="aafb1-106">For discussion, see [aspnet/AspNetCore#11637](https://github.com/aspnet/AspNetCore/issues/11637).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="aafb1-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="aafb1-107">Version introduced</span></span>

<span data-ttu-id="aafb1-108">3.0</span><span class="sxs-lookup"><span data-stu-id="aafb1-108">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="aafb1-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="aafb1-109">Old behavior</span></span>

<span data-ttu-id="aafb1-110">Das Clientpaket hatte den Namen `@aspnet/signalr`.</span><span class="sxs-lookup"><span data-stu-id="aafb1-110">The client package was named `@aspnet/signalr`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="aafb1-111">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="aafb1-111">New behavior</span></span>

<span data-ttu-id="aafb1-112">Das Clientpaket hat jetzt den Namen `@microsoft/signalr`.</span><span class="sxs-lookup"><span data-stu-id="aafb1-112">The client package is named `@microsoft/signalr`.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="aafb1-113">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="aafb1-113">Reason for change</span></span>

<span data-ttu-id="aafb1-114">Die Namensänderung macht deutlich, dass SignalR dank Azure SignalR Service für mehr als nur ASP.NET Core-Apps nützlich ist.</span><span class="sxs-lookup"><span data-stu-id="aafb1-114">The name change clarifies that SignalR is useful beyond ASP.NET Core apps, thanks to the Azure SignalR Service.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="aafb1-115">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="aafb1-115">Recommended action</span></span>

<span data-ttu-id="aafb1-116">Stellen Sie auf das neue Paket `@microsoft/signalr` um.</span><span class="sxs-lookup"><span data-stu-id="aafb1-116">Switch to the new package `@microsoft/signalr`.</span></span>

#### <a name="category"></a><span data-ttu-id="aafb1-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="aafb1-117">Category</span></span>

<span data-ttu-id="aafb1-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="aafb1-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="aafb1-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="aafb1-119">Affected APIs</span></span>

<span data-ttu-id="aafb1-120">Keine</span><span class="sxs-lookup"><span data-stu-id="aafb1-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
