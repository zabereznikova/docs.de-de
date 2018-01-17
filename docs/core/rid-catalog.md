---
title: .NET Core Runtime-ID-Katalog (RID)
description: "Erfahren Sie mehr über die Runtime-ID (RID) und wie RIDs in .NET Core verwendet werden."
author: mairaw
ms.author: mairaw
ms.date: 09/07/2017
ms.topic: article
ms.prod: .net-core
ms.workload: dotnetcore
ms.openlocfilehash: 180aac7635746f9ede146c3e561deb9bba9a61ab
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="47269-103">.NET Core-RID-Katalog</span><span class="sxs-lookup"><span data-stu-id="47269-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="47269-104">RID ist die Kurzform für *Runtime-ID* (Laufzeitbezeichner).</span><span class="sxs-lookup"><span data-stu-id="47269-104">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="47269-105">Mithilfe von RID-Werten werden Zielplattformen identifiziert, unter der die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="47269-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="47269-106">Sie werden von .NET-Paketen verwendet, um plattformspezifische Ressourcen in NuGet-Paketen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="47269-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="47269-107">Die folgenden Werte sind Beispiele für RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64` oder `osx.10.12-x64`.</span><span class="sxs-lookup"><span data-stu-id="47269-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="47269-108">Für die Pakete mit nativen Abhängigkeiten legt die RID fest, auf welchen Plattformen das Paket wiederhergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="47269-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="47269-109">RIDs können im `<RuntimeIdentifier>`-Element der Projektdatei festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="47269-109">RIDs can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="47269-110">Sie können auch über die Option `--runtime` mit den folgenden [.NET Core-CLI-Befehlen](./tools/index.md) verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="47269-110">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="47269-111">dotnet build</span><span class="sxs-lookup"><span data-stu-id="47269-111">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="47269-112">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="47269-112">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="47269-113">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="47269-113">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="47269-114">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="47269-114">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="47269-115">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="47269-115">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="47269-116">dotnet run</span><span class="sxs-lookup"><span data-stu-id="47269-116">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="47269-117">dotnet store</span><span class="sxs-lookup"><span data-stu-id="47269-117">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="47269-118">RIDs, die konkrete Betriebssysteme darstellen, weisen in der Regel folgendes Muster auf: `[os].[version]-[architecture]-[additional qualifiers]`, wobei:</span><span class="sxs-lookup"><span data-stu-id="47269-118">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="47269-119">`[os]` ist der Moniker des Betriebs-/Plattformsystems.</span><span class="sxs-lookup"><span data-stu-id="47269-119">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="47269-120">Beispielsweise `ubuntu`.</span><span class="sxs-lookup"><span data-stu-id="47269-120">For example, `ubuntu`.</span></span>

- <span data-ttu-id="47269-121">`[version]` ist die Version des Betriebssystems in Form einer durch Punkte getrennten (`.`) Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="47269-121">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="47269-122">Beispielsweise `15.10`.</span><span class="sxs-lookup"><span data-stu-id="47269-122">For example, `15.10`.</span></span>

  - <span data-ttu-id="47269-123">Die Version sollte **keine** Marketingversion sein, da diese häufig mehrere separate Versionen des Betriebssystems mit unterschiedlichen Plattform-API-Oberflächen darstellt.</span><span class="sxs-lookup"><span data-stu-id="47269-123">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="47269-124">`[architecture]` ist die Prozessorarchitektur.</span><span class="sxs-lookup"><span data-stu-id="47269-124">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="47269-125">Beispielsweise `x86`, `x64`, `arm` oder `arm64`.</span><span class="sxs-lookup"><span data-stu-id="47269-125">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="47269-126">`[additional qualifiers]` differenziert die verschiedenen Plattformen noch stärker.</span><span class="sxs-lookup"><span data-stu-id="47269-126">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="47269-127">Beispiel: `aot` oder `corert`.</span><span class="sxs-lookup"><span data-stu-id="47269-127">For example: `aot` or `corert`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="47269-128">RID-Diagramm</span><span class="sxs-lookup"><span data-stu-id="47269-128">RID graph</span></span>

