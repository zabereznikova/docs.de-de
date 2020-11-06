---
title: Netzwerkkonfigurationseinstellungen
description: Erfahren Sie mehr über Laufzeiteinstellungen, die das Netzwerk für .NET Core-Apps konfigurieren.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bda608e83bb1b093d7d9b860de9607f6734720aa
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188301"
---
# <a name="run-time-configuration-options-for-networking"></a><span data-ttu-id="26a10-103">Laufzeitkonfigurationsoptionen für Netzwerke</span><span class="sxs-lookup"><span data-stu-id="26a10-103">Run-time configuration options for networking</span></span>

## <a name="http2-protocol"></a><span data-ttu-id="26a10-104">HTTP/2-Protokoll</span><span class="sxs-lookup"><span data-stu-id="26a10-104">HTTP/2 protocol</span></span>

- <span data-ttu-id="26a10-105">Konfiguriert, ob der Support für das HTTP/2-Protokoll aktiviert ist</span><span class="sxs-lookup"><span data-stu-id="26a10-105">Configures whether support for the HTTP/2 protocol is enabled.</span></span>

- <span data-ttu-id="26a10-106">Eingeführt in .NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="26a10-106">Introduced in .NET Core 3.0.</span></span>

- <span data-ttu-id="26a10-107">Nur .NET Core 3.0: Wenn Sie diese Einstellung weglassen, ist die Unterstützung für das HTTP/2-Protokoll deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="26a10-107">.NET Core 3.0 only: If you omit this setting, support for the HTTP/2 protocol is disabled.</span></span> <span data-ttu-id="26a10-108">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="26a10-108">This is equivalent to setting the value to `false`.</span></span>

- <span data-ttu-id="26a10-109">.NET Core 3.1 und .NET 5 und höher: Wenn Sie diese Einstellung weglassen, ist die Unterstützung für das HTTP/2-Protokoll aktiviert.</span><span class="sxs-lookup"><span data-stu-id="26a10-109">.NET Core 3.1 and .NET 5+: If you omit this setting, support for the HTTP/2 protocol is enabled.</span></span> <span data-ttu-id="26a10-110">Dies entspricht der Einstellung des Werts auf `true`.</span><span class="sxs-lookup"><span data-stu-id="26a10-110">This is equivalent to setting the value to `true`.</span></span>

| | <span data-ttu-id="26a10-111">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="26a10-111">Setting name</span></span> | <span data-ttu-id="26a10-112">Werte</span><span class="sxs-lookup"><span data-stu-id="26a10-112">Values</span></span> |
| - | - | - |
| <span data-ttu-id="26a10-113">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="26a10-113">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.Http2Support` | <span data-ttu-id="26a10-114">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="26a10-114">`false` - disabled</span></span><br/><span data-ttu-id="26a10-115">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="26a10-115">`true` - enabled</span></span> |
| <span data-ttu-id="26a10-116">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="26a10-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2SUPPORT` | <span data-ttu-id="26a10-117">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="26a10-117">`0` - disabled</span></span><br/><span data-ttu-id="26a10-118">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="26a10-118">`1` - enabled</span></span> |

## <a name="usesocketshttphandler"></a><span data-ttu-id="26a10-119">UseSocketsHttpHandler</span><span class="sxs-lookup"><span data-stu-id="26a10-119">UseSocketsHttpHandler</span></span>

