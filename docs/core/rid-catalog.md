---
title: .NET Core Runtime-ID-Katalog (RID)
description: Erfahren Sie mehr über die Runtime-ID (RID) und wie RIDs in .NET Core verwendet werden.
ms.date: 02/22/2019
ms.openlocfilehash: b4e0226afa3f68d7c0d17b19e66489d70b759cf8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733549"
---
# <a name="net-core-rid-catalog"></a><span data-ttu-id="8bd84-103">.NET Core-RID-Katalog</span><span class="sxs-lookup"><span data-stu-id="8bd84-103">.NET Core RID Catalog</span></span>

<span data-ttu-id="8bd84-104">RID ist die Kurzform für *Runtime-ID* (Laufzeitbezeichner).</span><span class="sxs-lookup"><span data-stu-id="8bd84-104">RID is short for *Runtime IDentifier*.</span></span> <span data-ttu-id="8bd84-105">Mithilfe von RID-Werten werden Zielplattformen identifiziert, unter der die Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8bd84-105">RID values are used to identify target platforms where the application runs.</span></span>
<span data-ttu-id="8bd84-106">Sie werden von .NET-Paketen verwendet, um plattformspezifische Ressourcen in NuGet-Paketen darzustellen.</span><span class="sxs-lookup"><span data-stu-id="8bd84-106">They're used by .NET packages to represent platform-specific assets in NuGet packages.</span></span> <span data-ttu-id="8bd84-107">Die folgenden Werte sind Beispiele für RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64` oder `osx.10.12-x64`.</span><span class="sxs-lookup"><span data-stu-id="8bd84-107">The following values are examples of RIDs: `linux-x64`, `ubuntu.14.04-x64`, `win7-x64`, or `osx.10.12-x64`.</span></span>
<span data-ttu-id="8bd84-108">Für die Pakete mit nativen Abhängigkeiten legt die RID fest, auf welchen Plattformen das Paket wiederhergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="8bd84-108">For the packages with native dependencies, the RID designates on which platforms the package can be restored.</span></span>

<span data-ttu-id="8bd84-109">Eine einzelne RID kann im `<RuntimeIdentifier>`-Element Ihrer Projektdatei festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="8bd84-109">A single RID can be set in the `<RuntimeIdentifier>` element of your project file.</span></span> <span data-ttu-id="8bd84-110">Mehrere RIDs können als Liste mit Semikolon als Trennzeichen im `<RuntimeIdentifiers>`-Element der Projektdatei definiert werden.</span><span class="sxs-lookup"><span data-stu-id="8bd84-110">Multiple RIDs can be defined as a semicolon-delimited list in the project file's `<RuntimeIdentifiers>` element.</span></span> <span data-ttu-id="8bd84-111">Sie können auch über die Option `--runtime` mit den folgenden [.NET Core-CLI-Befehlen](./tools/index.md) verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="8bd84-111">They're also used via the `--runtime` option with the following [.NET Core CLI commands](./tools/index.md):</span></span>

- [<span data-ttu-id="8bd84-112">dotnet build</span><span class="sxs-lookup"><span data-stu-id="8bd84-112">dotnet build</span></span>](./tools/dotnet-build.md)
- [<span data-ttu-id="8bd84-113">dotnet clean</span><span class="sxs-lookup"><span data-stu-id="8bd84-113">dotnet clean</span></span>](./tools/dotnet-clean.md)
- [<span data-ttu-id="8bd84-114">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="8bd84-114">dotnet pack</span></span>](./tools/dotnet-pack.md)
- [<span data-ttu-id="8bd84-115">dotnet publish</span><span class="sxs-lookup"><span data-stu-id="8bd84-115">dotnet publish</span></span>](./tools/dotnet-publish.md)
- [<span data-ttu-id="8bd84-116">dotnet restore</span><span class="sxs-lookup"><span data-stu-id="8bd84-116">dotnet restore</span></span>](./tools/dotnet-restore.md)
- [<span data-ttu-id="8bd84-117">dotnet run</span><span class="sxs-lookup"><span data-stu-id="8bd84-117">dotnet run</span></span>](./tools/dotnet-run.md)
- [<span data-ttu-id="8bd84-118">dotnet store</span><span class="sxs-lookup"><span data-stu-id="8bd84-118">dotnet store</span></span>](./tools/dotnet-store.md)