<span data-ttu-id="47269-129">Das RID-Diagramm oder Runtimefallbackdiagramm ist eine Liste von RIDs, die miteinander kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="47269-129">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="47269-130">Die RIDs werden im Paket [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) definiert.</span><span class="sxs-lookup"><span data-stu-id="47269-130">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="47269-131">Die Liste der unterstützten RIDs und das RID-Diagramm finden Sie in der Datei [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) im CoreFX-Repository.</span><span class="sxs-lookup"><span data-stu-id="47269-131">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the CoreFX repo.</span></span> <span data-ttu-id="47269-132">In dieser Datei können Sie sehen, dass alle RIDs außer der Basis-RID eine `"#import"`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="47269-132">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="47269-133">Diese Anweisungen geben kompatible RIDs an.</span><span class="sxs-lookup"><span data-stu-id="47269-133">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="47269-134">Bei NuGet-Wiederherstellungspaketen wird versucht, eine genaue Übereinstimmung für die angegebene Runtime zu finden.</span><span class="sxs-lookup"><span data-stu-id="47269-134">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="47269-135">Wenn keine genaue Übereinstimmung gefunden wird, durchläuft das NuGet erneut das Diagramm, bis es das System mit der größten Kompatibilität gemäß dem RID-Diagramm findet.</span><span class="sxs-lookup"><span data-stu-id="47269-135">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="47269-136">Im Folgenden wird ein Beispiel für den tatsächlichen Eintrag für die `osx.10.12-x64`-RID vorgestellt:</span><span class="sxs-lookup"><span data-stu-id="47269-136">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="47269-137">Die oben genannte RID gibt an, dass `osx.10.12-x64` `osx.10.11-x64` importiert.</span><span class="sxs-lookup"><span data-stu-id="47269-137">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="47269-138">Bei NuGet-Wiederherstellungspaketen wird daher versucht, eine genaue Übereinstimmung für `osx.10.12-x64` im Paket zu finden.</span><span class="sxs-lookup"><span data-stu-id="47269-138">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="47269-139">Wenn das NuGet die angegebene Runtime nicht finden kann, kann es beispielsweise Wiederherstellungspakete mit den Runtimes `osx.10.11-x64` finden.</span><span class="sxs-lookup"><span data-stu-id="47269-139">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="47269-140">Das folgende Beispiel zeigt, wie ein etwas größeres RID-Diagramm auch in der Datei *runtime.json* definiert wird:</span><span class="sxs-lookup"><span data-stu-id="47269-140">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

```
    win7-x64    win7-x86
       |   \   /    |
       |   win7     |
       |     |      |
    win-x64  |  win-x86
          \  |  /
            win
             |
            any
```

<span data-ttu-id="47269-141">Alle RIDs bilden schließlich wieder den Stamm `any`-RID ab.</span><span class="sxs-lookup"><span data-stu-id="47269-141">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="47269-142">Es gibt einige Aspekte zu RIDs, die Sie bei der Verwendung bedenken müssen:</span><span class="sxs-lookup"><span data-stu-id="47269-142">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="47269-143">RIDs sind **opake Zeichenfolgen** und sollten als Blackboxes behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="47269-143">RIDs are **opaque strings** and should be treated as black boxes.</span></span>
- <span data-ttu-id="47269-144">Erstellen Sie RIDs nicht programmgesteuert.</span><span class="sxs-lookup"><span data-stu-id="47269-144">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="47269-145">Verwenden Sie RIDs, die bereits für die Plattform definiert sind.</span><span class="sxs-lookup"><span data-stu-id="47269-145">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="47269-146">Die RIDs müssen spezifisch sein. Leiten Sie daher keine Annahmen anhand des tatsächlichen RID-Werts ab.</span><span class="sxs-lookup"><span data-stu-id="47269-146">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="47269-147">Die Verwendung von RIDs</span><span class="sxs-lookup"><span data-stu-id="47269-147">Using RIDs</span></span>

<span data-ttu-id="47269-148">Um RIDs verwenden zu können, müssen Sie wissen, welche RIDs es gibt.</span><span class="sxs-lookup"><span data-stu-id="47269-148">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="47269-149">Zur Plattform werden regelmäßig neue Werte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="47269-149">New values are added regularly to the platform.</span></span>
<span data-ttu-id="47269-150">Prüfen Sie die Datei [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) im CoreFX-Repository auf die neueste und vollständige Version.</span><span class="sxs-lookup"><span data-stu-id="47269-150">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/runtime.json) file on CoreFX repo.</span></span>

