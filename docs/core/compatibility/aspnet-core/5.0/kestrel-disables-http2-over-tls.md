---
title: 'Breaking Change: Kestrel: Deaktivierung von HTTP/2 bei inkompatiblen Windows-Versionen über TLS'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Kestrel: Deaktivierung von HTTP/2 bei inkompatiblen Windows-Versionen über TLS'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: befd393795f3e1859d391bca513dd9856101d295
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759502"
---
# <a name="kestrel-http2-disabled-over-tls-on-incompatible-windows-versions"></a><span data-ttu-id="5ecda-103">Kestrel: Deaktivierung von HTTP/2 bei inkompatiblen Windows-Versionen über TLS</span><span class="sxs-lookup"><span data-stu-id="5ecda-103">Kestrel: HTTP/2 disabled over TLS on incompatible Windows versions</span></span>

<span data-ttu-id="5ecda-104">Es müssen zwei Anforderungen erfüllt sein, um HTTP/2 über TLS (Transport Layer Security) unter Windows zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="5ecda-104">To enable HTTP/2 over Transport Layer Security (TLS) on Windows, two requirements need to be met:</span></span>

- <span data-ttu-id="5ecda-105">ALPN-Unterstützung (Application-Layer Protocol Negotiation), die ab Windows 8.1 und Windows Server 2012 R2 verfügbar ist</span><span class="sxs-lookup"><span data-stu-id="5ecda-105">Application-Layer Protocol Negotiation (ALPN) support, which is available starting with Windows 8.1 and Windows Server 2012 R2.</span></span>
- <span data-ttu-id="5ecda-106">Eine Reihe von Verschlüsselungen, die mit HTTP/2 kompatibel und ab Windows 10 und Windows Server 2016 verfügbar sind</span><span class="sxs-lookup"><span data-stu-id="5ecda-106">A set of ciphers compatible with HTTP/2, which is available starting with Windows 10 and Windows Server 2016.</span></span>

<span data-ttu-id="5ecda-107">Daher hat sich das Verhalten von Kestrel bei der Konfiguration von HTTP/2 über TLS wie folgt geändert:</span><span class="sxs-lookup"><span data-stu-id="5ecda-107">As such, Kestrel's behavior when HTTP/2 over TLS is configured has changed to:</span></span>

- <span data-ttu-id="5ecda-108">Downgrade auf `Http1` und Protokollieren einer Meldung auf `Information`-Ebene, wenn [ListenOptions.HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols) auf `Http1AndHttp2` festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="5ecda-108">Downgrade to `Http1` and log a message at the `Information` level when [ListenOptions.HttpProtocols](/dotnet/api/microsoft.aspnetcore.server.kestrel.core.httpprotocols) is set to `Http1AndHttp2`.</span></span> <span data-ttu-id="5ecda-109">Der Standardwert für `ListenOptions.HttpProtocols` lautet `Http1AndHttp2`.</span><span class="sxs-lookup"><span data-stu-id="5ecda-109">`Http1AndHttp2` is the default value for `ListenOptions.HttpProtocols`.</span></span>
- <span data-ttu-id="5ecda-110">Ausgabe von `NotSupportedException`, wenn `ListenOptions.HttpProtocols` auf `Http2` festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="5ecda-110">Throw a `NotSupportedException` when `ListenOptions.HttpProtocols` is set to `Http2`.</span></span>