<span data-ttu-id="8bd84-119">RIDs, die konkrete Betriebssysteme darstellen, weisen in der Regel folgendes Muster auf: `[os].[version]-[architecture]-[additional qualifiers]`, wobei:</span><span class="sxs-lookup"><span data-stu-id="8bd84-119">RIDs that represent concrete operating systems usually follow this pattern: `[os].[version]-[architecture]-[additional qualifiers]` where:</span></span>

- <span data-ttu-id="8bd84-120">`[os]` ist der Moniker des Betriebs-/Plattformsystems.</span><span class="sxs-lookup"><span data-stu-id="8bd84-120">`[os]` is the operating/platform system moniker.</span></span> <span data-ttu-id="8bd84-121">Beispielsweise `ubuntu`.</span><span class="sxs-lookup"><span data-stu-id="8bd84-121">For example, `ubuntu`.</span></span>

- <span data-ttu-id="8bd84-122">`[version]` ist die Version des Betriebssystems in Form einer durch Punkte getrennten (`.`) Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="8bd84-122">`[version]` is the operating system version in the form of a dot-separated (`.`) version number.</span></span> <span data-ttu-id="8bd84-123">Beispielsweise `15.10`.</span><span class="sxs-lookup"><span data-stu-id="8bd84-123">For example, `15.10`.</span></span>

  - <span data-ttu-id="8bd84-124">Die Version sollte **keine** Marketingversion sein, da diese häufig mehrere separate Versionen des Betriebssystems mit unterschiedlichen Plattform-API-Oberflächen darstellt.</span><span class="sxs-lookup"><span data-stu-id="8bd84-124">The version **shouldn't** be marketing versions, as they often represent multiple discrete versions of the operating system with varying platform API surface area.</span></span>

- <span data-ttu-id="8bd84-125">`[architecture]` ist die Prozessorarchitektur.</span><span class="sxs-lookup"><span data-stu-id="8bd84-125">`[architecture]` is the processor architecture.</span></span> <span data-ttu-id="8bd84-126">Beispielsweise `x86`, `x64`, `arm` oder `arm64`.</span><span class="sxs-lookup"><span data-stu-id="8bd84-126">For example: `x86`, `x64`, `arm`, or `arm64`.</span></span>

- <span data-ttu-id="8bd84-127">`[additional qualifiers]` differenziert die verschiedenen Plattformen noch stärker.</span><span class="sxs-lookup"><span data-stu-id="8bd84-127">`[additional qualifiers]` further differentiate different platforms.</span></span> <span data-ttu-id="8bd84-128">Beispiel: `aot`.</span><span class="sxs-lookup"><span data-stu-id="8bd84-128">For example: `aot`.</span></span>

## <a name="rid-graph"></a><span data-ttu-id="8bd84-129">RID-Diagramm</span><span class="sxs-lookup"><span data-stu-id="8bd84-129">RID graph</span></span>