<span data-ttu-id="47269-151">Mit dem .NET Core 2.0 SDK wird das Konzept von portablen RIDs eingeführt.</span><span class="sxs-lookup"><span data-stu-id="47269-151">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="47269-152">Dabei handelt es sich um neue zum RID-Diagramm hinzugefügte Werte, die nicht an eine bestimmte Version oder Betriebssystemverteilung gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="47269-152">They are new values added to the RID graph that aren't tied to a specific version or OS distribution.</span></span> <span data-ttu-id="47269-153">Diese sind besonders bei mehreren Linux-Verteilungen nützlich.</span><span class="sxs-lookup"><span data-stu-id="47269-153">They're particularly useful when dealing with multiple Linux distros.</span></span>

<span data-ttu-id="47269-154">Die folgende Liste enthält die am häufigsten verwendeten RIDs für jedes Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="47269-154">The following list shows the most common RIDs used for each OS.</span></span> <span data-ttu-id="47269-155">Die Werte `arm` oder `corert` werden nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="47269-155">It doesn't cover `arm` or `corert` values.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="47269-156">RIDs für Windows</span><span class="sxs-lookup"><span data-stu-id="47269-156">Windows RIDs</span></span>

- <span data-ttu-id="47269-157">Portabel</span><span class="sxs-lookup"><span data-stu-id="47269-157">Portable</span></span>
  - `win-x86`
  - `win-x64`
- <span data-ttu-id="47269-158">Windows 7 / Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="47269-158">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="47269-159">Windows 8 / Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="47269-159">Windows 8 / Windows Server 2012</span></span>
  - `win8-x64`
  - `win8-x86`
  - `win8-arm`
