---
title: Installieren von .NET unter macOS
description: In diesem Artikel erhalten Sie Informationen zu den macOS-Versionen, unter denen Sie .NET installieren können.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 983c5d2c04b87759b898f449bc092161b03c8ace
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594455"
---
# <a name="install-net-on-macos"></a><span data-ttu-id="38e35-103">Installieren von .NET unter macOS</span><span class="sxs-lookup"><span data-stu-id="38e35-103">Install .NET on macOS</span></span>

> [!div class="op_single_selector"]
>
> - [Installieren unter Windows](windows.md)
> - [Installieren unter macOS](macos.md)
> - [Installieren unter Linux](linux.md)

<span data-ttu-id="38e35-107">In diesem Artikel wird erläutert, wie Sie .NET unter macOS installieren.</span><span class="sxs-lookup"><span data-stu-id="38e35-107">In this article, you'll learn how to install .NET on macOS.</span></span> <span data-ttu-id="38e35-108">.NET besteht aus der Runtime und dem SDK.</span><span class="sxs-lookup"><span data-stu-id="38e35-108">.NET is made up of the runtime and the SDK.</span></span> <span data-ttu-id="38e35-109">Die Runtime wird zum Ausführen von .NET-Apps verwendet und ist möglicherweise bereits in der App enthalten.</span><span class="sxs-lookup"><span data-stu-id="38e35-109">The runtime is used to run a .NET app and may or may not be included with the app.</span></span> <span data-ttu-id="38e35-110">Das SDK wird zum Erstellen von .NET-Apps und -Bibliotheken verwendet.</span><span class="sxs-lookup"><span data-stu-id="38e35-110">The SDK is used to create .NET apps and libraries.</span></span> <span data-ttu-id="38e35-111">Die .NET-Runtime wird immer mit dem SDK installiert.</span><span class="sxs-lookup"><span data-stu-id="38e35-111">The .NET runtime is always installed with the SDK.</span></span>

<span data-ttu-id="38e35-112">Version 5.0 ist die aktuelle Version von .NET.</span><span class="sxs-lookup"><span data-stu-id="38e35-112">The latest version of .NET is 5.0.</span></span>

