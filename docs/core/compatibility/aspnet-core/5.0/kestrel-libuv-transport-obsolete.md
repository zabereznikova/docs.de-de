---
title: 'Breaking Change: Kestrel: Markierung von Libuv-Transport als veraltet'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Kestrel: Markierung von Libuv-Transport als veraltet'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: f66b9b646671e07957e6d30a95333d392eb29617
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759466"
---
# <a name="kestrel-libuv-transport-marked-as-obsolete"></a><span data-ttu-id="408c8-103">Kestrel: Markierung von libuv-Transport als veraltet</span><span class="sxs-lookup"><span data-stu-id="408c8-103">Kestrel: Libuv transport marked as obsolete</span></span>

<span data-ttu-id="408c8-104">Frühere Versionen von ASP.NET Core haben Libuv als Implementierungsdetail für die Ausführung der asynchronen Ein- und Ausgabe verwendet.</span><span class="sxs-lookup"><span data-stu-id="408c8-104">Earlier versions of ASP.NET Core used Libuv as an implementation detail of how asynchronous input and output was performed.</span></span> <span data-ttu-id="408c8-105">In ASP.NET Core 2.0 wurde ein alternativer <xref:System.Net.Sockets.Socket>-basierter Transport entwickelt.</span><span class="sxs-lookup"><span data-stu-id="408c8-105">In ASP.NET Core 2.0, an alternative, <xref:System.Net.Sockets.Socket>-based transport was developed.</span></span> <span data-ttu-id="408c8-106">In ASP.NET Core 2.1 wurde Kestrel standardmäßig auf die Verwendung des `Socket`-basierten Transports umgestellt.</span><span class="sxs-lookup"><span data-stu-id="408c8-106">In ASP.NET Core 2.1, Kestrel switched to using the `Socket`-based transport by default.</span></span> <span data-ttu-id="408c8-107">Die Unterstützung von Libuv wurde aus Kompatibilitätsgründen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="408c8-107">Libuv support was maintained for compatibility reasons.</span></span>

<span data-ttu-id="408c8-108">Heute ist die Verwendung des `Socket`-basierten Transports weitaus häufiger als des Libuv-Transports.</span><span class="sxs-lookup"><span data-stu-id="408c8-108">At this point, use of the `Socket`-based transport is far more common than the Libuv transport.</span></span> <span data-ttu-id="408c8-109">Folglich ist die Libuv-Unterstützung in .NET 5.0 als veraltet markiert und wird in .NET 6.0 vollständig entfernt.</span><span class="sxs-lookup"><span data-stu-id="408c8-109">Consequently, Libuv support is marked as obsolete in .NET 5.0 and will be removed entirely in .NET 6.0.</span></span>

<span data-ttu-id="408c8-110">Im Rahmen dieser Änderung wird die Libuv-Unterstützung für neue Betriebssystemplattformen (wie Windows ARM64) nicht im .NET 5.0-Zeitrahmen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="408c8-110">As part of this change, Libuv support for new operating system platforms (like Windows ARM64) won't be added in the .NET 5.0 timeframe.</span></span>

<span data-ttu-id="408c8-111">Informationen zu Blockierungsproblemen, die die Verwendung des Libuv-Transports erfordern, finden Sie im GitHub Issue unter [dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409).</span><span class="sxs-lookup"><span data-stu-id="408c8-111">For discussion on blocking issues that require the use of the Libuv transport, see the GitHub issue at [dotnet/aspnetcore#23409](https://github.com/dotnet/aspnetcore/issues/23409).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="408c8-112">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="408c8-112">Version introduced</span></span>

<span data-ttu-id="408c8-113">5.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="408c8-113">5.0 Preview 8</span></span>

## <a name="old-behavior"></a><span data-ttu-id="408c8-114">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="408c8-114">Old behavior</span></span>

<span data-ttu-id="408c8-115">Die Libuv-APIs sind nicht als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="408c8-115">The Libuv APIs aren't marked as obsolete.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="408c8-116">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="408c8-116">New behavior</span></span>

<span data-ttu-id="408c8-117">Die Libuv-APIs sind als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="408c8-117">The Libuv APIs are marked as obsolete.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="408c8-118">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="408c8-118">Reason for change</span></span>

<span data-ttu-id="408c8-119">Der `Socket`-basierte Transport ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="408c8-119">The `Socket`-based transport is the default.</span></span> <span data-ttu-id="408c8-120">Es gibt keine überzeugenden Gründe, den Libuv-Transport weiterhin zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="408c8-120">There aren't any compelling reasons to continue using the Libuv transport.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="408c8-121">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="408c8-121">Recommended action</span></span>

<span data-ttu-id="408c8-122">Beenden Sie die Verwendung des [Libuv-Pakets](https://www.nuget.org/packages/Libuv) und der Erweiterungsmethoden.</span><span class="sxs-lookup"><span data-stu-id="408c8-122">Discontinue use of the [Libuv package](https://www.nuget.org/packages/Libuv) and extension methods.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="408c8-123">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="408c8-123">Affected APIs</span></span>

- [<span data-ttu-id="408c8-124">WebHostBuilderLibuvExtensions</span><span class="sxs-lookup"><span data-stu-id="408c8-124">WebHostBuilderLibuvExtensions</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions?view=aspnetcore-3.0)
- [<span data-ttu-id="408c8-125">WebHostBuilderLibuvExtensions.UseLibuv</span><span class="sxs-lookup"><span data-stu-id="408c8-125">WebHostBuilderLibuvExtensions.UseLibuv</span></span>](/dotnet/api/microsoft.aspnetcore.hosting.webhostbuilderlibuvextensions.uselibuv?view=aspnetcore-3.0)
- [<span data-ttu-id="408c8-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span><span class="sxs-lookup"><span data-stu-id="408c8-126">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions?view=aspnetcore-3.0)
- [<span data-ttu-id="408c8-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span><span class="sxs-lookup"><span data-stu-id="408c8-127">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.threadcount?view=aspnetcore-3.0)
- [<span data-ttu-id="408c8-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span><span class="sxs-lookup"><span data-stu-id="408c8-128">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.nodelay?view=aspnetcore-3.0)
- [<span data-ttu-id="408c8-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span><span class="sxs-lookup"><span data-stu-id="408c8-129">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxwritebuffersize?view=aspnetcore-3.0)
- [<span data-ttu-id="408c8-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span><span class="sxs-lookup"><span data-stu-id="408c8-130">Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize</span></span>](/dotnet/api/microsoft.aspnetcore.server.kestrel.transport.libuv.libuvtransportoptions.maxreadbuffersize?view=aspnetcore-3.0)
- `Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions`
- `Overload:Microsoft.AspNetCore.Hosting.WebHostBuilderLibuvExtensions.UseLibuv`
- `T:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.ThreadCount`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.NoDelay`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxWriteBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.MaxReadBufferSize`
- `P:Microsoft.AspNetCore.Server.Kestrel.Transport.Libuv.LibuvTransportOptions.Backlog`

-->