- <span data-ttu-id="26a10-120">Mit dieser Einstellung wird konfiguriert, ob <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> die <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType>-Klasse oder ältere HTTP-Protokollstapel verwendet (<xref:System.Net.Http.WinHttpHandler> unter Windows und `CurlHandler`, eine interne auf Grundlage von [libcurl](https://curl.haxx.se/libcurl/) implementierte Klasse, unter Linux).</span><span class="sxs-lookup"><span data-stu-id="26a10-120">Configures whether <xref:System.Net.Http.HttpClientHandler?displayProperty=nameWithType> uses <xref:System.Net.Http.SocketsHttpHandler?displayProperty=nameWithType> or older HTTP protocol stacks (<xref:System.Net.Http.WinHttpHandler> on Windows and `CurlHandler`, an internal class implemented on top of [libcurl](https://curl.haxx.se/libcurl/), on Linux).</span></span>

  > [!NOTE]
  > <span data-ttu-id="26a10-121">Möglicherweise verwenden Sie allgemeine Netzwerk-APIs, anstatt die <xref:System.Net.Http.HttpClientHandler>-Klasse direkt zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="26a10-121">You may be using high-level networking APIs instead of directly instantiating the <xref:System.Net.Http.HttpClientHandler> class.</span></span> <span data-ttu-id="26a10-122">Diese Einstellung wirkt sich auch darauf aus, welcher HTTP-Protokollstapel von allgemeinen Netzwerk-APIs verwendet wird, einschließlich <xref:System.Net.Http.HttpClient> und [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span><span class="sxs-lookup"><span data-stu-id="26a10-122">This setting also affects which HTTP protocol stack is used by high-level networking APIs, including <xref:System.Net.Http.HttpClient> and [HttpClientFactory](/previous-versions/aspnet/hh995280(v=vs.118)).</span></span>

- <span data-ttu-id="26a10-123">Wenn Sie diese Einstellung weglassen, verwendet <xref:System.Net.Http.HttpClientHandler> <xref:System.Net.Http.SocketsHttpHandler>.</span><span class="sxs-lookup"><span data-stu-id="26a10-123">If you omit this setting, <xref:System.Net.Http.HttpClientHandler> uses <xref:System.Net.Http.SocketsHttpHandler>.</span></span> <span data-ttu-id="26a10-124">Dies entspricht der Einstellung des Werts auf `true`.</span><span class="sxs-lookup"><span data-stu-id="26a10-124">This is equivalent to setting the value to `true`.</span></span>

- <span data-ttu-id="26a10-125">Sie können diese Einstellung programmgesteuert konfigurieren, indem Sie die <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="26a10-125">You can configure this setting programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

| | <span data-ttu-id="26a10-126">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="26a10-126">Setting name</span></span> | <span data-ttu-id="26a10-127">Werte</span><span class="sxs-lookup"><span data-stu-id="26a10-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="26a10-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="26a10-128">**runtimeconfig.json**</span></span> | `System.Net.Http.UseSocketsHttpHandler` | <span data-ttu-id="26a10-129">`true` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="26a10-129">`true` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="26a10-130">`false`: ermöglicht die Verwendung von <xref:System.Net.Http.WinHttpHandler> unter Windows oder [libcurl](https://curl.haxx.se/libcurl/) unter Linux</span><span class="sxs-lookup"><span data-stu-id="26a10-130">`false` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |
| <span data-ttu-id="26a10-131">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="26a10-131">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_USESOCKETSHTTPHANDLER` | <span data-ttu-id="26a10-132">`1` – aktiviert die Verwendung von <xref:System.Net.Http.SocketsHttpHandler></span><span class="sxs-lookup"><span data-stu-id="26a10-132">`1` - enables the use of <xref:System.Net.Http.SocketsHttpHandler></span></span><br/><span data-ttu-id="26a10-133">`0`: ermöglicht die Verwendung von <xref:System.Net.Http.WinHttpHandler> unter Windows oder [libcurl](https://curl.haxx.se/libcurl/) unter Linux</span><span class="sxs-lookup"><span data-stu-id="26a10-133">`0` - enables the use of <xref:System.Net.Http.WinHttpHandler> on Windows or [libcurl](https://curl.haxx.se/libcurl/) on Linux</span></span> |

> [!NOTE]
> <span data-ttu-id="26a10-134">Ab .NET 5 ist die Einstellung `System.Net.Http.UseSocketsHttpHandler` nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="26a10-134">Starting in .NET 5, the `System.Net.Http.UseSocketsHttpHandler` setting is no longer available.</span></span>

## <a name="latin1-headers-net-core-31-only"></a><span data-ttu-id="26a10-135">Latin1-Header (nur .NET Core 3.1)</span><span class="sxs-lookup"><span data-stu-id="26a10-135">Latin1 headers (.NET Core 3.1 only)</span></span>

- <span data-ttu-id="26a10-136">Durch diese Umstellung kann die Überprüfung des HTTP-Headers gelockert werden, wodurch <xref:System.Net.Http.SocketsHttpHandler> ISO-8859-1-codierte (Latin-1-codierte) Zeichen in Headern senden kann.</span><span class="sxs-lookup"><span data-stu-id="26a10-136">This switch allows relaxing the HTTP header validation, enabling <xref:System.Net.Http.SocketsHttpHandler> to send ISO-8859-1 (Latin-1) encoded characters in headers.</span></span>

- <span data-ttu-id="26a10-137">Wenn Sie diese Einstellung weglassen, wird beim Versuch, ein Nicht-ASCII-Zeichen zu senden, <xref:System.Net.Http.HttpRequestException> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="26a10-137">If you omit this setting, an attempt to send a non-ASCII character will result in <xref:System.Net.Http.HttpRequestException>.</span></span> <span data-ttu-id="26a10-138">Dies entspricht der Einstellung des Werts auf `false`.</span><span class="sxs-lookup"><span data-stu-id="26a10-138">This is equivalent to setting the value to `false`.</span></span>

| | <span data-ttu-id="26a10-139">Einstellungsname</span><span class="sxs-lookup"><span data-stu-id="26a10-139">Setting name</span></span> | <span data-ttu-id="26a10-140">Werte</span><span class="sxs-lookup"><span data-stu-id="26a10-140">Values</span></span> |
| - | - | - |
| <span data-ttu-id="26a10-141">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="26a10-141">**runtimeconfig.json**</span></span> | `System.Net.Http.SocketsHttpHandler.AllowLatin1Headers` | <span data-ttu-id="26a10-142">`false` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="26a10-142">`false` - disabled</span></span><br/><span data-ttu-id="26a10-143">`true` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="26a10-143">`true` - enabled</span></span> |
| <span data-ttu-id="26a10-144">**Umgebungsvariable**</span><span class="sxs-lookup"><span data-stu-id="26a10-144">**Environment variable**</span></span> | `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_ALLOWLATIN1HEADERS` | <span data-ttu-id="26a10-145">`0` – deaktiviert</span><span class="sxs-lookup"><span data-stu-id="26a10-145">`0` - disabled</span></span><br/><span data-ttu-id="26a10-146">`1` – aktiviert</span><span class="sxs-lookup"><span data-stu-id="26a10-146">`1` - enabled</span></span> |

> [!NOTE]
> <span data-ttu-id="26a10-147">Diese Option ist nur in .NET Core 3.1 ab Version 3.1.9 und nicht in früheren oder neueren Versionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="26a10-147">This option is only available in .NET Core 3.1 since version 3.1.9, and not in previous or later versions.</span></span> <span data-ttu-id="26a10-148">Bei .NET 5 empfiehlt sich die Verwendung von <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector>.</span><span class="sxs-lookup"><span data-stu-id="26a10-148">In .NET 5 we recommend using <xref:System.Net.Http.SocketsHttpHandler.RequestHeaderEncodingSelector>.</span></span>
