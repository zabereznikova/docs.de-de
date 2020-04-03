---
ms.openlocfilehash: ca0792a3fd05d28cecceac1d644e3e4bf64722bc
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345212"
---
### <a name="signalr-messagepack-hub-protocol-moved-to-messagepack-2x-package"></a><span data-ttu-id="935ae-101">SignalR: MessagePack-Hubprotokoll in MessagePack 2.x-Paket verschoben</span><span class="sxs-lookup"><span data-stu-id="935ae-101">SignalR: MessagePack Hub Protocol moved to MessagePack 2.x package</span></span>

<span data-ttu-id="935ae-102">Das [MessagePack-Hubprotokoll](/aspnet/core/signalr/messagepackhubprotocol) von ASP.NET Core SignalR verwendet das [NuGet-Paket „MessagePack“](https://www.nuget.org/packages/MessagePack) für die MessagePack-Serialisierung.</span><span class="sxs-lookup"><span data-stu-id="935ae-102">The ASP.NET Core SignalR [MessagePack Hub Protocol](/aspnet/core/signalr/messagepackhubprotocol) uses the [MessagePack NuGet package](https://www.nuget.org/packages/MessagePack) for MessagePack serialization.</span></span> <span data-ttu-id="935ae-103">In ASP.NET Core 5.0 wird das Paket von Version 1.x auf die neueste Paketversion 2.x aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="935ae-103">ASP.NET Core 5.0 upgrades the package from 1.x to the latest 2.x package version.</span></span>

<span data-ttu-id="935ae-104">Dieses Problem wird unter [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692) behandelt.</span><span class="sxs-lookup"><span data-stu-id="935ae-104">For discussion on this issue, see [dotnet/aspnetcore#18692](https://github.com/dotnet/aspnetcore/issues/18692).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="935ae-105">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="935ae-105">Version introduced</span></span>

<span data-ttu-id="935ae-106">5.0 Preview 1</span><span class="sxs-lookup"><span data-stu-id="935ae-106">5.0 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="935ae-107">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="935ae-107">Old behavior</span></span>

<span data-ttu-id="935ae-108">ASP.NET Core SignalR verwendete das MessagePack 1.x-Paket zum Serialisieren und Deserialisieren von MessagePack-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="935ae-108">ASP.NET Core SignalR used the MessagePack 1.x package to serialize and deserialize MessagePack messages.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="935ae-109">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="935ae-109">New behavior</span></span>

<span data-ttu-id="935ae-110">ASP.NET Core SignalR verwendete das MessagePack 2.x-Paket zum Serialisieren und Deserialisieren von MessagePack-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="935ae-110">ASP.NET Core SignalR uses the MessagePack 2.x package to serialize and deserialize MessagePack messages.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="935ae-111">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="935ae-111">Reason for change</span></span>

<span data-ttu-id="935ae-112">Mit den neuesten Verbesserungen im MessagePack 2.x-Paket wird nützliche Funktionalität hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="935ae-112">The latest improvements in the MessagePack 2.x package add useful functionality.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="935ae-113">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="935ae-113">Recommended action</span></span>

<span data-ttu-id="935ae-114">Dieser Breaking Change gilt in folgenden Fällen:</span><span class="sxs-lookup"><span data-stu-id="935ae-114">This breaking change applies when:</span></span>

* <span data-ttu-id="935ae-115">Sie konfigurieren oder legen Werte für <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions> fest.</span><span class="sxs-lookup"><span data-stu-id="935ae-115">Setting or configuring values on <xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions>.</span></span>
* <span data-ttu-id="935ae-116">Direkte Verwendung der MessagePack-APIs und Verwendung des MessagePack-Hubprotokolls von ASP.NET Core SignalR im selben Projekt.</span><span class="sxs-lookup"><span data-stu-id="935ae-116">Using the MessagePack APIs directly and using the ASP.NET Core SignalR MessagePack Hub Protocol in the same project.</span></span> <span data-ttu-id="935ae-117">Anstelle der vorherigen Version wird die neuere Version geladen.</span><span class="sxs-lookup"><span data-stu-id="935ae-117">The newer version will be loaded instead of the previous version.</span></span>

<span data-ttu-id="935ae-118">Hinweise der Paketautoren zur Migration finden Sie unter [Migrieren von MessagePack v1.x zu MessagePack v2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span><span class="sxs-lookup"><span data-stu-id="935ae-118">For migration guidance from the package authors, see [Migrating from MessagePack v1.x to MessagePack v2.x](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md).</span></span> <span data-ttu-id="935ae-119">Die Änderung wirkt sich auf einige Aspekte der Nachrichtenserialisierung und -deserialisierung aus.</span><span class="sxs-lookup"><span data-stu-id="935ae-119">Some aspects of message serialization and deserialization are affected.</span></span> <span data-ttu-id="935ae-120">Insbesondere kommt es [Verhaltensänderungen in Bezug auf die Serialisierung von DateTime-Werten](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span><span class="sxs-lookup"><span data-stu-id="935ae-120">Specifically, there are [behavioral changes to how DateTime values are serialized](https://github.com/neuecc/MessagePack-CSharp/blob/master/doc/migration.md#behavioral-changes).</span></span>

#### <a name="category"></a><span data-ttu-id="935ae-121">Kategorie</span><span class="sxs-lookup"><span data-stu-id="935ae-121">Category</span></span>

<span data-ttu-id="935ae-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="935ae-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="935ae-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="935ae-123">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions?displayProperty=nameWithType>

<!--

#### Affected APIs

`T:Microsoft.AspNetCore.SignalR.MessagePackHubProtocolOptions`

-->