> [!div class="button"]
> [<span data-ttu-id="38e35-113">.NET Core herunterladen</span><span class="sxs-lookup"><span data-stu-id="38e35-113">Download .NET Core</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="38e35-114">Unterstützte Versionen</span><span class="sxs-lookup"><span data-stu-id="38e35-114">Supported releases</span></span>

<span data-ttu-id="38e35-115">Die folgende Tabelle enthält die derzeit unterstützten .NET-Releases und die macOS-Versionen, die diese unterstützen.</span><span class="sxs-lookup"><span data-stu-id="38e35-115">The following table is a list of currently supported .NET releases and the versions of macOS they're supported on.</span></span> <span data-ttu-id="38e35-116">Diese Versionen werden so lange unterstützt, bis die Version von [.NET das Ende des Supports erreicht](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="38e35-116">These versions remain supported either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

- <span data-ttu-id="38e35-117">✔️ gibt an, dass die Version von .NET Core weiterhin unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="38e35-117">A ✔️ indicates that the version of .NET Core is still supported.</span></span>
- <span data-ttu-id="38e35-118">❌ gibt an, dass die Version von .NET Core nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="38e35-118">A ❌ indicates that the version of .NET Core isn't supported.</span></span>

| <span data-ttu-id="38e35-119">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="38e35-119">Operating System</span></span>          | <span data-ttu-id="38e35-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="38e35-120">.NET Core 2.1</span></span> | <span data-ttu-id="38e35-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="38e35-121">.NET Core 3.1</span></span> | <span data-ttu-id="38e35-122">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="38e35-122">.NET 5.0</span></span> |
|---------------------------|---------------|---------------|----------------|
| <span data-ttu-id="38e35-123">macOS 10.15 Catalina</span><span class="sxs-lookup"><span data-stu-id="38e35-123">macOS 10.15 "Catalina"</span></span>    | <span data-ttu-id="38e35-124">✔️ 2.1 ([Versionshinweise][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="38e35-124">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="38e35-125">✔️ 3.1 ([Versionshinweise][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="38e35-125">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="38e35-126">✔️ 5.0 ([Versionshinweise][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="38e35-126">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="38e35-127">macOS 10.14 Mojave</span><span class="sxs-lookup"><span data-stu-id="38e35-127">macOS 10.14 "Mojave"</span></span>      | <span data-ttu-id="38e35-128">✔️ 2.1 ([Versionshinweise][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="38e35-128">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="38e35-129">✔️ 3.1 ([Versionshinweise][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="38e35-129">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="38e35-130">✔️ 5.0 ([Versionshinweise][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="38e35-130">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="38e35-131">macOS 10.13 High Sierra</span><span class="sxs-lookup"><span data-stu-id="38e35-131">macOS 10.13 "High Sierra"</span></span> | <span data-ttu-id="38e35-132">✔️ 2.1 ([Versionshinweise][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="38e35-132">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="38e35-133">✔️ 3.1 ([Versionshinweise][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="38e35-133">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="38e35-134">✔️ 5.0 ([Versionshinweise][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="38e35-134">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="38e35-135">macOS 10.12 „Sierra“</span><span class="sxs-lookup"><span data-stu-id="38e35-135">macOS 10.12 "Sierra"</span></span>      | <span data-ttu-id="38e35-136">✔️ 2.1 ([Versionshinweise][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="38e35-136">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="38e35-137">❌ 3.1 ([Versionshinweise][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="38e35-137">❌ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="38e35-138">❌ 5.0 ([Versionshinweise][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="38e35-138">❌ 5.0 ([Release notes][release-notes-50])</span></span> |

## <a name="unsupported-releases"></a><span data-ttu-id="38e35-139">Nicht unterstützte Versionen</span><span class="sxs-lookup"><span data-stu-id="38e35-139">Unsupported releases</span></span>

<span data-ttu-id="38e35-140">Die folgenden Versionen von .NET werden nicht mehr unterstützt (❌).</span><span class="sxs-lookup"><span data-stu-id="38e35-140">The following versions of .NET are ❌ no longer supported.</span></span> <span data-ttu-id="38e35-141">Die Downloads dafür bleiben weiterhin veröffentlicht:</span><span class="sxs-lookup"><span data-stu-id="38e35-141">The downloads for these still remain published:</span></span>

- <span data-ttu-id="38e35-142">3.0 ([Versionshinweise][release-notes-30])</span><span class="sxs-lookup"><span data-stu-id="38e35-142">3.0 ([Release notes][release-notes-30])</span></span>
- <span data-ttu-id="38e35-143">2.2 ([Versionshinweise][release-notes-22])</span><span class="sxs-lookup"><span data-stu-id="38e35-143">2.2 ([Release notes][release-notes-22])</span></span>
- <span data-ttu-id="38e35-144">2.0 ([Versionshinweise][release-notes-20])</span><span class="sxs-lookup"><span data-stu-id="38e35-144">2.0 ([Release notes][release-notes-20])</span></span>

## <a name="runtime-information"></a><span data-ttu-id="38e35-145">Informationen zur Runtime</span><span class="sxs-lookup"><span data-stu-id="38e35-145">Runtime information</span></span>

<span data-ttu-id="38e35-146">Die Runtime wird zur Ausführung der mit .NET erstellten Apps verwendet.</span><span class="sxs-lookup"><span data-stu-id="38e35-146">The runtime is used to run apps created with .NET.</span></span> <span data-ttu-id="38e35-147">Wenn ein App-Autor eine App veröffentlicht, kann er die Runtime zusammen mit seiner App bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="38e35-147">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="38e35-148">Wenn er die Runtime nicht hinzufügt, ist es dem Benutzer überlassen, die Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="38e35-148">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="38e35-149">Es gibt drei verschiedene Runtimes, die Sie unter macOS installieren können:</span><span class="sxs-lookup"><span data-stu-id="38e35-149">There are three different runtimes you can install on macOS:</span></span>

<span data-ttu-id="38e35-150">*ASP.NET Core-Runtime*</span><span class="sxs-lookup"><span data-stu-id="38e35-150">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="38e35-151">Diese führt ASP.NET Core-Apps aus.</span><span class="sxs-lookup"><span data-stu-id="38e35-151">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="38e35-152">Diese Runtime schließt die .NET-Runtime ein.</span><span class="sxs-lookup"><span data-stu-id="38e35-152">Includes the .NET runtime.</span></span>

<span data-ttu-id="38e35-153">*.NET-Runtime*</span><span class="sxs-lookup"><span data-stu-id="38e35-153">*.NET runtime*</span></span>\
<span data-ttu-id="38e35-154">Hierbei handelt es sich um die einfachste Runtime, die keine weiteren Runtimes beinhaltet.</span><span class="sxs-lookup"><span data-stu-id="38e35-154">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="38e35-155">Es wird dringend empfohlen, dass Sie die *ASP.NET Core-Runtime* installieren, um die bestmögliche Kompatibilität mit .NET-Apps zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="38e35-155">It's highly recommended that you install *ASP.NET Core runtime* for the best compatibility with .NET apps.</span></span>

> [!div class="button"]
> [<span data-ttu-id="38e35-156">.NET-Runtime herunterladen</span><span class="sxs-lookup"><span data-stu-id="38e35-156">Download .NET Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="38e35-157">Informationen zum SDK</span><span class="sxs-lookup"><span data-stu-id="38e35-157">SDK information</span></span>

<span data-ttu-id="38e35-158">Das SDK wird zum Erstellen und Veröffentlichen von .NET-Apps und -Bibliotheken verwendet.</span><span class="sxs-lookup"><span data-stu-id="38e35-158">The SDK is used to build and publish .NET apps and libraries.</span></span> <span data-ttu-id="38e35-159">Die Installation des SDK umfasst beide [Runtimes](#runtime-information): ASP.NET Core und .NET</span><span class="sxs-lookup"><span data-stu-id="38e35-159">Installing the SDK includes both [runtimes](#runtime-information): ASP.NET Core and .NET.</span></span>

## <a name="dependencies"></a><span data-ttu-id="38e35-160">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="38e35-160">Dependencies</span></span>

<span data-ttu-id="38e35-161">.NET wird von den folgenden macOS-Releases unterstützt:</span><span class="sxs-lookup"><span data-stu-id="38e35-161">.NET is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="38e35-162">Die mindestens erforderliche Version ist mit einem `+`-Zeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="38e35-162">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="38e35-163">.NET Core-Version</span><span class="sxs-lookup"><span data-stu-id="38e35-163">.NET Core Version</span></span> | <span data-ttu-id="38e35-164">macOS</span><span class="sxs-lookup"><span data-stu-id="38e35-164">macOS</span></span>                 | <span data-ttu-id="38e35-165">Architekturen</span><span class="sxs-lookup"><span data-stu-id="38e35-165">Architectures</span></span> | <span data-ttu-id="38e35-166">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38e35-166">More information</span></span>    |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="38e35-167">5.0</span><span class="sxs-lookup"><span data-stu-id="38e35-167">5.0</span></span>               | <span data-ttu-id="38e35-168">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="38e35-168">High Sierra (10.13+)</span></span>  | <span data-ttu-id="38e35-169">x64</span><span class="sxs-lookup"><span data-stu-id="38e35-169">x64</span></span> | [<span data-ttu-id="38e35-170">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38e35-170">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md) |
| <span data-ttu-id="38e35-171">3.1</span><span class="sxs-lookup"><span data-stu-id="38e35-171">3.1</span></span>               | <span data-ttu-id="38e35-172">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="38e35-172">High Sierra (10.13+)</span></span>  | <span data-ttu-id="38e35-173">x64</span><span class="sxs-lookup"><span data-stu-id="38e35-173">x64</span></span> | [<span data-ttu-id="38e35-174">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38e35-174">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="38e35-175">3.0</span><span class="sxs-lookup"><span data-stu-id="38e35-175">3.0</span></span>               | <span data-ttu-id="38e35-176">High Sierra (10.13 oder höher)</span><span class="sxs-lookup"><span data-stu-id="38e35-176">High Sierra (10.13+)</span></span>  | <span data-ttu-id="38e35-177">x64</span><span class="sxs-lookup"><span data-stu-id="38e35-177">x64</span></span> | [<span data-ttu-id="38e35-178">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38e35-178">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="38e35-179">2.2</span><span class="sxs-lookup"><span data-stu-id="38e35-179">2.2</span></span>               | <span data-ttu-id="38e35-180">Sierra (10.12 oder höher)</span><span class="sxs-lookup"><span data-stu-id="38e35-180">Sierra (10.12+)</span></span>       | <span data-ttu-id="38e35-181">x64</span><span class="sxs-lookup"><span data-stu-id="38e35-181">x64</span></span> | [<span data-ttu-id="38e35-182">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38e35-182">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="38e35-183">2.1</span><span class="sxs-lookup"><span data-stu-id="38e35-183">2.1</span></span>               | <span data-ttu-id="38e35-184">Sierra (10.12 oder höher)</span><span class="sxs-lookup"><span data-stu-id="38e35-184">Sierra (10.12+)</span></span>       | <span data-ttu-id="38e35-185">x64</span><span class="sxs-lookup"><span data-stu-id="38e35-185">x64</span></span> | [<span data-ttu-id="38e35-186">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38e35-186">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="38e35-187">Ab macOS Catalina (Version 10.15) muss jegliche Software notarisiert werden, die nach dem 1. Juni 2019 erstellt wurde und mit einer Entwickler-ID verteilt wird.</span><span class="sxs-lookup"><span data-stu-id="38e35-187">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="38e35-188">Diese Voraussetzung gilt für die .NET-Runtime, das .NET SDK und jegliche Software, die mit .NET erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="38e35-188">This requirement applies to the .NET runtime, .NET SDK, and software created with .NET.</span></span>

<span data-ttu-id="38e35-189">Die Installationsprogramme für Runtime und SDK für .NET 5.0 und .NET Core 3.1, 3.0 und 2.1 von .NET Core wurden seit dem 18. Februar 2020 notarisiert.</span><span class="sxs-lookup"><span data-stu-id="38e35-189">The runtime and SDK installers for .NET 5.0 and .NET Core 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="38e35-190">Vorherige Versionen wurden nicht notarisiert.</span><span class="sxs-lookup"><span data-stu-id="38e35-190">Prior released versions aren't notarized.</span></span> <span data-ttu-id="38e35-191">Wenn Sie eine nicht notarisierte App ausführen, wird eine Fehlermeldung ähnlich der folgenden Abbildung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="38e35-191">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![macOS Catalina-Notarisierungswarnung](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="38e35-193">Weitere Informationen dazu, wie sich die erzwungene Notarisierung auf .NET (und Ihre .NET-Apps) auswirkt, finden Sie unter [macOS Catalina-Notarisierung und die Auswirkungen auf .NET Core-Downloads und -Projekte](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="38e35-193">For more information about how enforced-notarization affects .NET (and your .NET apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="38e35-194">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="38e35-194">libgdiplus</span></span>

<span data-ttu-id="38e35-195">Für .NET-Anwendungen, die die Assembly *System.Drawing.Common* verwenden, muss libgdiplus installiert sein.</span><span class="sxs-lookup"><span data-stu-id="38e35-195">.NET applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="38e35-196">Eine einfache Möglichkeit zum Abrufen von libgdiplus bietet der [Homebrew](https://brew.sh/)-Paket-Manager („brew“) für macOS.</span><span class="sxs-lookup"><span data-stu-id="38e35-196">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="38e35-197">Installieren Sie nach der Installation von *brew* libgdiplus durch Ausführen der folgenden Befehle in einem Terminal (Befehl):</span><span class="sxs-lookup"><span data-stu-id="38e35-197">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a><span data-ttu-id="38e35-198">Installieren mit einem Installer</span><span class="sxs-lookup"><span data-stu-id="38e35-198">Install with an installer</span></span>

<span data-ttu-id="38e35-199">macOS verfügt über eigenständige Installationsprogramme, die zur Installation des .NET 5.0 SDK verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="38e35-199">macOS has standalone installers that can be used to install the .NET 5.0 SDK:</span></span>

- [<span data-ttu-id="38e35-200">x64-CPUs (64 Bit)</span><span class="sxs-lookup"><span data-stu-id="38e35-200">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/5.0)

## <a name="download-and-manually-install"></a><span data-ttu-id="38e35-201">Herunterladen und manuelles Installieren</span><span class="sxs-lookup"><span data-stu-id="38e35-201">Download and manually install</span></span>

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="38e35-202">Alternativ zu den macOS-Installationsprogrammen für .NET können Sie das SDK und die Runtime herunterladen und manuell installieren.</span><span class="sxs-lookup"><span data-stu-id="38e35-202">As an alternative to the macOS installers for .NET, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="38e35-203">Die manuelle Installation wird normalerweise im Rahmen von CI-Tests (Continuous Integration) durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="38e35-203">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="38e35-204">Für Entwickler oder Benutzer eignet sich in der Regel die Verwendung eines [Installationsprogramms](https://dotnet.microsoft.com/download/dotnet-core) besser.</span><span class="sxs-lookup"><span data-stu-id="38e35-204">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="38e35-205">Wenn Sie das .NET SDK installieren, müssen Sie die entsprechende Runtime nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="38e35-205">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="38e35-206">Laden Sie zunächst entweder für das SDK oder die Runtime eine **binäre** Version auf einer der folgenden Websites herunter:</span><span class="sxs-lookup"><span data-stu-id="38e35-206">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="38e35-207">✔️ [.NET 5.0-Downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="38e35-207">✔️ [.NET 5.0 downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="38e35-208">✔️ [.NET Core 3.1 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="38e35-208">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="38e35-209">✔️ [.NET Core 2.1 herunterladen](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="38e35-209">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="38e35-210">Alle .NET Core-Downloads</span><span class="sxs-lookup"><span data-stu-id="38e35-210">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="38e35-211">Extrahieren Sie als Nächstes die heruntergeladene Datei, und führen Sie den Befehl `export` aus, um von .NET verwendete Variablen festzulegen. Stellen Sie anschließend sicher, dass sich .NET in PATH befindet.</span><span class="sxs-lookup"><span data-stu-id="38e35-211">Next, extract the downloaded file and use the `export` command to set variables used by .NET and then ensure .NET is in PATH.</span></span>

<span data-ttu-id="38e35-212">Laden Sie zunächst ein binäres .NET-Release herunter, um die Runtime zu extrahieren und die .NET-CLI-Befehle im Terminal bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="38e35-212">To extract the runtime and make the .NET CLI commands available at the terminal, first download a .NET binary release.</span></span> <span data-ttu-id="38e35-213">Öffnen Sie dann ein Terminal, und führen Sie die folgenden Befehle im Verzeichnis aus, in dem die Datei gespeichert wurde.</span><span class="sxs-lookup"><span data-stu-id="38e35-213">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="38e35-214">Je nachdem, was Sie heruntergeladen haben, kann der Name der Archivdatei abweichen.</span><span class="sxs-lookup"><span data-stu-id="38e35-214">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="38e35-215">**Verwenden Sie den folgenden Befehl, um die Runtime zu extrahieren:**</span><span class="sxs-lookup"><span data-stu-id="38e35-215">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-5.0.0-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="38e35-216">**Verwenden Sie den folgenden Befehl, um das SDK zu extrahieren:**</span><span class="sxs-lookup"><span data-stu-id="38e35-216">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-5.0.100-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="38e35-217">Mit den oben aufgeführten `export`-Befehlen werden nur die .NET-CLI-Befehle für die Terminalsitzung bereitgestellt, in der sie ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="38e35-217">The preceding `export` commands only make the .NET CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="38e35-218">Sie können Ihr Shell-Profil bearbeiten, um diese Befehle dauerhaft hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="38e35-218">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="38e35-219">Für Linux sind verschiedene Shells verfügbar, die jeweils über ein anderes Profil verfügen.</span><span class="sxs-lookup"><span data-stu-id="38e35-219">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="38e35-220">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="38e35-220">For example:</span></span>
>
> - <span data-ttu-id="38e35-221">**Bash-Shell**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="38e35-221">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="38e35-222">**Korn-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="38e35-222">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="38e35-223">**Z-Shell**: *~/.kshrc* oder *.profile*</span><span class="sxs-lookup"><span data-stu-id="38e35-223">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="38e35-224">Bearbeiten Sie die geeignete Quelldatei für die Shell, und fügen Sie `:$HOME/dotnet` am Ende der vorhandenen `PATH`-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="38e35-224">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="38e35-225">Wenn keine `PATH`-Anweisung enthalten ist, fügen Sie eine neue Zeile mit `export PATH=$PATH:$HOME/dotnet` hinzu.</span><span class="sxs-lookup"><span data-stu-id="38e35-225">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="38e35-226">Fügen Sie außerdem `export DOTNET_ROOT=$HOME/dotnet` am Ende der Datei hinzu.</span><span class="sxs-lookup"><span data-stu-id="38e35-226">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="38e35-227">Bei diesem Ansatz können Sie unterschiedliche Versionen an separaten Speicherorten installieren und explizit auswählen, welche Version von welcher Anwendung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="38e35-227">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="38e35-228">Installieren mit Visual Studio für Mac</span><span class="sxs-lookup"><span data-stu-id="38e35-228">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="38e35-229">Visual Studio für Mac installiert das .NET SDK, wenn die **.NET-Workload** ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="38e35-229">Visual Studio for Mac installs the .NET SDK when the **.NET** workload is selected.</span></span> <span data-ttu-id="38e35-230">Informationen zu den ersten Schritten mit der .NET-Entwicklung unter macOS finden Sie unter [Installieren von Visual Studio 2019 für Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="38e35-230">To get started with .NET development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span>

| <span data-ttu-id="38e35-231">.NET SDK-Version</span><span class="sxs-lookup"><span data-stu-id="38e35-231">.NET SDK version</span></span>      | <span data-ttu-id="38e35-232">Visual Studio-Version</span><span class="sxs-lookup"><span data-stu-id="38e35-232">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="38e35-233">5.0</span><span class="sxs-lookup"><span data-stu-id="38e35-233">5.0</span></span>                   | <span data-ttu-id="38e35-234">Visual Studio 2019 für Mac, Version 8.8 oder höher</span><span class="sxs-lookup"><span data-stu-id="38e35-234">Visual Studio 2019 for Mac version 8.8 or higher.</span></span> |
| <span data-ttu-id="38e35-235">3.1</span><span class="sxs-lookup"><span data-stu-id="38e35-235">3.1</span></span>                   | <span data-ttu-id="38e35-236">Visual Studio 2019 für Mac, Version 8.4 oder höher</span><span class="sxs-lookup"><span data-stu-id="38e35-236">Visual Studio 2019 for Mac version 8.4 or higher.</span></span> |
| <span data-ttu-id="38e35-237">2.1</span><span class="sxs-lookup"><span data-stu-id="38e35-237">2.1</span></span>                   | <span data-ttu-id="38e35-238">Visual Studio 2019 für Mac, Version 8.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="38e35-238">Visual Studio 2019 for Mac version 8.0 or higher.</span></span> |

<span data-ttu-id="38e35-239">[![macOS-Feature für Visual Studio 2019 für Mac mit .NET-Workload](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="38e35-239">[![macOS Visual Studio 2019 for Mac with .NET workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="38e35-240">Installieren zusammen mit Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="38e35-240">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="38e35-241">Visual Studio Code ist ein leistungsstarker und einfacher Quellcode-Editor, der auf Ihrem Desktop ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="38e35-241">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="38e35-242">Visual Studio Code ist für Windows, macOS und Linux verfügbar.</span><span class="sxs-lookup"><span data-stu-id="38e35-242">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="38e35-243">Zwar verfügt Visual Studio Code im Gegensatz zu Visual Studio über keine automatisierten .NET-Installationsprogramme, allerdings ist das Hinzufügen der Unterstützung für .NET einfach.</span><span class="sxs-lookup"><span data-stu-id="38e35-243">While Visual Studio Code doesn't come with an automated .NET installer like Visual Studio does, adding .NET support is simple.</span></span>

01. <span data-ttu-id="38e35-244">[Laden Sie Visual Studio Code herunter, und installieren Sie das Tool.](https://code.visualstudio.com/Download)</span><span class="sxs-lookup"><span data-stu-id="38e35-244">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="38e35-245">[Laden Sie das .NET SDK herunter, und installieren Sie es.](https://dotnet.microsoft.com/download/dotnet-core)</span><span class="sxs-lookup"><span data-stu-id="38e35-245">[Download and install the .NET SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="38e35-246">[Installieren Sie die C#-Erweiterung aus dem Visual Studio Code Marketplace.](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)</span><span class="sxs-lookup"><span data-stu-id="38e35-246">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="install-with-bash-automation"></a><span data-ttu-id="38e35-247">Installieren mit Bash-Automatisierung</span><span class="sxs-lookup"><span data-stu-id="38e35-247">Install with bash automation</span></span>

<span data-ttu-id="38e35-248">Die [dotnet-Installationsskripts](../tools/dotnet-install-script.md) werden für die Automatisierung und Installationen der Runtime von nicht-Administratoren verwendet.</span><span class="sxs-lookup"><span data-stu-id="38e35-248">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="38e35-249">Sie können das Skript über die Seite [dotnet-install-Skriptverweis](../tools/dotnet-install-script.md) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="38e35-249">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="38e35-250">Das Skript installiert standardmäßig die aktuelle Version von [LTS (Long-Term Support)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), die derzeit .NET 3.1 entspricht.</span><span class="sxs-lookup"><span data-stu-id="38e35-250">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET 3.1.</span></span> <span data-ttu-id="38e35-251">Sie können eine bestimmte Version durch Angeben der `current`-Option auswählen.</span><span class="sxs-lookup"><span data-stu-id="38e35-251">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="38e35-252">Schließen Sie die `runtime`-Option mit ein, um eine Runtime zu installieren.</span><span class="sxs-lookup"><span data-stu-id="38e35-252">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="38e35-253">Andernfalls installiert das Skript das [SDK](./windows.md) nicht.</span><span class="sxs-lookup"><span data-stu-id="38e35-253">Otherwise, the script installs the [SDK](./windows.md).</span></span>

```bash
./dotnet-install.sh --channel 5.0 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="38e35-254">Durch den obigen Befehl wird die ASP.NET Core-Runtime für maximale Kompatibilität installiert.</span><span class="sxs-lookup"><span data-stu-id="38e35-254">The previous command installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="38e35-255">Die ASP.NET Core-Runtime enthält auch die .NET-Standardruntime.</span><span class="sxs-lookup"><span data-stu-id="38e35-255">The ASP.NET Core runtime also includes the standard .NET runtime.</span></span>

## <a name="docker"></a><span data-ttu-id="38e35-256">Docker</span><span class="sxs-lookup"><span data-stu-id="38e35-256">Docker</span></span>

<span data-ttu-id="38e35-257">Container bieten eine einfache Möglichkeit, Ihre Anwendung vom Rest des Hostsystems zu isolieren.</span><span class="sxs-lookup"><span data-stu-id="38e35-257">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="38e35-258">Container auf demselben Computer teilen nur den Kernel und verwenden die Ihrer Anwendung zur Verfügung gestellten Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="38e35-258">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="38e35-259">.NET kann in einem Docker-Container ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="38e35-259">.NET can run in a Docker container.</span></span> <span data-ttu-id="38e35-260">Offizielle Docker-Images für .NET werden in Microsoft Container Registry (MCR) veröffentlicht und sind im [Microsoft.NET Core Docker-Hub-Repository](https://hub.docker.com/_/microsoft-dotnet/) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="38e35-260">Official .NET Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet/).</span></span> <span data-ttu-id="38e35-261">Jedes Repository enthält Images für verschiedene Kombinationen von .NET (SDK oder Runtime) und dem Betriebssystem, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="38e35-261">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="38e35-262">Microsoft stellt Images bereit, die auf bestimmte Szenarien zugeschnitten sind.</span><span class="sxs-lookup"><span data-stu-id="38e35-262">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="38e35-263">So stellt beispielsweise das [ASP.NET Core-Repository](https://hub.docker.com/_/microsoft-dotnet-aspnet) Images bereit, die für die Ausführung von ASP.NET Core-Apps in der Produktion erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="38e35-263">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-aspnet) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="38e35-264">Weitere Informationen zur Verwendung von .NET Core in einem Docker-Container finden Sie unter [Einführung in .NET und Docker](../docker/introduction.md) und [Beispiele](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="38e35-264">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="38e35-265">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="38e35-265">Next steps</span></span>

- <span data-ttu-id="38e35-266">[Überprüfen, ob .NET Core bereits installiert ist](how-to-detect-installed-versions.md?pivots=os-macos)</span><span class="sxs-lookup"><span data-stu-id="38e35-266">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md?pivots=os-macos).</span></span>
- <span data-ttu-id="38e35-267">[Verwenden der macOS Catalina-Notarisierung](macos-notarization-issues.md)</span><span class="sxs-lookup"><span data-stu-id="38e35-267">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="38e35-268">[Tutorial: Erste Schritte unter macOS](../tutorials/with-visual-studio-mac.md)</span><span class="sxs-lookup"><span data-stu-id="38e35-268">[Tutorial: Get started on macOS](../tutorials/with-visual-studio-mac.md).</span></span>
- <span data-ttu-id="38e35-269">[Tutorial: Erstellen einer neuen App mit Visual Studio Code](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="38e35-269">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="38e35-270">[Tutorial: Containerisieren einer .NET Core-App](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="38e35-270">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