<span data-ttu-id="8bd84-130">Das RID-Diagramm oder Runtimefallbackdiagramm ist eine Liste von RIDs, die miteinander kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="8bd84-130">The RID graph or runtime fallback graph is a list of RIDs that are compatible with each other.</span></span> <span data-ttu-id="8bd84-131">Die RIDs werden im Paket [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) definiert.</span><span class="sxs-lookup"><span data-stu-id="8bd84-131">The RIDs are defined in the [Microsoft.NETCore.Platforms](https://www.nuget.org/packages/Microsoft.NETCore.Platforms/) package.</span></span> <span data-ttu-id="8bd84-132">Die Liste der unterstützten RIDs und das RID-Diagramm finden Sie in der Datei [*runtime.json*](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) im `dotnet/runtime`-Repository.</span><span class="sxs-lookup"><span data-stu-id="8bd84-132">You can see the list of supported RIDs and the RID graph in the [*runtime.json*](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file, which is located at the `dotnet/runtime` repository.</span></span> <span data-ttu-id="8bd84-133">In dieser Datei können Sie sehen, dass alle RIDs außer der Basis-RID eine `"#import"`-Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="8bd84-133">In this file, you can see that all RIDs, except for the base one, contain an `"#import"` statement.</span></span> <span data-ttu-id="8bd84-134">Diese Anweisungen geben kompatible RIDs an.</span><span class="sxs-lookup"><span data-stu-id="8bd84-134">These statements indicate compatible RIDs.</span></span>

<span data-ttu-id="8bd84-135">Bei NuGet-Wiederherstellungspaketen wird versucht, eine genaue Übereinstimmung für die angegebene Runtime zu finden.</span><span class="sxs-lookup"><span data-stu-id="8bd84-135">When NuGet restores packages, it tries to find an exact match for the specified runtime.</span></span>
<span data-ttu-id="8bd84-136">Wenn keine genaue Übereinstimmung gefunden wird, durchläuft das NuGet erneut das Diagramm, bis es das System mit der größten Kompatibilität gemäß dem RID-Diagramm findet.</span><span class="sxs-lookup"><span data-stu-id="8bd84-136">If an exact match is not found, NuGet walks back the graph until it finds the closest compatible system according to the RID graph.</span></span>

<span data-ttu-id="8bd84-137">Im Folgenden wird ein Beispiel für den tatsächlichen Eintrag für die `osx.10.12-x64`-RID vorgestellt:</span><span class="sxs-lookup"><span data-stu-id="8bd84-137">The following example is the actual entry for the `osx.10.12-x64` RID:</span></span>

```json
"osx.10.12-x64": {
    "#import": [ "osx.10.12", "osx.10.11-x64" ]
}
```

<span data-ttu-id="8bd84-138">Die oben genannte RID gibt an, dass `osx.10.12-x64``osx.10.11-x64` importiert.</span><span class="sxs-lookup"><span data-stu-id="8bd84-138">The above RID specifies that `osx.10.12-x64` imports `osx.10.11-x64`.</span></span> <span data-ttu-id="8bd84-139">Bei NuGet-Wiederherstellungspaketen wird daher versucht, eine genaue Übereinstimmung für `osx.10.12-x64` im Paket zu finden.</span><span class="sxs-lookup"><span data-stu-id="8bd84-139">So, when NuGet restores packages, it tries to find an exact match for  `osx.10.12-x64` in the package.</span></span> <span data-ttu-id="8bd84-140">Wenn das NuGet die angegebene Runtime nicht finden kann, kann es beispielsweise Wiederherstellungspakete mit den Runtimes `osx.10.11-x64` finden.</span><span class="sxs-lookup"><span data-stu-id="8bd84-140">If NuGet cannot find the specific runtime, it can restore packages that specify `osx.10.11-x64` runtimes, for example.</span></span>

<span data-ttu-id="8bd84-141">Das folgende Beispiel zeigt, wie ein etwas größeres RID-Diagramm auch in der Datei *runtime.json* definiert wird:</span><span class="sxs-lookup"><span data-stu-id="8bd84-141">The following example shows a slightly bigger RID graph also defined in the *runtime.json*  file:</span></span>

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

<span data-ttu-id="8bd84-142">Alle RIDs bilden schließlich wieder den Stamm `any`-RID ab.</span><span class="sxs-lookup"><span data-stu-id="8bd84-142">All RIDs eventually map back to the root `any` RID.</span></span>

<span data-ttu-id="8bd84-143">Es gibt einige Aspekte zu RIDs, die Sie bei der Verwendung bedenken müssen:</span><span class="sxs-lookup"><span data-stu-id="8bd84-143">There are some considerations about RIDs that you have to keep in mind when working with them:</span></span>

- <span data-ttu-id="8bd84-144">RIDs sind **opake Zeichenfolgen** und sollten als Blackboxes behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="8bd84-144">RIDs are **opaque strings** and should be treated as black boxes.</span></span>
- <span data-ttu-id="8bd84-145">Erstellen Sie RIDs nicht programmgesteuert.</span><span class="sxs-lookup"><span data-stu-id="8bd84-145">Don't build RIDs programmatically.</span></span>
- <span data-ttu-id="8bd84-146">Verwenden Sie RIDs, die bereits für die Plattform definiert sind.</span><span class="sxs-lookup"><span data-stu-id="8bd84-146">Use RIDs that are already defined for the platform.</span></span>
- <span data-ttu-id="8bd84-147">Die RIDs müssen spezifisch sein. Leiten Sie daher keine Annahmen anhand des tatsächlichen RID-Werts ab.</span><span class="sxs-lookup"><span data-stu-id="8bd84-147">The RIDs need to be specific, so don't assume anything from the actual RID value.</span></span>

## <a name="using-rids"></a><span data-ttu-id="8bd84-148">Die Verwendung von RIDs</span><span class="sxs-lookup"><span data-stu-id="8bd84-148">Using RIDs</span></span>

<span data-ttu-id="8bd84-149">Um RIDs verwenden zu können, müssen Sie wissen, welche RIDs es gibt.</span><span class="sxs-lookup"><span data-stu-id="8bd84-149">To be able to use RIDs, you have to know which RIDs exist.</span></span> <span data-ttu-id="8bd84-150">Zur Plattform werden regelmäßig neue Werte hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8bd84-150">New values are added regularly to the platform.</span></span>
<span data-ttu-id="8bd84-151">Prüfen Sie die Datei [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) im `dotnet/runtime`-Repository auf die neueste und vollständige Version.</span><span class="sxs-lookup"><span data-stu-id="8bd84-151">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span>

<span data-ttu-id="8bd84-152">Mit dem .NET Core 2.0 SDK wird das Konzept von portablen RIDs eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8bd84-152">.NET Core 2.0 SDK introduces the concept of portable RIDs.</span></span> <span data-ttu-id="8bd84-153">Dabei handelt es sich um neue zum RID-Diagramm hinzugefügte Werte, die nicht an eine bestimmte Version oder Betriebssystemverteilung gebunden und die bevorzugte Wahl bei der Verwendung von .NET Core 2.0 und höher sind.</span><span class="sxs-lookup"><span data-stu-id="8bd84-153">They are new values added to the RID graph that aren't tied to a specific version or OS distribution and are the preferred choice when using .NET Core 2.0 and higher.</span></span> <span data-ttu-id="8bd84-154">Sie sind besonders nützlich beim Umgang mit mehreren Linux-Distributionen, da die meisten Distributions-RIDs portable RIDs sind.</span><span class="sxs-lookup"><span data-stu-id="8bd84-154">They're particularly useful when dealing with multiple Linux distros since most distribution RIDs are mapped to the portable RIDs.</span></span>

<span data-ttu-id="8bd84-155">Die folgende Liste enthält eine kleine Untergruppe der am häufigsten verwendeten RIDs für jedes Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="8bd84-155">The following list shows a small subset of the most common RIDs used for each OS.</span></span>

## <a name="windows-rids"></a><span data-ttu-id="8bd84-156">RIDs für Windows</span><span class="sxs-lookup"><span data-stu-id="8bd84-156">Windows RIDs</span></span>

<span data-ttu-id="8bd84-157">Nur allgemeine Werte werden aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8bd84-157">Only common values are listed.</span></span> <span data-ttu-id="8bd84-158">Prüfen Sie die Datei [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) im `dotnet/runtime`-Repository auf die neueste und vollständige Version.</span><span class="sxs-lookup"><span data-stu-id="8bd84-158">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on `dotnet/runtime` repository.</span></span>

- <span data-ttu-id="8bd84-159">Portabel (.NET Core 2.0 oder höher)</span><span class="sxs-lookup"><span data-stu-id="8bd84-159">Portable (.NET Core 2.0 or later versions)</span></span>
  - `win-x64`
  - `win-x86`
  - `win-arm`
  - `win-arm64`
- <span data-ttu-id="8bd84-160">Windows 7 / Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="8bd84-160">Windows 7 / Windows Server 2008 R2</span></span>
  - `win7-x64`
  - `win7-x86`
- <span data-ttu-id="8bd84-161">Windows 8.1 / Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="8bd84-161">Windows 8.1 / Windows Server 2012 R2</span></span>
  - `win81-x64`
  - `win81-x86`
  - `win81-arm`
- <span data-ttu-id="8bd84-162">Windows 10 / Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="8bd84-162">Windows 10 / Windows Server 2016</span></span>
  - `win10-x64`
  - `win10-x86`
  - `win10-arm`
  - `win10-arm64`

<span data-ttu-id="8bd84-163">Weitere Informationen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="8bd84-163">See [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-windows) for more information.</span></span>

## <a name="linux-rids"></a><span data-ttu-id="8bd84-164">RIDs für Linux</span><span class="sxs-lookup"><span data-stu-id="8bd84-164">Linux RIDs</span></span>

<span data-ttu-id="8bd84-165">Nur allgemeine Werte werden aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8bd84-165">Only common values are listed.</span></span> <span data-ttu-id="8bd84-166">Prüfen Sie die Datei [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) im `dotnet/runtime`-Repository auf die neueste und vollständige Version.</span><span class="sxs-lookup"><span data-stu-id="8bd84-166">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span> <span data-ttu-id="8bd84-167">Geräte, die unter einer nicht aufgeführten Distribution ausgeführt werden, funktionieren möglicherweise mit einem der portablen RIDs.</span><span class="sxs-lookup"><span data-stu-id="8bd84-167">Devices running a distribution not listed below may work with one of the Portable RIDs.</span></span> <span data-ttu-id="8bd84-168">Beispielsweise können Raspberry Pi-Geräte, die unter einer nicht aufgeführten Linux-Distribution ausgeführt werden, mit `linux-arm` erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="8bd84-168">For example, Raspberry Pi devices running a Linux distribution not listed can be targeted with `linux-arm`.</span></span>

- <span data-ttu-id="8bd84-169">Portabel (.NET Core 2.0 oder höher)</span><span class="sxs-lookup"><span data-stu-id="8bd84-169">Portable (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="8bd84-170">`linux-x64` (Die meisten Desktopdistributionen wie CentOS, Debian, Fedora, Ubuntu und Ableitungen)</span><span class="sxs-lookup"><span data-stu-id="8bd84-170">`linux-x64` (Most desktop distributions like CentOS, Debian, Fedora, Ubuntu and derivatives)</span></span>
  - <span data-ttu-id="8bd84-171">`linux-musl-x64` (Einfache Distributionen mit [musl](https://wiki.musl-libc.org/projects-using-musl.html) wie Alpine Linux)</span><span class="sxs-lookup"><span data-stu-id="8bd84-171">`linux-musl-x64` (Lightweight distributions using [musl](https://wiki.musl-libc.org/projects-using-musl.html) like Alpine Linux)</span></span>
  - <span data-ttu-id="8bd84-172">`linux-arm` (Linux-Distributionen wie Raspberry Pi, die auf ARM ausgeführt werden)</span><span class="sxs-lookup"><span data-stu-id="8bd84-172">`linux-arm` (Linux distributions running on ARM like Raspberry Pi)</span></span>
- <span data-ttu-id="8bd84-173">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="8bd84-173">Red Hat Enterprise Linux</span></span>
  - <span data-ttu-id="8bd84-174">`rhel-x64` (Ersetzt durch `linux-x64` für RHEL ab Version 6)</span><span class="sxs-lookup"><span data-stu-id="8bd84-174">`rhel-x64` (Superseded by `linux-x64` for RHEL above version 6)</span></span>
  - <span data-ttu-id="8bd84-175">`rhel.6-x64` (.NET Core 2.0 oder höher)</span><span class="sxs-lookup"><span data-stu-id="8bd84-175">`rhel.6-x64` (.NET Core 2.0 or later versions)</span></span>
- <span data-ttu-id="8bd84-176">Tizen (.NET Core 2.0 oder höher)</span><span class="sxs-lookup"><span data-stu-id="8bd84-176">Tizen (.NET Core 2.0 or later versions)</span></span>
  - `tizen`
  - `tizen.4.0.0`
  - `tizen.5.0.0`

<span data-ttu-id="8bd84-177">Weitere Informationen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](install/dependencies.md?tabs=netcore30&pivots=os-linux).</span><span class="sxs-lookup"><span data-stu-id="8bd84-177">See [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-linux) for more information.</span></span>

## <a name="macos-rids"></a><span data-ttu-id="8bd84-178">Relative IDs für macOS</span><span class="sxs-lookup"><span data-stu-id="8bd84-178">macOS RIDs</span></span>

<span data-ttu-id="8bd84-179">Relative IDs für macOS verwenden das ältere Branding „OSX“.</span><span class="sxs-lookup"><span data-stu-id="8bd84-179">macOS RIDs use the older "OSX" branding.</span></span> <span data-ttu-id="8bd84-180">Nur allgemeine Werte werden aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="8bd84-180">Only common values are listed.</span></span> <span data-ttu-id="8bd84-181">Prüfen Sie die Datei [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) im `dotnet/runtime`-Repository auf die neueste und vollständige Version.</span><span class="sxs-lookup"><span data-stu-id="8bd84-181">For the latest and complete version, see the [runtime.json](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/runtime.json) file on the `dotnet/runtime` repository.</span></span>

- <span data-ttu-id="8bd84-182">Portabel (.NET Core 2.0 oder höher)</span><span class="sxs-lookup"><span data-stu-id="8bd84-182">Portable (.NET Core 2.0 or later versions)</span></span>
  - <span data-ttu-id="8bd84-183">`osx-x64` (Mindestversion des Betriebssystems ist macOS 10.12 Sierra)</span><span class="sxs-lookup"><span data-stu-id="8bd84-183">`osx-x64` (Minimum OS version is macOS 10.12 Sierra)</span></span>
- <span data-ttu-id="8bd84-184">macOS 10.10  Yosemite</span><span class="sxs-lookup"><span data-stu-id="8bd84-184">macOS 10.10  Yosemite</span></span>
  - `osx.10.10-x64`
- <span data-ttu-id="8bd84-185">macOS 10.11 El Capitan</span><span class="sxs-lookup"><span data-stu-id="8bd84-185">macOS 10.11 El Capitan</span></span>
  - `osx.10.11-x64`
- <span data-ttu-id="8bd84-186">macOS 10.12 Sierra (.NET Core 1.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="8bd84-186">macOS 10.12 Sierra (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.12-x64`
- <span data-ttu-id="8bd84-187">macOS 10.13 Sierra (.NET Core 1.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="8bd84-187">macOS 10.13 High Sierra (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.13-x64`
- <span data-ttu-id="8bd84-188">macOS 10.14 Mojave (.NET Core 1.1 oder höher)</span><span class="sxs-lookup"><span data-stu-id="8bd84-188">macOS 10.14 Mojave (.NET Core 1.1 or later versions)</span></span>
  - `osx.10.14-x64`

<span data-ttu-id="8bd84-189">Weitere Informationen finden Sie unter [.NET Core-Abhängigkeiten und -Anforderungen](install/dependencies.md?tabs=netcore30&pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="8bd84-189">See [.NET Core dependencies and requirements](install/dependencies.md?tabs=netcore30&pivots=os-macos) for more information.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bd84-190">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bd84-190">See also</span></span>

- [<span data-ttu-id="8bd84-191">Runtime-IDs</span><span class="sxs-lookup"><span data-stu-id="8bd84-191">Runtime IDs</span></span>](https://github.com/dotnet/runtime/blob/master/src/libraries/pkg/Microsoft.NETCore.Platforms/readme.md)