- <span data-ttu-id="47269-160">Windows 8.1 / Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="47269-160">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="47269-161">Windows 10 / Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="47269-161">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="47269-162">Weitere Informationen finden Sie unter [Prerequisites for .NET Core on Mac (Erforderliche Komponenten für .NET Core unter Mac)](windows-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="47269-162">See [Prerequisites for .NET Core on Windows](windows-prerequisites.md) for more information.</span></span>

## <a name="linux-rids"></a><span data-ttu-id="47269-163">RIDs für Linux</span><span class="sxs-lookup"><span data-stu-id="47269-163">Linux RIDs</span></span>

- <span data-ttu-id="47269-164">Portabel</span><span class="sxs-lookup"><span data-stu-id="47269-164">Portable</span></span>
  - `linux-x64`
- <span data-ttu-id="47269-165">CentOS</span><span class="sxs-lookup"><span data-stu-id="47269-165">CentOS</span></span>
  - `centos-x64`
  - `centos.7-x64`
- <span data-ttu-id="47269-166">Debian</span><span class="sxs-lookup"><span data-stu-id="47269-166">Debian</span></span>
  - `debian-x64`
  - `debian.8-x64`
- <span data-ttu-id="47269-167">Fedora</span><span class="sxs-lookup"><span data-stu-id="47269-167">Fedora</span></span>
  - `fedora-x64`
  - `fedora.24-x64`
  - <span data-ttu-id="47269-168">`fedora.25-x64` (.NET Core 2.0 oder höher)</span><span class="sxs-lookup"><span data-stu-id="47269-168">`fedora.25-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="47269-169">`fedora.26-x64` (.NET Core 2.0 oder höher)</span><span class="sxs-lookup"><span data-stu-id="47269-169">`fedora.26-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="47269-170">Gentoo (.NET Core 2.0 oder höher)</span><span class="sxs-lookup"><span data-stu-id="47269-170">Gentoo (.NET Core 2.0 or later versions)</span></span>
  - `gentoo-x64`
- <span data-ttu-id="47269-171">openSUSE</span><span class="sxs-lookup"><span data-stu-id="47269-171">openSUSE</span></span>
  - `opensuse-x64`
  - `opensuse.42.1-x64`
- <span data-ttu-id="47269-172">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="47269-172">Oracle Linux</span></span>
  - `ol-x64`
  - `ol.7-x64`
  - `ol.7.0-x64`
  - `ol.7.1-x64`
  - `ol.7.2-x64`
- <span data-ttu-id="47269-173">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="47269-173">Red Hat Enterprise Linux</span></span>
  - `rhel-x64`
  - <span data-ttu-id="47269-174">`rhel.6-x64` (.NET Core 2.0 oder höher)</span><span class="sxs-lookup"><span data-stu-id="47269-174">`rhel.6-x64` (.NET Core 2.0 or later versions)</span></span>
  - `rhel.7-x64`
  - `rhel.7.1-x64`
  - `rhel.7.2-x64`
  - <span data-ttu-id="47269-175">`rhel.7.3-x64` (.NET Core 2.0 oder höher)</span><span class="sxs-lookup"><span data-stu-id="47269-175">`rhel.7.3-x64` (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="47269-176">`rhel.7.4-x64` (.NET Core 2.0 oder höher)</span><span class="sxs-lookup"><span data-stu-id="47269-176">`rhel.7.4-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="47269-177">Tizen (.NET Core 2.0 oder höher)</span><span class="sxs-lookup"><span data-stu-id="47269-177">Tizen (.NET Core 2.0 or later versions)</span></span>
  - `tizen`
- <span data-ttu-id="47269-178">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="47269-178">Ubuntu</span></span>
  - `ubuntu-x64`
  - `ubuntu.14.04-x64`
  - `ubuntu.14.10-x64`
  - `ubuntu.15.04-x64`
  - `ubuntu.15.10-x64`
  - `ubuntu.16.04-x64`
  - `ubuntu.16.10-x64`
- <span data-ttu-id="47269-179">Ubuntu-Ableitungen</span><span class="sxs-lookup"><span data-stu-id="47269-179">Ubuntu derivatives</span></span>
  - `linuxmint.17-x64`
  - `linuxmint.17.1-x64`
  - `linuxmint.17.2-x64`
  - `linuxmint.17.3-x64`
  - `linuxmint.18-x64`
  - <span data-ttu-id="47269-180">`linuxmint.18.1-x64` (.NET Core 2.0 oder höher)</span><span class="sxs-lookup"><span data-stu-id="47269-180">`linuxmint.18.1-x64` (.NET Core 2.0 or later versions)</span></span>

<span data-ttu-id="47269-181">Weitere Informationen finden Sie unter [Prerequisites for .NET Core on Linux (Erforderliche Komponenten für .NET Core unter Linux)](linux-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="47269-181">See [Prerequisites for .NET Core on Linux](linux-prerequisites.md) for more information.</span></span>

## <a name="macos-rids"></a><span data-ttu-id="47269-182">Relative IDs für macOS</span><span class="sxs-lookup"><span data-stu-id="47269-182">macOS RIDs</span></span>

<span data-ttu-id="47269-183">Relative IDs für macOS verwenden das ältere Branding „OSX“.</span><span class="sxs-lookup"><span data-stu-id="47269-183">macOS RIDs use the older "OSX" branding.</span></span>

- <span data-ttu-id="47269-184">`osx-x64` (.NET Core 2.0 oder höher, die mindestens erforderliche Version ist `osx.10.12-x64`)</span><span class="sxs-lookup"><span data-stu-id="47269-184">`osx-x64` (.NET Core 2.0 or later versions, minimum version is `osx.10.12-x64`)</span></span>
- `osx.10.10-x64`
- `osx.10.11-x64`
- <span data-ttu-id="47269-185">`osx.10.12-x64` (.NET Core 1.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="47269-185">`osx.10.12-x64` (.NET Core 1.1 or later versions)</span></span>
- `osx.10.13-x64`

<span data-ttu-id="47269-186">Weitere Informationen finden Sie unter [Prerequisites for .NET Core on macOS (Erforderliche Komponenten für .NET Core unter macOS)](macos-prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="47269-186">See [Prerequisites for .NET Core on macOS](macos-prerequisites.md) for more information.</span></span>

## <a name="android-rids-net-core-20-or-later-versions"></a><span data-ttu-id="47269-187">Android-RIDs (.NET Core 2.0 oder höher)</span><span class="sxs-lookup"><span data-stu-id="47269-187">Android RIDs (.NET Core 2.0 or later versions)</span></span>

- `android`
- `android.21`

## <a name="see-also"></a><span data-ttu-id="47269-188">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47269-188">See also</span></span>

[<span data-ttu-id="47269-189">Runtime-IDs</span><span class="sxs-lookup"><span data-stu-id="47269-189">Runtime IDs</span></span>](https://github.com/dotnet/corefx/blob/master/pkg/Microsoft.NETCore.Platforms/readme.md)
