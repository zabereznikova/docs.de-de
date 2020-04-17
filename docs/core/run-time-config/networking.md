---
title: Netzwerkkonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Netzwerk für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 8d02087ad7260cc78c096090bf3b06a716d34678
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989102"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="7b69e-103">Laufzeitkonfigurationsoptionen für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="7b69e-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="7b69e-104">HTTP/2-Protokoll</span><span class="sxs-lookup"><span data-stu-id="7b69e-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="7b69e-105">Konfiguriert, ob der Support für das HTTP/2-Protokoll aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="7b69e-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="7b69e-106">Standard: Deaktiviert (`false`)</span><span class="sxs-lookup"><span data-stu-id="7b69e-106">Default: Disabled (`false`).</span></span>

- <span data-ttu-id="7b69e-107">Eingeführt in .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7b69e-107">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="7b69e-108">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="7b69e-108">Setting name</span></span> | <span data-ttu-id="7b69e-109">Werte</span><span class="sxs-lookup"><span data-stu-id="7b69e-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="7b69e-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="7b69e-110">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="7b69e-111">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="7b69e-111">`false` - disabled</span></span><br/><span data-ttu-id="7b69e-112">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="7b69e-112">`true` - enabled</span></span> |
| <span data-ttu-id="7b69e-113">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="7b69e-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="7b69e-114">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="7b69e-114">`0` - disabled</span></span><br/><span data-ttu-id="7b69e-115">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="7b69e-115">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="7b69e-116">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="7b69e-116">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="7b69e-117">Mit dieser Einstellung wird konfiguriert, ob <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> die <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>-Klasse oder ältere HTTP-Protokollstapel verwendet (<xref:System.Net.Http.WinHttpHandler> unter Windows und `CurlHandler`, eine interne auf Grundlage von [libcurl](https://curl.haxx.se/libcurl/) implementierte Klasse, unter Linux).</span><span class="sxs-lookup"><span data-stu-id="7b69e-117">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="7b69e-118">Möglicherweise verwenden Sie allgemeine Netzwerk-APIs, anstatt die <xref:System.Net.Http.HttpClientHandler>-Klasse direkt zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="7b69e-118">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="7b69e-119">Diese Einstellung wirkt sich auch darauf aus, welcher HTTP-Protokollstapel von allgemeinen Netzwerk-APIs verwendet wird, einschließlich <xref:System.Net.Http.HttpClient> und [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span><span class="sxs-lookup"><span data-stu-id="7b69e-119">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](https://docs.microsoft.com/previous-versions/aspnet/hh995280(v%3dvs.118)).</span></span>

- <span data-ttu-id="7b69e-120">Standard: Verwenden von <xref:System.Net.Http.SocketsHttpHandler> (`true`)</span><span class="sxs-lookup"><span data-stu-id="7b69e-120">Default: Use <xref:System.Net.Http.SocketsHttpHandler> (`true`).</span></span>

- <span data-ttu-id="7b69e-121">Sie können diese Einstellung programmgesteuert konfigurieren, indem Sie die <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="7b69e-121">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="7b69e-122">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="7b69e-122">Setting name</span></span> | <span data-ttu-id="7b69e-123">Werte</span><span class="sxs-lookup"><span data-stu-id="7b69e-123">Values</span></span> |
| - | - | - |
| <span data-ttu-id="7b69e-124">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="7b69e-124">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="7b69e-125">`true` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="7b69e-125">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="7b69e-126">`false`: ermöglicht die Verwendung von <xref:System.Net.Http.WinHttpHandler> unter Windows oder [libcurl](https://curl.haxx.se/libcurl/) unter Linux</span><span class="sxs-lookup"><span data-stu-id="7b69e-126">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="7b69e-127">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="7b69e-127">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="7b69e-128">`1` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="7b69e-128">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="7b69e-129">`0`: ermöglicht die Verwendung von <xref:System.Net.Http.WinHttpHandler> unter Windows oder [libcurl](https://curl.haxx.se/libcurl/) unter Linux</span><span class="sxs-lookup"><span data-stu-id="7b69e-129">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="7b69e-130">Ab .NET 5 ist die Einstellung `System.Net.Http.UseSocketsHttpHandler` nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7b69e-130">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
