---
title: Netzwerkkonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Netzwerk für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: d43b68206cc82f4a41df02bd5998702b4f5d0590
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538132"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="72d94-103">Laufzeitkonfigurationsoptionen für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="72d94-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="72d94-104">HTTP/2-Protokoll</span><span class="sxs-lookup"><span data-stu-id="72d94-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="72d94-105">Konfiguriert, ob der Support für das HTTP/2-Protokoll aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="72d94-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="72d94-106">Wenn Sie diese Einstellung weglassen, ist die Unterstützung für das HTTP/2-Protokoll deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="72d94-106">If you omit this setting, support for the HTTP/2 protocol is disabled.</span></span> <span data-ttu-id="72d94-107">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="72d94-107">This is equivalent to setting the value to `false`.</span></span>

- <span data-ttu-id="72d94-108">Eingeführt in .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="72d94-108">Introduced in .NET Core 3.0.</span></span>

| | <span data-ttu-id="72d94-109">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72d94-109">Setting name</span></span> | <span data-ttu-id="72d94-110">Werte</span><span class="sxs-lookup"><span data-stu-id="72d94-110">Values</span></span> |
| - | - | - |
| <span data-ttu-id="72d94-111">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72d94-111">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="72d94-112">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="72d94-112">`false` - disabled</span></span><br/><span data-ttu-id="72d94-113">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="72d94-113">`true` - enabled</span></span> |
| <span data-ttu-id="72d94-114">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72d94-114">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="72d94-115">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="72d94-115">`0` - disabled</span></span><br/><span data-ttu-id="72d94-116">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="72d94-116">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="72d94-117">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="72d94-117">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="72d94-118">Mit dieser Einstellung wird konfiguriert, ob <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> die <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>-Klasse oder ältere HTTP-Protokollstapel verwendet (<xref:System.Net.Http.WinHttpHandler> unter Windows und `CurlHandler`, eine interne auf Grundlage von [libcurl](https://curl.haxx.se/libcurl/) implementierte Klasse, unter Linux).</span><span class="sxs-lookup"><span data-stu-id="72d94-118">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="72d94-119">Möglicherweise verwenden Sie allgemeine Netzwerk-APIs, anstatt die <xref:System.Net.Http.HttpClientHandler>-Klasse direkt zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="72d94-119">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="72d94-120">Diese Einstellung wirkt sich auch darauf aus, welcher HTTP-Protokollstapel von allgemeinen Netzwerk-APIs verwendet wird, einschließlich <xref:System.Net.Http.HttpClient> und [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span><span class="sxs-lookup"><span data-stu-id="72d94-120">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span></span>

- <span data-ttu-id="72d94-121">Wenn Sie diese Einstellung weglassen, verwendet <xref:System.Net.Http.HttpClientHandler> <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="72d94-121">If you omit this setting, <xref:System.Net.Http.HttpClientHandler> uses <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="72d94-122">Dies entspricht der Einstellung des Werts auf `true`.</span><span class="sxs-lookup"><span data-stu-id="72d94-122">This is equivalent to setting the value to `true`.</span></span>

- <span data-ttu-id="72d94-123">Sie können diese Einstellung programmgesteuert konfigurieren, indem Sie die <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="72d94-123">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="72d94-124">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="72d94-124">Setting name</span></span> | <span data-ttu-id="72d94-125">Werte</span><span class="sxs-lookup"><span data-stu-id="72d94-125">Values</span></span> |
| - | - | - |
| <span data-ttu-id="72d94-126">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="72d94-126">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="72d94-127">`true` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="72d94-127">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="72d94-128">`false`: ermöglicht die Verwendung von <xref:System.Net.Http.WinHttpHandler> unter Windows oder [libcurl](https://curl.haxx.se/libcurl/) unter Linux</span><span class="sxs-lookup"><span data-stu-id="72d94-128">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="72d94-129">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="72d94-129">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="72d94-130">`1` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="72d94-130">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="72d94-131">`0`: ermöglicht die Verwendung von <xref:System.Net.Http.WinHttpHandler> unter Windows oder [libcurl](https://curl.haxx.se/libcurl/) unter Linux</span><span class="sxs-lookup"><span data-stu-id="72d94-131">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="72d94-132">Ab .NET 5 ist die Einstellung `System.Net.Http.UseSocketsHttpHandler` nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="72d94-132">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>
