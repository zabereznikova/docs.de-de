---
title: Installieren von .NET Core unter macOS
description: Informationen zu den macOS-Versionen, unter denen Sie .NET Core installieren können
author: adegeo
ms.author: adegeo
ms.date: 06/25/2020
ms.openlocfilehash: f946759a57bf2eedd296ecbd55fd3a5a7560638d
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538365"
---
# <a name="install-net-core-on-macos"></a><span data-ttu-id="935e8-103">Installieren von .NET Core unter macOS</span><span class="sxs-lookup"><span data-stu-id="935e8-103">Install .NET Core on macOS</span></span>

> [!div class="op_single_selector"]
>
> - [Installieren unter Windows](windows.md)
> - [Installieren unter macOS](macos.md)
> - [Installieren unter Linux](linux.md)

<span data-ttu-id="935e8-107">In diesem Artikel wird erläutert, wie Sie .NET Core unter macOS installieren.</span><span class="sxs-lookup"><span data-stu-id="935e8-107">In this article, you'll learn how to install .NET Core on macOS.</span></span> <span data-ttu-id="935e8-108">.NET Core besteht aus der Runtime und dem SDK.</span><span class="sxs-lookup"><span data-stu-id="935e8-108">.NET Core is made up of the runtime and the SDK.</span></span> <span data-ttu-id="935e8-109">Die Runtime wird zum Ausführen von .NET Core-Apps verwendet und ist möglicherweise bereits in der App enthalten. Dies ist allerdings keine Voraussetzung.</span><span class="sxs-lookup"><span data-stu-id="935e8-109">The runtime is used to run a .NET Core app and may or may not be included with the app.</span></span> <span data-ttu-id="935e8-110">Das SDK wird zum Erstellen von .NET Core-Apps und -Bibliotheken verwendet.</span><span class="sxs-lookup"><span data-stu-id="935e8-110">The SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="935e8-111">Die .NET Core-Runtime wird immer mit dem SDK installiert.</span><span class="sxs-lookup"><span data-stu-id="935e8-111">The .NET Core runtime is always installed with the SDK.</span></span>

<span data-ttu-id="935e8-112">Version 3.1 ist die aktuelle Version von .NET Core.</span><span class="sxs-lookup"><span data-stu-id="935e8-112">The latest version of .NET Core is 3.1.</span></span>

