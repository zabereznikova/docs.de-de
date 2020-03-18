---
title: Netzwerkkonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Netzwerk für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 622c4afbd36d3d9004edbd9219145fa9e5d326ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74998834"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="ea9e5-103">Laufzeitkonfigurationsoptionen für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="ea9e5-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="ea9e5-104">HTTP/2-Protokoll</span><span class="sxs-lookup"><span data-stu-id="ea9e5-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="ea9e5-105">Konfiguriert, ob der Support für das HTTP/2-Protokoll aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="ea9e5-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>
- <span data-ttu-id="ea9e5-106">Standard: Deaktiviert (`false`)</span><span class="sxs-lookup"><span data-stu-id="ea9e5-106">Default: Disabled (`false`).</span></span>
- <span data-ttu-id="ea9e5-107">Eingeführt in .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="ea9e5-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="ea9e5-108">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="ea9e5-108">Setting name</span></span> | <span data-ttu-id="ea9e5-109">Werte</span><span class="sxs-lookup"><span data-stu-id="ea9e5-109">Values</span></span> |
| - | - |
| <span data-ttu-id="ea9e5-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ea9e5-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="ea9e5-111">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="ea9e5-111">`false` - disabled</span></span><br/><span data-ttu-id="ea9e5-112">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="ea9e5-112">`true` - enabled</span></span> |
| <span data-ttu-id="ea9e5-113">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="ea9e5-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="ea9e5-114">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="ea9e5-114">`0` - disabled</span></span><br/><span data-ttu-id="ea9e5-115">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="ea9e5-115">`1` - enabled</span></span> |

## <a name="sockets-http-handler"></a><span data-ttu-id="ea9e5-116">Socket-HTTP-Handler</span><span class="sxs-lookup"><span data-stu-id="ea9e5-116">Sockets HTTP handler</span></span>

- <span data-ttu-id="ea9e5-117">Konfiguriert, ob allgemeine Netzwerk-APIs, wie z. B. <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> oder die Implementierung von <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> verwenden, die auf [libcurl](https://curl.haxx.se/libcurl/) basiert</span><span class="sxs-lookup"><span data-stu-id="ea9e5-117">Configures whether high-level networking APIs, such as <xref:System.Net.Http.HttpClient>, use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or the implementation of <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> that's based on [libcurl](https://curl.haxx.se/libcurl/).</span></span>
- <span data-ttu-id="ea9e5-118">Standard: Verwenden von <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`)</span><span class="sxs-lookup"><span data-stu-id="ea9e5-118">Default: Use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span></span>
- <span data-ttu-id="ea9e5-119">Sie können diese Einstellung programmgesteuert konfigurieren, indem Sie die <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ea9e5-119">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="ea9e5-120">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="ea9e5-120">Setting name</span></span> | <span data-ttu-id="ea9e5-121">Werte</span><span class="sxs-lookup"><span data-stu-id="ea9e5-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="ea9e5-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="ea9e5-122">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="ea9e5-123">`true` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="ea9e5-123">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="ea9e5-124">`false` – aktiviert die Verwendung von <xref:System.Net.Http.HttpClientHandler></span><span class="sxs-lookup"><span data-stu-id="ea9e5-124">`false` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
| <span data-ttu-id="ea9e5-125">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="ea9e5-125">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="ea9e5-126">`1` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="ea9e5-126">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="ea9e5-127">`0` – aktiviert die Verwendung von <xref:System.Net.Http.HttpClientHandler></span><span class="sxs-lookup"><span data-stu-id="ea9e5-127">`0` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
