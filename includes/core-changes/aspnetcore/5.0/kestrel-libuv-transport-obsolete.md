---
ms.openlocfilehash: 203d75f5858c8ff039cf579c0539efda0c5c9f02
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474376"
---
### <a name="kestrel-libuv-transport-marked-as-obsolete"></a><span data-ttu-id="aebc9-101">Kestrel: Markierung von libuv-Transport als veraltet</span><span class="sxs-lookup"><span data-stu-id="aebc9-101">Kestrel: Libuv transport marked as obsolete</span></span>

<span data-ttu-id="aebc9-102">Frühere Versionen von ASP.NET Core haben Libuv als Implementierungsdetail für die Ausführung der asynchronen Ein- und Ausgabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="aebc9-102">Earlier versions of ASP.NET Core used Libuv as an implementation detail of how asynchronous input and output was performed.</span></span> <span data-ttu-id="aebc9-103">In ASP.NET Core 2.0 wurde ein alternativer <xref:System.Net.Sockets.Socket>-basierter Transport entwickelt.</span><span class="sxs-lookup"><span data-stu-id="aebc9-103">In ASP.NET Core 2.0, an alternative, <xref:System.Net.Sockets.Socket>-based transport was developed.</span></span> <span data-ttu-id="aebc9-104">In ASP.NET Core 2.1 wurde Kestrel standardmäßig auf die Verwendung des `Socket`-basierten Transports umgestellt.</span><span class="sxs-lookup"><span data-stu-id="aebc9-104">In ASP.NET Core 2.1, Kestrel switched to using the `Socket`-based transport by default.</span></span> <span data-ttu-id="aebc9-105">Die Unterstützung von Libuv wurde aus Kompatibilitätsgründen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="aebc9-105">Libuv support was maintained for compatibility reasons.</span></span>

<span data-ttu-id="aebc9-106">Heute ist die Verwendung des `Socket`-basierten Transports weitaus häufiger als des Libuv-Transports.</span><span class="sxs-lookup"><span data-stu-id="aebc9-106">At this point, use of the `Socket`-based transport is far more common than the Libuv transport.</span></span> <span data-ttu-id="aebc9-107">Folglich ist die Libuv-Unterstützung in .NET 5.0 als veraltet markiert und wird in .NET 6.0 vollständig entfernt.</span><span class="sxs-lookup"><span data-stu-id="aebc9-107">Consequently, Libuv support is marked as obsolete in .NET 5.0 and will be removed entirely in .NET 6.0.</span></span>

<span data-ttu-id="aebc9-108">Im Rahmen dieser Änderung wird die Libuv-Unterstützung für neue Betriebssystemplattformen (wie Windows ARM64) nicht im .NET 5.0-Zeitrahmen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="aebc9-108">As part of this change, Libuv support for new operating system platforms (like Windows ARM64) won't be added in the .NET 5.0 timeframe.</span></span>

<span data-ttu-id="aebc9-109">Informationen zu Blockierungsproblemen, die die Verwendung des Libuv-Transports erfordern, finden Sie im GitHub Issue unter [dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409).</span><span class="sxs-lookup"><span data-stu-id="aebc9-109">For discussion on blocking issues that require the use of the Libuv transport, see the GitHub issue at [dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="aebc9-110">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="aebc9-110">Version introduced</span></span>

<span data-ttu-id="aebc9-111">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="aebc9-111">5.0 Preview 8</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="aebc9-112">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="aebc9-112">Old behavior</span></span>

<span data-ttu-id="aebc9-113">Die Libuv-APIs sind nicht als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="aebc9-113">The Libuv APIs aren't marked as obsolete.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="aebc9-114">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="aebc9-114">New behavior</span></span>

<span data-ttu-id="aebc9-115">Die Libuv-APIs sind als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="aebc9-115">The Libuv APIs are marked as obsolete.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="aebc9-116">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="aebc9-116">Reason for change</span></span>

<span data-ttu-id="aebc9-117">Der `Socket`-basierte Transport ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="aebc9-117">The `Socket`-based transport is the default.</span></span> <span data-ttu-id="aebc9-118">Es gibt keine überzeugenden Gründe, den Libuv-Transport weiterhin zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="aebc9-118">There aren't any compelling reasons to continue using the Libuv transport.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="aebc9-119">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="aebc9-119">Recommended action</span></span>

<span data-ttu-id="aebc9-120">Beenden Sie die Verwendung des [Libuv-Pakets](https://www.nuget.org/packages/Libuv) und der Erweiterungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="aebc9-120">Discontinue use of the [Libuv package](https://www.nuget.org/packages/Libuv) and extension methods.</span></span>

#### <a name="category"></a><span data-ttu-id="aebc9-121">Kategorie</span><span class="sxs-lookup"><span data-stu-id="aebc9-121">Category</span></span>

<span data-ttu-id="aebc9-122">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="aebc9-122">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="aebc9-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="aebc9-123">Affected APIs</span></span>

- [<span data-ttu-id="aebc9-124">WebHostBuilderLibuvExtensions</span><span class="sxs-lookup"><span data-stu-id="aebc9-124">WebHostBuilderLibuvExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions?view=aspnetcore-3.0)
- [<span data-ttu-id="aebc9-125">WebHostBuilderLibuvExtensions.UseLibuv</span><span class="sxs-lookup"><span data-stu-id="aebc9-125">WebHostBuilderLibuvExtensions.UseLibuv</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions.uselibuv?view=aspnetcore-3.0)
- [<span data-ttu-id="aebc9-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span><span class="sxs-lookup"><span data-stu-id="aebc9-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions?view=aspnetcore-3.0)
- [<span data-ttu-id="aebc9-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span><span class="sxs-lookup"><span data-stu-id="aebc9-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.threadcount?view=aspnetcore-3.0)
- [<span data-ttu-id="aebc9-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span><span class="sxs-lookup"><span data-stu-id="aebc9-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.nodelay?view=aspnetcore-3.0)
- [<span data-ttu-id="aebc9-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span><span class="sxs-lookup"><span data-stu-id="aebc9-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxwritebuffersize?view=aspnetcore-3.0)
- [<span data-ttu-id="aebc9-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span><span class="sxs-lookup"><span data-stu-id="aebc9-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxreadbuffersize?view=aspnetcore-3.0)
- `Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

<!-- 

#### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions`
- `Overload:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions.UseLibuv`
- `T:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

-->