> [!div class="button"]
> [<span data-ttu-id="935e8-113">.NET Core herunterladen</span><span class="sxs-lookup"><span data-stu-id="935e8-113">Download .NET Core</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="935e8-114">Unterstützte Versionen</span><span class="sxs-lookup"><span data-stu-id="935e8-114">Supported releases</span></span>

<span data-ttu-id="935e8-115">Die folgende Tabelle enthält die derzeit unterstützten .NET Core-Releases und die macOS-Versionen, die diese unterstützen.</span><span class="sxs-lookup"><span data-stu-id="935e8-115">The following table is a list of currently supported .NET Core releases and the versions of macOS they're supported on.</span></span> <span data-ttu-id="935e8-116">Diese Versionen werden so lange unterstützt, bis die Version von [.NET Core das Ende des Supports erreicht](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="935e8-116">These versions remain supported either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

- <span data-ttu-id="935e8-117">✔️ gibt an, dass die Version von .NET Core weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="935e8-117">A ✔️ indicates that the version of .NET Core is still supported.</span></span>
- <span data-ttu-id="935e8-118">❌ gibt an, dass die Version von .NET Core nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="935e8-118">A ❌ indicates that the version of .NET Core isn't supported.</span></span>

| <span data-ttu-id="935e8-119">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="935e8-119">Operating System</span></span>          | <span data-ttu-id="935e8-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="935e8-120">.NET Core 2.1</span></span> | <span data-ttu-id="935e8-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="935e8-121">.NET Core 3.1</span></span> | <span data-ttu-id="935e8-122">.NET 5 Preview</span><span class="sxs-lookup"><span data-stu-id="935e8-122">.NET 5 Preview</span></span> |
|---------------------------|---------------|---------------|----------------|
| <span data-ttu-id="935e8-123">macOS 10.15 Catalina</span><span class="sxs-lookup"><span data-stu-id="935e8-123">macOS 10.15 "Catalina"</span></span>    | <span data-ttu-id="935e8-124">✔️ 2.1 ([Versionshinweise][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="935e8-124">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="935e8-125">✔️ 3.1 ([Versionshinweise][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="935e8-125">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="935e8-126">✔️ Vorschauversion 5.0 ([Versionshinweise][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="935e8-126">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="935e8-127">macOS 10.14 Mojave</span><span class="sxs-lookup"><span data-stu-id="935e8-127">macOS 10.14 "Mojave"</span></span>      | <span data-ttu-id="935e8-128">✔️ 2.1 ([Versionshinweise][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="935e8-128">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="935e8-129">✔️ 3.1 ([Versionshinweise][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="935e8-129">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="935e8-130">✔️ Vorschauversion 5.0 ([Versionshinweise][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="935e8-130">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="935e8-131">macOS 10.13 High Sierra</span><span class="sxs-lookup"><span data-stu-id="935e8-131">macOS 10.13 "High Sierra"</span></span> | <span data-ttu-id="935e8-132">✔️ 2.1 ([Versionshinweise][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="935e8-132">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="935e8-133">✔️ 3.1 ([Versionshinweise][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="935e8-133">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="935e8-134">✔️ Vorschauversion 5.0 ([Versionshinweise][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="935e8-134">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="935e8-135">macOS 10.12 „Sierra“</span><span class="sxs-lookup"><span data-stu-id="935e8-135">macOS 10.12 "Sierra"</span></span>      | <span data-ttu-id="935e8-136">✔️ 2.1 ([Versionshinweise][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="935e8-136">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="935e8-137">❌ 3.1 ([Versionshinweise][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="935e8-137">❌ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="935e8-138">❌ Vorschauversion 5.0. ([Versionshinweise][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="935e8-138">❌ 5.0 Preview ([Release notes][release-notes-50])</span></span> |

## <a name="unsupported-releases"></a><span data-ttu-id="935e8-139">Nicht unterstützte Versionen</span><span class="sxs-lookup"><span data-stu-id="935e8-139">Unsupported releases</span></span>

<span data-ttu-id="935e8-140">Die folgenden Versionen von .NET Core werden ❌ nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="935e8-140">The following versions of .NET Core are ❌ no longer supported.</span></span> <span data-ttu-id="935e8-141">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="935e8-141">The downloads for these still remain published:</span></span>

- <span data-ttu-id="935e8-142">3.0 ([Versionshinweise][release-notes-30])</span><span class="sxs-lookup"><span data-stu-id="935e8-142">3.0 ([Release notes][release-notes-30])</span></span>
- <span data-ttu-id="935e8-143">2.2 ([Versionshinweise][release-notes-22])</span><span class="sxs-lookup"><span data-stu-id="935e8-143">2.2 ([Release notes][release-notes-22])</span></span>
- <span data-ttu-id="935e8-144">2.0 ([Versionshinweise][release-notes-20])</span><span class="sxs-lookup"><span data-stu-id="935e8-144">2.0 ([Release notes][release-notes-20])</span></span>

## <a name="runtime-information"></a><span data-ttu-id="935e8-145">Informationen zur Runtime</span><span class="sxs-lookup"><span data-stu-id="935e8-145">Runtime information</span></span>

<span data-ttu-id="935e8-146">Die Runtime wird zur Ausführung der mit .NET Core erstellten Apps verwendet.</span><span class="sxs-lookup"><span data-stu-id="935e8-146">The runtime is used to run apps created with .NET Core.</span></span> <span data-ttu-id="935e8-147">Wenn ein App-Autor eine App veröffentlicht, kann er die Runtime zusammen mit seiner App bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="935e8-147">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="935e8-148">Wenn er die Runtime nicht hinzufügt, ist es dem Benutzer überlassen, die Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="935e8-148">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="935e8-149">Es gibt drei verschiedene Runtimes, die Sie unter macOS installieren können:</span><span class="sxs-lookup"><span data-stu-id="935e8-149">There are three different runtimes you can install on macOS:</span></span>

<span data-ttu-id="935e8-150">*ASP.NET Core-Runtime*</span><span class="sxs-lookup"><span data-stu-id="935e8-150">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="935e8-151">Diese führt ASP.NET Core-Apps aus.</span><span class="sxs-lookup"><span data-stu-id="935e8-151">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="935e8-152">Sie umfasst die .NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="935e8-152">Includes the .NET Core runtime.</span></span>

<span data-ttu-id="935e8-153">*.NET Core-Runtime*</span><span class="sxs-lookup"><span data-stu-id="935e8-153">*.NET Core runtime*</span></span>\
<span data-ttu-id="935e8-154">Hierbei handelt es sich um die einfachste Runtime, die keine weiteren Runtimes beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="935e8-154">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="935e8-155">Es wird dringend empfohlen, dass Sie die *ASP.NET Core-Runtime* installieren, um die bestmögliche Kompatibilität mit .NET Core-Apps zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="935e8-155">It's highly recommended that you install *ASP.NET Core runtime* for the best compatibility with .NET Core apps.</span></span>

> [!div class="button"]
> [<span data-ttu-id="935e8-156">.NET Core-Runtime herunterladen</span><span class="sxs-lookup"><span data-stu-id="935e8-156">Download .NET Core Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="935e8-157">Informationen zum SDK</span><span class="sxs-lookup"><span data-stu-id="935e8-157">SDK information</span></span>

<span data-ttu-id="935e8-158">Das SDK wird zum Erstellen und Veröffentlichen von .NET Core-Apps und -Bibliotheken verwendet.</span><span class="sxs-lookup"><span data-stu-id="935e8-158">The SDK is used to build and publish .NET Core apps and libraries.</span></span> <span data-ttu-id="935e8-159">Die Installation des SDK umfasst beide [Runtimes](#runtime-information): ASP.NET Core und .NET Core.</span><span class="sxs-lookup"><span data-stu-id="935e8-159">Installing the SDK includes both [runtimes](#runtime-information): ASP.NET Core and .NET Core.</span></span>

> [!div class="button"]
> [<span data-ttu-id="935e8-160">.NET Core SDK herunterladen</span><span class="sxs-lookup"><span data-stu-id="935e8-160">Download .NET Core SDK</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a><span data-ttu-id="935e8-161">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="935e8-161">Dependencies</span></span>

<span data-ttu-id="935e8-162">.NET Core wird von den folgenden macOS-Versionen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="935e8-162">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="935e8-163">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="935e8-163">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="935e8-164">.NET Core-Version</span><span class="sxs-lookup"><span data-stu-id="935e8-164">.NET Core Version</span></span> | <span data-ttu-id="935e8-165">macOS</span><span class="sxs-lookup"><span data-stu-id="935e8-165">macOS</span></span>                 | <span data-ttu-id="935e8-166">Architekturen</span><span class="sxs-lookup"><span data-stu-id="935e8-166">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="935e8-167">3.1</span><span class="sxs-lookup"><span data-stu-id="935e8-167">3.1</span></span>               | <span data-ttu-id="935e8-168">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="935e8-168">High Sierra (10.13+)</span></span>  | <span data-ttu-id="935e8-169">x64</span><span class="sxs-lookup"><span data-stu-id="935e8-169">x64</span></span> | [<span data-ttu-id="935e8-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="935e8-170">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="935e8-171">3.0</span><span class="sxs-lookup"><span data-stu-id="935e8-171">3.0</span></span>               | <span data-ttu-id="935e8-172">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="935e8-172">High Sierra (10.13+)</span></span>  | <span data-ttu-id="935e8-173">x64</span><span class="sxs-lookup"><span data-stu-id="935e8-173">x64</span></span> | [<span data-ttu-id="935e8-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="935e8-174">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="935e8-175">2.2</span><span class="sxs-lookup"><span data-stu-id="935e8-175">2.2</span></span>               | <span data-ttu-id="935e8-176">Sierra (10.12 oder höher)</span><span class="sxs-lookup"><span data-stu-id="935e8-176">Sierra (10.12+)</span></span>       | <span data-ttu-id="935e8-177">x64</span><span class="sxs-lookup"><span data-stu-id="935e8-177">x64</span></span> | [<span data-ttu-id="935e8-178">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="935e8-178">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="935e8-179">2.1</span><span class="sxs-lookup"><span data-stu-id="935e8-179">2.1</span></span>               | <span data-ttu-id="935e8-180">Sierra (10.12 oder höher)</span><span class="sxs-lookup"><span data-stu-id="935e8-180">Sierra (10.12+)</span></span>       | <span data-ttu-id="935e8-181">x64</span><span class="sxs-lookup"><span data-stu-id="935e8-181">x64</span></span> | [<span data-ttu-id="935e8-182">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="935e8-182">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="935e8-183">Ab macOS Catalina (Version 10.15) muss jegliche Software notarisiert werden, die nach dem 1. Juni 2019 erstellt wurde und mit einer Entwickler-ID verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="935e8-183">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="935e8-184">Diese Voraussetzung gilt für die .NET Core-Runtime, das .NET Core SDK und jegliche Software, die mit .NET Core erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="935e8-184">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="935e8-185">Die Installationsprogramme für die Versionen 3.1, 3.0 und 2.1 von .NET Core (sowohl für die Runtime als auch das SDK) wurden seit dem 18. Februar 2020 notarisiert.</span><span class="sxs-lookup"><span data-stu-id="935e8-185">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="935e8-186">Vorherige Versionen wurden nicht notarisiert.</span><span class="sxs-lookup"><span data-stu-id="935e8-186">Prior released versions aren't notarized.</span></span> <span data-ttu-id="935e8-187">Wenn Sie eine nicht notarisierte App ausführen, wird eine Fehlermeldung ähnlich der folgenden Abbildung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="935e8-187">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina-Notarisierungswarnung](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="935e8-189">Weitere Informationen dazu, wie sich die erzwungene Notarisierung auf .NET Core (und Ihre .NET Core-Apps) auswirkt, finden Sie unter [Verwenden der macOS Catalina-Notarisierung](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="935e8-189">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="935e8-190">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="935e8-190">libgdiplus</span></span>

<span data-ttu-id="935e8-191">Für .NET Core-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, muss libgdiplus installiert sein.</span><span class="sxs-lookup"><span data-stu-id="935e8-191">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="935e8-192">Eine einfache Möglichkeit zum Abrufen von libgdiplus bietet der [Homebrew](https://brew.sh/)-Paket-Manager („brew“) für macOS.</span><span class="sxs-lookup"><span data-stu-id="935e8-192">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="935e8-193">Installieren Sie nach der Installation von *brew* libgdiplus durch Ausführen der folgenden Befehle in einem Terminal (Befehl):</span><span class="sxs-lookup"><span data-stu-id="935e8-193">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a><span data-ttu-id="935e8-194">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="935e8-194">Install with an installer</span></span>

<span data-ttu-id="935e8-195">macOS verfügt über eigenständige Installer, die zur Installation des .NET Core 3.1 SDK verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="935e8-195">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="935e8-196">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="935e8-196">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="935e8-197">Herunterladen und manuelles Installieren</span><span class="sxs-lookup"><span data-stu-id="935e8-197">Download and manually install</span></span>

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="935e8-198">Alternativ zu den macOS-Installationsprogrammen für .NET Core können Sie das SDK und die Runtime herunterladen und manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="935e8-198">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="935e8-199">Die manuelle Installation wird normalerweise im Rahmen von CI-Tests (Continuous Integration) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="935e8-199">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="935e8-200">Für Entwickler oder Benutzer eignet sich in der Regel die Verwendung eines [Installationsprogramms](https://dotnet.microsoft.com/download/dotnet-core) besser.</span><span class="sxs-lookup"><span data-stu-id="935e8-200">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="935e8-201">Wenn Sie das .NET Core SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="935e8-201">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="935e8-202">Laden Sie zunächst entweder für das SDK oder die Runtime eine **binäre** Version auf einer der folgenden Websites herunter:</span><span class="sxs-lookup"><span data-stu-id="935e8-202">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="935e8-203">✔️ [.NET 5.0 Preview herunterladen](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="935e8-203">✔️ [.NET 5.0 preview downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="935e8-204">✔️ [.NET Core 3.1 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="935e8-204">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="935e8-205">✔️ [.NET Core 2.1 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="935e8-205">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="935e8-206">Alle .NET Core-Downloads</span><span class="sxs-lookup"><span data-stu-id="935e8-206">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="935e8-207">Extrahieren Sie als Nächstes die heruntergeladene Datei, und führen Sie den Befehl `export` aus, um von . NET Core verwendete Variablen festzulegen. Stellen Sie anschließend sicher, dass sich .NET Core in PATH befindet.</span><span class="sxs-lookup"><span data-stu-id="935e8-207">Next, extract the downloaded file and use the `export` command to set variables used by .NET Core and then ensure .NET Core is in PATH.</span></span>

<span data-ttu-id="935e8-208">Laden Sie zunächst eine binäre .NET Core-Version herunter, um die Runtime zu extrahieren und die .NET Core-CLI-Befehle im Terminal bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="935e8-208">To extract the runtime and make the .NET Core CLI commands available at the terminal, first download a .NET Core binary release.</span></span> <span data-ttu-id="935e8-209">Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle im Verzeichnis aus, in dem die Datei gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="935e8-209">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="935e8-210">Je nachdem, was Sie heruntergeladen haben, kann der Name der Archivdatei abweichen.</span><span class="sxs-lookup"><span data-stu-id="935e8-210">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="935e8-211">**Verwenden Sie den folgenden Befehl, um die Runtime zu extrahieren:**</span><span class="sxs-lookup"><span data-stu-id="935e8-211">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.5-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="935e8-212">**Verwenden Sie den folgenden Befehl, um das SDK zu extrahieren:**</span><span class="sxs-lookup"><span data-stu-id="935e8-212">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-3.1.301-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="935e8-213">Mit den oben aufgeführten `export`-Befehlen werden nur die .NET Core-CLI-Befehle für die Terminalsitzung bereitgestellt, in der sie ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="935e8-213">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="935e8-214">Sie können Ihr Shell-Profil bearbeiten, um diese Befehle dauerhaft hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="935e8-214">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="935e8-215">Für Linux sind verschiedene Shells verfügbar, die jeweils über ein anderes Profil verfügen.</span><span class="sxs-lookup"><span data-stu-id="935e8-215">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="935e8-216">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="935e8-216">For example:</span></span>
>
> - <span data-ttu-id="935e8-217">**Bash-Shell**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="935e8-217">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="935e8-218">**Korn-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="935e8-218">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="935e8-219">**Z-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="935e8-219">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="935e8-220">Bearbeiten Sie die geeignete Quelldatei für die Shell, und fügen Sie `:$HOME/dotnet` am Ende der vorhandenen `PATH`-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="935e8-220">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="935e8-221">Wenn keine `PATH`-Anweisung enthalten ist, fügen Sie eine neue Zeile mit `export PATH=$PATH:$HOME/dotnet` hinzu.</span><span class="sxs-lookup"><span data-stu-id="935e8-221">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="935e8-222">Fügen Sie außerdem `export DOTNET_ROOT=$HOME/dotnet` am Ende der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="935e8-222">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="935e8-223">Bei diesem Ansatz können Sie unterschiedliche Versionen an separaten Speicherorten installieren und explizit auswählen, welche Version von welcher Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="935e8-223">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="935e8-224">Installieren mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="935e8-224">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="935e8-225">Visual Studio für Mac installiert das .NET Core SDK, wenn die **.NET Core-Workload** ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="935e8-225">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="935e8-226">Informationen zu den ersten Schritten mit der .NET Core-Entwicklung unter macOS finden Sie unter [Installieren von Visual Studio 2019 für Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="935e8-226">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="935e8-227">Für die neueste Version .NET Core 3.1 müssen Sie Visual Studio für Mac 8.4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="935e8-227">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4.</span></span>

<span data-ttu-id="935e8-228">[![macOS-Feature für Visual Studio 2019 für Mac mit .NET Core-Workload](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="935e8-228">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="935e8-229">Installieren zusammen mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="935e8-229">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="935e8-230">Visual Studio Code ist ein leistungsstarker und einfacher Quellcode-Editor, der auf Ihrem Desktop ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="935e8-230">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="935e8-231">Visual Studio Code ist für Windows, macOS und Linux verfügbar.</span><span class="sxs-lookup"><span data-stu-id="935e8-231">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="935e8-232">Zwar verfügt Visual Studio Code im Gegensatz zu Visual Studio über keine automatisierten .NET Core-Installer, allerdings ist das Hinzufügen der Unterstützung von .NET Core einfach.</span><span class="sxs-lookup"><span data-stu-id="935e8-232">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="935e8-233">[Laden Sie Visual Studio Code herunter, und installieren Sie das Tool.](https://code.visualstudio.com/Download)</span><span class="sxs-lookup"><span data-stu-id="935e8-233">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="935e8-234">[Laden Sie das .NET Core SDK herunter, und installieren Sie es.](https://dotnet.microsoft.com/download/dotnet-core)</span><span class="sxs-lookup"><span data-stu-id="935e8-234">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="935e8-235">[Installieren Sie die C#-Erweiterung aus dem Visual Studio Code Marketplace.](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)</span><span class="sxs-lookup"><span data-stu-id="935e8-235">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="install-with-bash-automation"></a><span data-ttu-id="935e8-236">Installieren mit Bash-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="935e8-236">Install with bash automation</span></span>

<span data-ttu-id="935e8-237">Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="935e8-237">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="935e8-238">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="935e8-238">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="935e8-239">Das Skript installiert standardmäßig die neueste [Langzeitunterstützungsversion](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), nämlich .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="935e8-239">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="935e8-240">Sie können eine bestimmte Version durch Angeben der `current`-Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="935e8-240">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="935e8-241">Schließen Sie die `runtime`-Option mit ein, um eine Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="935e8-241">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="935e8-242">Andernfalls installiert das Skript das [SDK](./windows.md) nicht.</span><span class="sxs-lookup"><span data-stu-id="935e8-242">Otherwise, the script installs the [SDK](./windows.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="935e8-243">Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert.</span><span class="sxs-lookup"><span data-stu-id="935e8-243">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="935e8-244">Die ASP.NET Core-Runtime enthält auch die .NET Core-Standardruntime.</span><span class="sxs-lookup"><span data-stu-id="935e8-244">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="docker"></a><span data-ttu-id="935e8-245">Docker</span><span class="sxs-lookup"><span data-stu-id="935e8-245">Docker</span></span>

<span data-ttu-id="935e8-246">Container bieten eine einfache Möglichkeit, Ihre Anwendung vom Rest des Hostsystems zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="935e8-246">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="935e8-247">Container auf demselben Computer teilen nur den Kernel und verwenden die Ihrer Anwendung zur Verfügung gestellten Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="935e8-247">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="935e8-248">.NET Core kann in einem Docker-Container ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="935e8-248">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="935e8-249">Offizielle.NET Core Docker-Images werden in Microsoft Container Registry (MCR) veröffentlicht und sind im [Microsoft.NET Core Docker-Hub-Repository](https://hub.docker.com/_/microsoft-dotnet-core/) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="935e8-249">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="935e8-250">Jedes Repository enthält Images für verschiedene Kombinationen von .NET (SDK oder Runtime) und dem Betriebssystem, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="935e8-250">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="935e8-251">Microsoft stellt Images bereit, die auf bestimmte Szenarien zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="935e8-251">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="935e8-252">So stellt beispielsweise das [ASP.NET Core-Repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) Images bereit, die für die Ausführung von ASP.NET Core-Apps in der Produktion erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="935e8-252">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="935e8-253">Weitere Informationen zur Verwendung von .NET Core in einem Docker-Container finden Sie unter [Einführung in .NET und Docker](../docker/introduction.md) und [Beispiele](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="935e8-253">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="935e8-254">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="935e8-254">Next steps</span></span>

- <span data-ttu-id="935e8-255">[Überprüfen, ob .NET Core bereits installiert ist](how-to-detect-installed-versions.md?pivots=os-macos)</span><span class="sxs-lookup"><span data-stu-id="935e8-255">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md?pivots=os-macos).</span></span>
- <span data-ttu-id="935e8-256">[Verwenden der macOS Catalina-Notarisierung](macos-notarization-issues.md)</span><span class="sxs-lookup"><span data-stu-id="935e8-256">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="935e8-257">[Tutorial: Erste Schritte unter macOS](../tutorials/with-visual-studio-mac.md)</span><span class="sxs-lookup"><span data-stu-id="935e8-257">[Tutorial: Get started on macOS](../tutorials/with-visual-studio-mac.md).</span></span>
- <span data-ttu-id="935e8-258">[Tutorial: Erstellen einer neuen App mit Visual Studio Code](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="935e8-258">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="935e8-259">[Tutorial: Containerisieren einer .NET Core-App](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="935e8-259">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
