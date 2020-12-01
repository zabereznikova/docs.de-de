---
ms.openlocfilehash: de06825f1031d05bc83183a83bae165e2f9512ff
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032661"
---
### <a name="signalr-hubconnection-resetsendping-and-resettimeout-methods-removed"></a><span data-ttu-id="11167-101">SignalR: Methoden ResetSendPing und ResetTimeout wurden aus HubConnection entfernt.</span><span class="sxs-lookup"><span data-stu-id="11167-101">SignalR: HubConnection ResetSendPing and ResetTimeout methods removed</span></span>

<span data-ttu-id="11167-102">Die Methoden `ResetSendPing` und `ResetTimeout` wurden aus der SignalR-API `HubConnection` entfernt.</span><span class="sxs-lookup"><span data-stu-id="11167-102">The `ResetSendPing` and `ResetTimeout` methods were removed from the SignalR `HubConnection` API.</span></span> <span data-ttu-id="11167-103">Diese Methoden waren ursprünglich nur für die interne Verwendung vorgesehen, wurden aber in ASP.NET Core 2.2 öffentlich („public“) gemacht.</span><span class="sxs-lookup"><span data-stu-id="11167-103">These methods were originally intended only for internal use but were made public in ASP.NET Core 2.2.</span></span> <span data-ttu-id="11167-104">Diese Methoden sind ab dem Release ASP.NET Core 3.0 Preview 4 nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="11167-104">These methods won't be available starting in the ASP.NET Core 3.0 Preview 4 release.</span></span> <span data-ttu-id="11167-105">Weitere Informationen finden Sie unter [dotnet/aspnetcore#8543](https://github.com/dotnet/aspnetcore/issues/8543).</span><span class="sxs-lookup"><span data-stu-id="11167-105">For discussion, see [dotnet/aspnetcore#8543](https://github.com/dotnet/aspnetcore/issues/8543).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="11167-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="11167-106">Version introduced</span></span>

<span data-ttu-id="11167-107">3.0</span><span class="sxs-lookup"><span data-stu-id="11167-107">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="11167-108">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="11167-108">Old behavior</span></span>

<span data-ttu-id="11167-109">Die APIs waren verfügbar.</span><span class="sxs-lookup"><span data-stu-id="11167-109">APIs were available.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="11167-110">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="11167-110">New behavior</span></span>

<span data-ttu-id="11167-111">Die APIs wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="11167-111">APIs are removed.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="11167-112">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="11167-112">Reason for change</span></span>

<span data-ttu-id="11167-113">Diese Methoden waren ursprünglich nur für die interne Verwendung vorgesehen, wurden aber in ASP.NET Core 2.2 öffentlich („public“) gemacht.</span><span class="sxs-lookup"><span data-stu-id="11167-113">These methods were originally intended only for internal use but were made public in ASP.NET Core 2.2.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="11167-114">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="11167-114">Recommended action</span></span>

<span data-ttu-id="11167-115">Verwenden Sie diese Methoden nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="11167-115">Don't use these methods.</span></span>

#### <a name="category"></a><span data-ttu-id="11167-116">Kategorie</span><span class="sxs-lookup"><span data-stu-id="11167-116">Category</span></span>

<span data-ttu-id="11167-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="11167-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="11167-118">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="11167-118">Affected APIs</span></span>

- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing?displayProperty=nameWithType>
- <xref:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetSendPing`
- `M:Microsoft.AspNetCore.SignalR.Client.HubConnection.ResetTimeout`

-->