<span data-ttu-id="5ecda-111">Weitere Informationen finden Sie unter Issue [dotnet/aspnetcore#23068](https://github.com/dotnet/aspnetcore/issues/23068).</span><span class="sxs-lookup"><span data-stu-id="5ecda-111">For discussion, see issue [dotnet/aspnetcore#23068](https://github.com/dotnet/aspnetcore/issues/23068).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5ecda-112">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="5ecda-112">Version introduced</span></span>

<span data-ttu-id="5ecda-113">ASP.NET Core 5.0 Preview 7</span><span class="sxs-lookup"><span data-stu-id="5ecda-113">ASP.NET Core 5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="5ecda-114">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="5ecda-114">Old behavior</span></span>

<span data-ttu-id="5ecda-115">In der folgenden Tabelle wird das Verhalten beschrieben, wenn HTTP/2 über TLS konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="5ecda-115">The following table outlines the behavior when HTTP/2 over TLS is configured.</span></span>

| <span data-ttu-id="5ecda-116">Protokolle</span><span class="sxs-lookup"><span data-stu-id="5ecda-116">Protocols</span></span> | <span data-ttu-id="5ecda-117">Windows 7,</span><span class="sxs-lookup"><span data-stu-id="5ecda-117">Windows 7,</span></span><br /><span data-ttu-id="5ecda-118">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5ecda-118">Windows Server 2008 R2,</span></span><br /><span data-ttu-id="5ecda-119">oder früher</span><span class="sxs-lookup"><span data-stu-id="5ecda-119">or earlier</span></span> | <span data-ttu-id="5ecda-120">Windows 8,</span><span class="sxs-lookup"><span data-stu-id="5ecda-120">Windows 8,</span></span><br /><span data-ttu-id="5ecda-121">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="5ecda-121">Windows Server 2012</span></span> | <span data-ttu-id="5ecda-122">Windows 8.1,</span><span class="sxs-lookup"><span data-stu-id="5ecda-122">Windows 8.1,</span></span><br /><span data-ttu-id="5ecda-123">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5ecda-123">Windows Server 2012 R2</span></span> | <span data-ttu-id="5ecda-124">Windows 10,</span><span class="sxs-lookup"><span data-stu-id="5ecda-124">Windows 10,</span></span><br /><span data-ttu-id="5ecda-125">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="5ecda-125">Windows Server 2016,</span></span><br /><span data-ttu-id="5ecda-126">oder höher</span><span class="sxs-lookup"><span data-stu-id="5ecda-126">or newer</span></span> |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | <span data-ttu-id="5ecda-127">Ausgabe von `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="5ecda-127">Throw `NotSupportedException`</span></span>                   | <span data-ttu-id="5ecda-128">Fehler beim TLS-Handshake</span><span class="sxs-lookup"><span data-stu-id="5ecda-128">Error during TLS handshake</span></span>     | <span data-ttu-id="5ecda-129">Fehler beim TLS-Handshake &ast;</span><span class="sxs-lookup"><span data-stu-id="5ecda-129">Error during TLS handshake &ast;</span></span>     | <span data-ttu-id="5ecda-130">Kein Fehler</span><span class="sxs-lookup"><span data-stu-id="5ecda-130">No error</span></span> |
| `Http1AndHttp2` | <span data-ttu-id="5ecda-131">Downgrade auf `Http1`</span><span class="sxs-lookup"><span data-stu-id="5ecda-131">Downgrade to `Http1`</span></span>                    | <span data-ttu-id="5ecda-132">Herabstufung auf `Http1`</span><span class="sxs-lookup"><span data-stu-id="5ecda-132">Downgrade to `Http1`</span></span>     | <span data-ttu-id="5ecda-133">Fehler beim TLS-Handshake &ast;</span><span class="sxs-lookup"><span data-stu-id="5ecda-133">Error during TLS handshake &ast;</span></span>     | <span data-ttu-id="5ecda-134">Kein Fehler</span><span class="sxs-lookup"><span data-stu-id="5ecda-134">No error</span></span> |

<span data-ttu-id="5ecda-135">&ast; Konfigurieren Sie kompatible Verschlüsselungssammlungen, um diese Szenarios zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5ecda-135">&ast; Configure compatible cipher suites to enable these scenarios.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="5ecda-136">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="5ecda-136">New behavior</span></span>

<span data-ttu-id="5ecda-137">In der folgenden Tabelle wird das Verhalten beschrieben, wenn HTTP/2 über TLS konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="5ecda-137">The following table outlines the behavior when HTTP/2 over TLS is configured.</span></span>

| <span data-ttu-id="5ecda-138">Protokolle</span><span class="sxs-lookup"><span data-stu-id="5ecda-138">Protocols</span></span> | <span data-ttu-id="5ecda-139">Windows 7,</span><span class="sxs-lookup"><span data-stu-id="5ecda-139">Windows 7,</span></span><br /><span data-ttu-id="5ecda-140">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5ecda-140">Windows Server 2008 R2,</span></span><br /><span data-ttu-id="5ecda-141">oder früher</span><span class="sxs-lookup"><span data-stu-id="5ecda-141">or earlier</span></span> | <span data-ttu-id="5ecda-142">Windows 8,</span><span class="sxs-lookup"><span data-stu-id="5ecda-142">Windows 8,</span></span><br /><span data-ttu-id="5ecda-143">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="5ecda-143">Windows Server 2012</span></span> | <span data-ttu-id="5ecda-144">Windows 8.1,</span><span class="sxs-lookup"><span data-stu-id="5ecda-144">Windows 8.1,</span></span><br /><span data-ttu-id="5ecda-145">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5ecda-145">Windows Server 2012 R2</span></span> | <span data-ttu-id="5ecda-146">Windows 10,</span><span class="sxs-lookup"><span data-stu-id="5ecda-146">Windows 10,</span></span><br /><span data-ttu-id="5ecda-147">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="5ecda-147">Windows Server 2016,</span></span><br /><span data-ttu-id="5ecda-148">oder höher</span><span class="sxs-lookup"><span data-stu-id="5ecda-148">or newer</span></span> |
|---------------|-----------------------------------------------|--------------------------------|-------------------------------------|------------------------------------------|
| `Http2`         | <span data-ttu-id="5ecda-149">Ausgabe von `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="5ecda-149">Throw `NotSupportedException`</span></span>                   | <span data-ttu-id="5ecda-150">Ausgabe von `NotSupportedException`</span><span class="sxs-lookup"><span data-stu-id="5ecda-150">Throw `NotSupportedException`</span></span>     | <span data-ttu-id="5ecda-151">Ausgabe von `NotSupportedException` &ast;&ast;</span><span class="sxs-lookup"><span data-stu-id="5ecda-151">Throw `NotSupportedException` &ast;&ast;</span></span>     | <span data-ttu-id="5ecda-152">Kein Fehler</span><span class="sxs-lookup"><span data-stu-id="5ecda-152">No error</span></span> |
| `Http1AndHttp2` | <span data-ttu-id="5ecda-153">Downgrade auf `Http1`</span><span class="sxs-lookup"><span data-stu-id="5ecda-153">Downgrade to `Http1`</span></span>                    | <span data-ttu-id="5ecda-154">Downgrade auf `Http1`</span><span class="sxs-lookup"><span data-stu-id="5ecda-154">Downgrade to `Http1`</span></span>     | <span data-ttu-id="5ecda-155">Downgrade auf `Http1` &ast;&ast;</span><span class="sxs-lookup"><span data-stu-id="5ecda-155">Downgrade to `Http1` &ast;&ast;</span></span>     | <span data-ttu-id="5ecda-156">Kein Fehler</span><span class="sxs-lookup"><span data-stu-id="5ecda-156">No error</span></span> |

<span data-ttu-id="5ecda-157">&ast;&ast; Konfigurieren Sie kompatible Verschlüsselungssammlungen, und legen Sie den App-Kontextwechsel `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` auf `true` fest, um diese Szenarios zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5ecda-157">&ast;&ast; Configure compatible cipher suites and set the app context switch `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` to `true` to enable these scenarios.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="5ecda-158">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="5ecda-158">Reason for change</span></span>

<span data-ttu-id="5ecda-159">Durch diese Änderung wird sichergestellt, dass Kompatibilitätsfehler bei HTTP/2 über TLS und älteren Windows-Versionen so früh und klar wie möglich angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="5ecda-159">This change ensures compatibility errors for HTTP/2 over TLS on older Windows versions are surfaced as early and as clearly as possible.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5ecda-160">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="5ecda-160">Recommended action</span></span>

<span data-ttu-id="5ecda-161">Stellen Sie sicher, dass HTTP/2 über TLS bei inkompatiblen Windows-Versionen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="5ecda-161">Ensure HTTP/2 over TLS is disabled on incompatible Windows versions.</span></span> <span data-ttu-id="5ecda-162">Windows 8.1 und Windows Server 2012 R2 sind inkompatibel, da sie standardmäßig nicht über die erforderlichen Verschlüsselungen verfügen.</span><span class="sxs-lookup"><span data-stu-id="5ecda-162">Windows 8.1 and Windows Server 2012 R2 are incompatible since they lack the necessary ciphers by default.</span></span> <span data-ttu-id="5ecda-163">Allerdings ist es möglich, die Computerkonfigurationseinstellungen so zu aktualisieren, dass mit HTTP/2 kompatible Verschlüsselungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5ecda-163">However, it's possible to update the Computer Configuration settings to use HTTP/2 compatible ciphers.</span></span> <span data-ttu-id="5ecda-164">Weitere Informationen finden Sie unter [TLS-Verschlüsselungssammlungen in Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1).</span><span class="sxs-lookup"><span data-stu-id="5ecda-164">For more information, see [TLS cipher suites in Windows 8.1](/windows/win32/secauthn/tls-cipher-suites-in-windows-8-1).</span></span> <span data-ttu-id="5ecda-165">Nach der Konfiguration muss HTTP/2 über TLS in Kestrel aktiviert werden, indem der App-Kontextwechsel `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="5ecda-165">Once configured, HTTP/2 over TLS on Kestrel must be enabled by setting the app context switch `Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2`.</span></span> <span data-ttu-id="5ecda-166">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5ecda-166">For example:</span></span>

```csharp
AppContext.SetSwitch("Microsoft.AspNetCore.Server.Kestrel.EnableWindows81Http2", true);
```

<span data-ttu-id="5ecda-167">Die vorhandene Unterstützung wurde nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="5ecda-167">No underlying support has changed.</span></span> <span data-ttu-id="5ecda-168">HTTP/2 über TLS hat beispielsweise nie unter Windows 8 oder Windows Server 2012 funktioniert.</span><span class="sxs-lookup"><span data-stu-id="5ecda-168">For example, HTTP/2 over TLS has never worked on Windows 8 or Windows Server 2012.</span></span> <span data-ttu-id="5ecda-169">Durch diese Änderung wird die Anzeige von Fehlern in den nicht unterstützten Szenarios angepasst.</span><span class="sxs-lookup"><span data-stu-id="5ecda-169">This change modifies how errors in these unsupported scenarios are presented.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5ecda-170">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="5ecda-170">Affected APIs</span></span>

<span data-ttu-id="5ecda-171">Keine</span><span class="sxs-lookup"><span data-stu-id="5ecda-171">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
