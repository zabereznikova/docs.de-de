---
title: 'Breaking Change: Entfernung von WinHttpHandler aus der .NET-Runtime'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den WinHttpHandler aus der .NET-Runtime entfernt wurde.
ms.date: 10/18/2020
ms.openlocfilehash: f8b9910ade8d459133791a23704d624a91cc5dff
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759382"
---
# <a name="winhttphandler-removed-from-net-runtime"></a><span data-ttu-id="53f40-103">Entfernung von WinHttpHandler aus der .NET-Runtime</span><span class="sxs-lookup"><span data-stu-id="53f40-103">WinHttpHandler removed from .NET runtime</span></span>

<span data-ttu-id="53f40-104">Die `WinHttpHandler`-Klasse wurde aus der Assembly *System.Net.Http.dll* entfernt.</span><span class="sxs-lookup"><span data-stu-id="53f40-104">The `WinHttpHandler` class was removed from the *System.Net.Http.dll* assembly.</span></span> <span data-ttu-id="53f40-105">Sie ist jetzt nur als [OOB-NuGet-Paket](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) (Out-of-Band) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="53f40-105">It's now available only as an out-of-band (OOB) [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="53f40-106">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="53f40-106">Version introduced</span></span>

<span data-ttu-id="53f40-107">5.0</span><span class="sxs-lookup"><span data-stu-id="53f40-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="53f40-108">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="53f40-108">Change description</span></span>

<span data-ttu-id="53f40-109">In früheren .NET-Versionen ist die <xref:System.Net.Http.WinHttpHandler>-Klasse als Teil der .NET-Kernbibliotheken verfügbar.</span><span class="sxs-lookup"><span data-stu-id="53f40-109">In previous .NET versions, the <xref:System.Net.Http.WinHttpHandler> class is available as part of the core .NET libraries.</span></span> <span data-ttu-id="53f40-110">Ab .NET 5.0 ist die <xref:System.Net.Http.WinHttpHandler>-Klasse nur als separat installiertes [NuGet-Paket](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="53f40-110">Starting in .NET 5.0, the <xref:System.Net.Http.WinHttpHandler> class is only available as a separately installed [NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span>

## <a name="recommended-action"></a><span data-ttu-id="53f40-111">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="53f40-111">Recommended action</span></span>

<span data-ttu-id="53f40-112">Installieren Sie das [NuGet-Paket „System.Net.Http.WinHttpHandler“](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span><span class="sxs-lookup"><span data-stu-id="53f40-112">Install the [System.Net.Http.WinHttpHandler NuGet package](https://www.nuget.org/packages/System.Net.Http.WinHttpHandler/).</span></span> <span data-ttu-id="53f40-113">Wenn Sie keine WinHTTP-spezifischen Features benötigen, können Sie stattdessen <xref:System.Net.Http.SocketsHttpHandler> verwenden.</span><span class="sxs-lookup"><span data-stu-id="53f40-113">Or, if you don't require WinHTTP-specific features, use <xref:System.Net.Http.SocketsHttpHandler> instead.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="53f40-114">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="53f40-114">Affected APIs</span></span>

- <xref:System.Net.Http.WinHttpHandler?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Net.Http.WinHttpHandler`

### Category

Networking

-->
