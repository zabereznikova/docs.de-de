---
title: Netzwerkkonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Netzwerk für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: f5ea47f0444a911dc2347a66817cabf585fd8e70
ms.sourcegitcommit: 1c1a1f9ec0bd1efb3040d86a79f7ee94e207cca5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/03/2020
ms.locfileid: "80635429"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="73f4f-103">Laufzeitkonfigurationsoptionen für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="73f4f-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="73f4f-104">HTTP/2-Protokoll</span><span class="sxs-lookup"><span data-stu-id="73f4f-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="73f4f-105">Konfiguriert, ob der Support für das HTTP/2-Protokoll aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="73f4f-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>
- <span data-ttu-id="73f4f-106">Standard: Deaktiviert (`false`)</span><span class="sxs-lookup"><span data-stu-id="73f4f-106">Default: Disabled (`false`).</span></span>
- <span data-ttu-id="73f4f-107">Eingeführt in .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="73f4f-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="73f4f-108">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="73f4f-108">Setting name</span></span> | <span data-ttu-id="73f4f-109">Werte</span><span class="sxs-lookup"><span data-stu-id="73f4f-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="73f4f-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="73f4f-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="73f4f-111">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="73f4f-111">`false` - disabled</span></span><br/><span data-ttu-id="73f4f-112">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="73f4f-112">`true` - enabled</span></span> |
| <span data-ttu-id="73f4f-113">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="73f4f-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="73f4f-114">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="73f4f-114">`0` - disabled</span></span><br/><span data-ttu-id="73f4f-115">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="73f4f-115">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="73f4f-116">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="73f4f-116">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="73f4f-117">Konfiguriert, ob allgemeine Netzwerk-APIs, wie z. B. <xref:System.Net.Http.HttpClient>, <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> oder die Implementierung von <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> verwenden, die auf [libcurl](https://curl.haxx.se/libcurl/) basiert</span><span class="sxs-lookup"><span data-stu-id="73f4f-117">Configures whether high-level networking APIs, such as <xref:System.Net.Http.HttpClient>, use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or the implementation of <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> that's based on [libcurl](https://curl.haxx.se/libcurl/).</span></span>
- <span data-ttu-id="73f4f-118">Standard: Verwenden von <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`)</span><span class="sxs-lookup"><span data-stu-id="73f4f-118">Default: Use <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> (`true`).</span></span>
- <span data-ttu-id="73f4f-119">Sie können diese Einstellung programmgesteuert konfigurieren, indem Sie die <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="73f4f-119">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="73f4f-120">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="73f4f-120">Setting name</span></span> | <span data-ttu-id="73f4f-121">Werte</span><span class="sxs-lookup"><span data-stu-id="73f4f-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="73f4f-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="73f4f-122">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="73f4f-123">`true` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="73f4f-123">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="73f4f-124">`false` – aktiviert die Verwendung von <xref:System.Net.Http.HttpClientHandler></span><span class="sxs-lookup"><span data-stu-id="73f4f-124">`false` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |
| <span data-ttu-id="73f4f-125">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="73f4f-125">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="73f4f-126">`1` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="73f4f-126">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="73f4f-127">`0` – aktiviert die Verwendung von <xref:System.Net.Http.HttpClientHandler></span><span class="sxs-lookup"><span data-stu-id="73f4f-127">`0` - enables the use of <xref:System.Net.Http.HttpClientHandler></span></span> |

> [!NOTE]
> <span data-ttu-id="73f4f-128">Ab .NET 5 ist die Einstellung `System.Net.Http.UseSocketsHttpHandler` nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="73f4f-128">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
