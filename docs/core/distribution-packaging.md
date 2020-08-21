---
title: Verpacken einer Verteilung von .NET Core
description: Erfahren Sie, wie Sie .NET Core für die Verteilung verpacken, benennen und mit einer Versionsnummer versehen.
author: tmds
ms.date: 10/09/2019
ms.openlocfilehash: 3324a6a151fc6dc46a8f13ea17c89da99d108d82
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062885"
---
# <a name="net-core-distribution-packaging"></a><span data-ttu-id="98735-103">Verpacken einer Verteilung von .NET Core</span><span class="sxs-lookup"><span data-stu-id="98735-103">.NET Core distribution packaging</span></span>

<span data-ttu-id="98735-104">Da .NET Core auf immer mehr Plattformen verfügbar wird, ist es hilfreich zu erfahren, wie man es verpackt, benennt und mit einer Versionsnummer versieht.</span><span class="sxs-lookup"><span data-stu-id="98735-104">As .NET Core becomes available on more and more platforms, it's useful to learn how to package, name, and version it.</span></span> <span data-ttu-id="98735-105">Auf diese Weise kann mithilfe von Paketverwaltern eine konsistente Benutzererfahrung sichergestellt werden, unabhängig davon, wo Benutzer .NET ausführen.</span><span class="sxs-lookup"><span data-stu-id="98735-105">This way, package maintainers can help ensure a consistent experience no matter where users choose to run .NET.</span></span> <span data-ttu-id="98735-106">Dieser Artikel ist für Benutzer hilfreich, die</span><span class="sxs-lookup"><span data-stu-id="98735-106">This article is useful for users that are:</span></span>

- <span data-ttu-id="98735-107">versuchen, .NET Core von der Quelle aus zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="98735-107">Attempting to build .NET Core from source.</span></span>
- <span data-ttu-id="98735-108">Änderungen an der .NET Core-CLI vornehmen möchten, die sich auf das resultierende Layout oder die erzeugten Pakete auswirken könnten.</span><span class="sxs-lookup"><span data-stu-id="98735-108">Wanting to make changes to the .NET Core CLI that could impact the resulting layout or packages produced.</span></span>

## <a name="disk-layout"></a><span data-ttu-id="98735-109">Datenträgerlayout</span><span class="sxs-lookup"><span data-stu-id="98735-109">Disk layout</span></span>

<span data-ttu-id="98735-110">.NET Core besteht aus mehreren Komponenten, die im Dateisystem folgendermaßen angeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="98735-110">When installed, .NET Core consists of several components that are laid out as follows in the filesystem:</span></span>

```
{dotnet_root}                                     (*)
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host                                          (*)
│   └── fxr                                       (*)
│       └── <fxr version>        (2)
├── sdk                                           (*)
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)              (*)
├── packs                                         (*)
│   ├── Microsoft.AspNetCore.App.Ref              (*)
│   │   └── <aspnetcore ref version>     (11)
│   ├── Microsoft.NETCore.App.Ref                 (*)
│   │   └── <netcore ref version>        (12)
│   ├── Microsoft.NETCore.App.Host.<rid>          (*)
│   │   └── <apphost version>            (13)
│   ├── Microsoft.WindowsDesktop.App.Ref          (*)
│   │   └── <desktop ref version>        (14)
│   └── NETStandard.Library.Ref                   (*)
│       └── <netstandard version>        (15)
├── shared                                        (*)
│   ├── Microsoft.NETCore.App                     (*)
│   │   └── <runtime version>     (5)
│   ├── Microsoft.AspNetCore.App                  (*)
│   │   └── <aspnetcore version>  (6)
│   ├── Microsoft.AspNetCore.All                  (*)
│   │   └── <aspnetcore version>  (6)
│   └── Microsoft.WindowsDesktop.App              (*)
│       └── <desktop app version> (7)
└── templates                                     (*)
│   └── <templates version>      (17)
/
├── etc/dotnet
│       └── install_location     (16)
├── usr/share/man/man1
│       └── dotnet.1.gz          (9)
└── usr/bin
        └── dotnet               (10)
```

- <span data-ttu-id="98735-111">(1) **dotnet**: Der Host (auch bekannt als „Muxer“) führt zwei unterschiedliche Rollen aus: das Aktivieren einer Runtime, um eine Anwendung zu starten, und das Aktivieren eines SDK, um Befehle an dieses weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="98735-111">(1) **dotnet** The host (also known as the "muxer") has two distinct roles: activate a runtime to launch an application, and activate an SDK to dispatch commands to it.</span></span> <span data-ttu-id="98735-112">Der Host ist eine native ausführbare Datei (`dotnet.exe`).</span><span class="sxs-lookup"><span data-stu-id="98735-112">The host is a native executable (`dotnet.exe`).</span></span>

<span data-ttu-id="98735-113">Es gibt nur einen Host, die meisten anderen Komponenten befinden sich jedoch in Verzeichnissen mit Versionsangabe (2, 3, 5, 6).</span><span class="sxs-lookup"><span data-stu-id="98735-113">While there's a single host, most of the other components are in versioned directories (2,3,5,6).</span></span> <span data-ttu-id="98735-114">Das bedeutet, dass auf dem System mehrere Versionen vorhanden sein können, da sie nebeneinander installiert werden können.</span><span class="sxs-lookup"><span data-stu-id="98735-114">This means multiple versions can be present on the system since they're installed side by side.</span></span>

- <span data-ttu-id="98735-115">(2) **host/fxr/\<fxr version>** : Enthält die vom Host verwendete Frameworkauflösungslogik.</span><span class="sxs-lookup"><span data-stu-id="98735-115">(2) **host/fxr/\<fxr version>** contains the framework resolution logic used by the host.</span></span> <span data-ttu-id="98735-116">Der Host verwendet die neueste installierte hostfxr-Version.</span><span class="sxs-lookup"><span data-stu-id="98735-116">The host uses the latest hostfxr that is installed.</span></span> <span data-ttu-id="98735-117">„hostfxr“ ist für die Auswahl der geeigneten Runtime beim Ausführen einer .NET Core-Anwendung zuständig.</span><span class="sxs-lookup"><span data-stu-id="98735-117">The hostfxr is responsible for selecting the appropriate runtime when executing a .NET Core application.</span></span> <span data-ttu-id="98735-118">Eine Anwendung, die für .NET Core 2.0.0 erstellt wurde, verwendet beispielsweise die Runtime 2.0.5, wenn sie verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="98735-118">For example, an application built for .NET Core 2.0.0 uses the 2.0.5 runtime when it's available.</span></span> <span data-ttu-id="98735-119">Ebenso wählt „hostfxr“ während der Entwicklung das geeignete SDK aus.</span><span class="sxs-lookup"><span data-stu-id="98735-119">Similarly, hostfxr selects the appropriate SDK during development.</span></span>

- <span data-ttu-id="98735-120">(3) **sdk/\<sdk version>** : Bei dem SDK (auch „die Tools“) handelt es sich um mehrere verwaltete Tools, die zum Schreiben und Erstellen von .NET Core-Bibliotheken und -Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="98735-120">(3) **sdk/\<sdk version>** The SDK (also known as "the tooling") is a set of managed tools that are used to write and build .NET Core libraries and applications.</span></span> <span data-ttu-id="98735-121">Das SDK enthält die .NET Core-CLI, die verwalteten Sprachcompiler, MSBuild und zugehörige Buildtasks und -ziele, NuGet, neue Projektvorlagen usw.</span><span class="sxs-lookup"><span data-stu-id="98735-121">The SDK includes the .NET Core CLI, the managed languages compilers, MSBuild, and associated build tasks and targets, NuGet, new project templates, and so on.</span></span>

- <span data-ttu-id="98735-122">(4) **sdk/NuGetFallbackFolder** enthält einen Cache der NuGet-Pakete, die von einem SDK während der Wiederherstellung verwendet werden, etwa bei der Ausführung von `dotnet restore` oder `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="98735-122">(4) **sdk/NuGetFallbackFolder** contains a cache of NuGet packages used by an SDK during the restore operation, such as when running `dotnet restore` or `dotnet build`.</span></span> <span data-ttu-id="98735-123">Dieser Ordner wird nur vor .NET Core 3.0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="98735-123">This folder is only used prior to .NET Core 3.0.</span></span> <span data-ttu-id="98735-124">Er kann nicht aus der Quelle erstellt werden, da er vorgefertigte binäre Ressourcen aus `nuget.org` enthält.</span><span class="sxs-lookup"><span data-stu-id="98735-124">It can't be built from source, because it contains prebuilt binary assets from `nuget.org`.</span></span>

<span data-ttu-id="98735-125">Der Ordner **shared** enthält Frameworks.</span><span class="sxs-lookup"><span data-stu-id="98735-125">The **shared** folder contains frameworks.</span></span> <span data-ttu-id="98735-126">Ein gemeinsames (shared) Framework stellt einen Satz Bibliotheken an einem zentralen Speicherort bereit, sodass diese von verschiedenen Anwendungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="98735-126">A shared framework provides a set of libraries at a central location so they can be used by different applications.</span></span>

- <span data-ttu-id="98735-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** : Dieses Framework enthält die .NET-Runtime und die unterstützenden verwalteten Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="98735-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** This framework contains the .NET Core runtime and supporting managed libraries.</span></span>

- <span data-ttu-id="98735-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** : Enthält die ASP.NET Core-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="98735-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contains the ASP.NET Core libraries.</span></span> <span data-ttu-id="98735-129">Die Bibliotheken unter `Microsoft.AspNetCore.App` werden im Rahmen des .NET Core-Projekts entwickelt und unterstützt.</span><span class="sxs-lookup"><span data-stu-id="98735-129">The libraries under `Microsoft.AspNetCore.App` are developed and supported as part of the .NET Core project.</span></span> <span data-ttu-id="98735-130">Die Bibliotheken unter `Microsoft.AspNetCore.All` sind ein übergeordnetes Set, das auch Drittanbieterbibliotheken enthält.</span><span class="sxs-lookup"><span data-stu-id="98735-130">The libraries under `Microsoft.AspNetCore.All` are a superset that also contains third-party libraries.</span></span>

- <span data-ttu-id="98735-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** : Enthält die Windows-Desktopbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="98735-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** contains the Windows desktop libraries.</span></span> <span data-ttu-id="98735-132">Dies ist nur in Windows enthalten, und nicht in anderen Plattformen.</span><span class="sxs-lookup"><span data-stu-id="98735-132">This isn't included on non-Windows platforms.</span></span>

- <span data-ttu-id="98735-133">(8) **LICENSE.txt,ThirdPartyNotices.txt**: Dies sind die .NET Core-Lizenzen und die Lizenzen von Drittanbieterbibliotheken, die in .NET Core jeweils verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="98735-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** are the .NET Core license and licenses of third-party libraries used in .NET Core, respectively.</span></span>

- <span data-ttu-id="98735-134">(9, 10) **dotnet.1.gz, dotnet**: `dotnet.1.gz` ist die dotnet-Handbuchseite.</span><span class="sxs-lookup"><span data-stu-id="98735-134">(9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` is the dotnet manual page.</span></span> <span data-ttu-id="98735-135">`dotnet` ist eine symbolische Verknüpfung mit dem Dotnet-Host (1).</span><span class="sxs-lookup"><span data-stu-id="98735-135">`dotnet` is a symlink to the dotnet host(1).</span></span> <span data-ttu-id="98735-136">Diese Dateien werden zur Systemintegration an bekannten Speicherorten installiert.</span><span class="sxs-lookup"><span data-stu-id="98735-136">These files are installed at well-known locations for system integration.</span></span>

- <span data-ttu-id="98735-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** beschreibt jeweils die API einer `x.y`-Version von .NET Core und ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="98735-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** describe the API of an `x.y` version of .NET Core and ASP.NET Core respectively.</span></span> <span data-ttu-id="98735-138">Diese Pakete werden bei der Kompilierung für diese Zielversionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="98735-138">These packs are used when compiling for those target versions.</span></span>

- <span data-ttu-id="98735-139">(13) **Microsoft.NETCore.App.Host.\<rid>** :</span><span class="sxs-lookup"><span data-stu-id="98735-139">(13) **Microsoft.NETCore.App.Host.\<rid>**</span></span> <span data-ttu-id="98735-140">Enthält eine native Binärdatei für die Plattform `rid`.</span><span class="sxs-lookup"><span data-stu-id="98735-140">contains a native binary for platform `rid`.</span></span> <span data-ttu-id="98735-141">Diese Binärdatei ist eine Vorlage für das Kompilieren einer .NET Core-Anwendung in eine native Binärdatei für diese Plattform.</span><span class="sxs-lookup"><span data-stu-id="98735-141">This binary is a template when compiling a .NET Core application into a native binary for that platform.</span></span>

- <span data-ttu-id="98735-142">(14) **Microsoft.WindowsDesktop.App.Ref** beschreibt die API der `x.y`-Version von Windows-Desktopanwendungen.</span><span class="sxs-lookup"><span data-stu-id="98735-142">(14) **Microsoft.WindowsDesktop.App.Ref** describes the API of `x.y` version of Windows Desktop applications.</span></span> <span data-ttu-id="98735-143">Diese Dateien werden beim Kompilieren für dieses Ziel verwendet.</span><span class="sxs-lookup"><span data-stu-id="98735-143">These files are used when compiling for that target.</span></span> <span data-ttu-id="98735-144">Dies wird nur unter Windows bereitgestellt, und nicht für andere Plattformen.</span><span class="sxs-lookup"><span data-stu-id="98735-144">This isn't provided on non-Windows platforms.</span></span>

- <span data-ttu-id="98735-145">(15) **NETStandard.Library.Ref** beschreibt die NetStandard-API `x.y`.</span><span class="sxs-lookup"><span data-stu-id="98735-145">(15) **NETStandard.Library.Ref** describes the netstandard `x.y` API.</span></span> <span data-ttu-id="98735-146">Diese Dateien werden beim Kompilieren für dieses Ziel verwendet.</span><span class="sxs-lookup"><span data-stu-id="98735-146">These files are used when compiling for that target.</span></span>

- <span data-ttu-id="98735-147">(16) **/etc/dotnet/install_location** ist eine Datei, die den vollständigen Pfad für `{dotnet_root}` enthält.</span><span class="sxs-lookup"><span data-stu-id="98735-147">(16) **/etc/dotnet/install_location** is a file that contains the full path for `{dotnet_root}`.</span></span> <span data-ttu-id="98735-148">Der Pfad kann mit einem Zeilenvorschubzeichen enden.</span><span class="sxs-lookup"><span data-stu-id="98735-148">The path may end with a newline.</span></span> <span data-ttu-id="98735-149">Es ist nicht erforderlich, diese Datei hinzuzufügen, wenn `/usr/share/dotnet` das Stammverzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="98735-149">It's not necessary to add this file when the root is `/usr/share/dotnet`.</span></span>

- <span data-ttu-id="98735-150">(17) **templates** enthält die Vorlagen, die vom SDK verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="98735-150">(17) **templates** contains the templates used by the SDK.</span></span> <span data-ttu-id="98735-151">Beispielsweise ermittelt `dotnet new` Projektvorlagen in diesem Ordner.</span><span class="sxs-lookup"><span data-stu-id="98735-151">For example, `dotnet new` finds project templates here.</span></span>

<span data-ttu-id="98735-152">Die mit `(*)` markierten Ordner werden von mehreren Paketen verwendet.</span><span class="sxs-lookup"><span data-stu-id="98735-152">The folders marked with `(*)` are used by multiple packages.</span></span> <span data-ttu-id="98735-153">Einige Paketformate (z.B. `rpm`) erfordern eine besondere Verarbeitung solcher Ordner.</span><span class="sxs-lookup"><span data-stu-id="98735-153">Some package formats (for example, `rpm`) require special handling of such folders.</span></span> <span data-ttu-id="98735-154">Der Paketmaintainer muss dafür Sorge tragen.</span><span class="sxs-lookup"><span data-stu-id="98735-154">The package maintainer must take care of this.</span></span>

## <a name="recommended-packages"></a><span data-ttu-id="98735-155">Empfohlene Pakete</span><span class="sxs-lookup"><span data-stu-id="98735-155">Recommended packages</span></span>

<span data-ttu-id="98735-156">Die .NET Core-Versionierung basiert auf dem Versionsnummernmuster `[major].[minor]` der Runtimekomponente.</span><span class="sxs-lookup"><span data-stu-id="98735-156">.NET Core versioning is based on the runtime component `[major].[minor]` version numbers.</span></span>
<span data-ttu-id="98735-157">Die SDK-Version verwendet das gleiche `[major].[minor]`-Muster und weist eine unabhängige `[patch]`-Zeichenfolge auf, die die Feature- und Patchsemantik für das SDK kombiniert.</span><span class="sxs-lookup"><span data-stu-id="98735-157">The SDK version uses the same `[major].[minor]` and has an independent `[patch]` that combines feature and patch semantics for the SDK.</span></span>
<span data-ttu-id="98735-158">Zum Beispiel: Die SDK-Version 2.2.302 ist das zweite Patchrelease des dritten Featurerelease des SDK, das die Runtimeversion 2.2 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="98735-158">For example: SDK version 2.2.302 is the second patch release of the third feature release of the SDK that supports the 2.2 runtime.</span></span> <span data-ttu-id="98735-159">Weitere Informationen zur Funktionsweise der Versionsverwaltung finden Sie unter [.NET Core-Versionskontrolle: Übersicht](./versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="98735-159">For more information about how versioning works, see [.NET Core versioning overview](./versions/index.md).</span></span>

<span data-ttu-id="98735-160">Einige Pakete enthalten einen Teil der Versionsnummer im Namen.</span><span class="sxs-lookup"><span data-stu-id="98735-160">Some of the packages include part of the version number in their name.</span></span> <span data-ttu-id="98735-161">Dies ermöglicht Ihnen, eine bestimmte Version zu installieren.</span><span class="sxs-lookup"><span data-stu-id="98735-161">This allows you to install a specific version.</span></span>
<span data-ttu-id="98735-162">Der Rest der Version ist im Versionsnamen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="98735-162">The rest of the version isn't included in the version name.</span></span> <span data-ttu-id="98735-163">Dies ermöglicht dem Paket-Manager des Betriebssystems, die Pakete zu aktualisieren (z.B. durch automatisches Installieren von Sicherheitsfixes).</span><span class="sxs-lookup"><span data-stu-id="98735-163">This allows the OS package manager to update the packages (for example, automatically installing security fixes).</span></span> <span data-ttu-id="98735-164">Unterstützte Paket-Manager sind Linux-spezifisch.</span><span class="sxs-lookup"><span data-stu-id="98735-164">Supported package managers are Linux specific.</span></span>

<span data-ttu-id="98735-165">Im Folgenden werden die empfohlenen Pakete aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="98735-165">The following lists the recommended packages:</span></span>

- <span data-ttu-id="98735-166">`dotnet-sdk-[major].[minor]`: installiert das neueste SDK für eine spezifische Runtime.</span><span class="sxs-lookup"><span data-stu-id="98735-166">`dotnet-sdk-[major].[minor]` - Installs the latest sdk for specific runtime</span></span>
  - <span data-ttu-id="98735-167">**Version:** \<sdk version></span><span class="sxs-lookup"><span data-stu-id="98735-167">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="98735-168">**Beispiel:** dotnet-sdk-2.1</span><span class="sxs-lookup"><span data-stu-id="98735-168">**Example:** dotnet-sdk-2.1</span></span>
  - <span data-ttu-id="98735-169">**Enthält:** (3), (4)</span><span class="sxs-lookup"><span data-stu-id="98735-169">**Contains:** (3),(4)</span></span>
  - <span data-ttu-id="98735-170">**Abhängigkeiten:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="98735-170">**Dependencies:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span></span>

- <span data-ttu-id="98735-171">`aspnetcore-runtime-[major].[minor]`: installiert eine spezifische ASP.NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="98735-171">`aspnetcore-runtime-[major].[minor]` - Installs a specific ASP.NET Core runtime</span></span>
  - <span data-ttu-id="98735-172">**Version:** \<aspnetcore runtime version></span><span class="sxs-lookup"><span data-stu-id="98735-172">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="98735-173">**Beispiel:** aspnetcore-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="98735-173">**Example:** aspnetcore-runtime-2.1</span></span>
  - <span data-ttu-id="98735-174">**Enthält:** (6)</span><span class="sxs-lookup"><span data-stu-id="98735-174">**Contains:** (6)</span></span>
  - <span data-ttu-id="98735-175">**Abhängigkeiten:** `dotnet-runtime-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="98735-175">**Dependencies:** `dotnet-runtime-[major].[minor]`</span></span>

- <span data-ttu-id="98735-176">`dotnet-runtime-deps-[major].[minor]` _(Optional):_ Installiert die Abhängigkeiten zum Ausführen eigenständiger Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="98735-176">`dotnet-runtime-deps-[major].[minor]` _(Optional)_ - Installs the dependencies for running self-contained applications</span></span>
  - <span data-ttu-id="98735-177">**Version:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="98735-177">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="98735-178">**Beispiel:** dotnet-runtime-deps-2.1</span><span class="sxs-lookup"><span data-stu-id="98735-178">**Example:** dotnet-runtime-deps-2.1</span></span>
  - <span data-ttu-id="98735-179">**Abhängigkeiten:** _Verteilungsspezifische Abhängigkeiten_</span><span class="sxs-lookup"><span data-stu-id="98735-179">**Dependencies:** _distribution-specific dependencies_</span></span>

- <span data-ttu-id="98735-180">`dotnet-runtime-[major].[minor]`: installiert eine spezifische Runtime</span><span class="sxs-lookup"><span data-stu-id="98735-180">`dotnet-runtime-[major].[minor]` - Installs a specific runtime</span></span>
  - <span data-ttu-id="98735-181">**Version:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="98735-181">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="98735-182">**Beispiel:** dotnet-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="98735-182">**Example:** dotnet-runtime-2.1</span></span>
  - <span data-ttu-id="98735-183">**Enthält:** (5)</span><span class="sxs-lookup"><span data-stu-id="98735-183">**Contains:** (5)</span></span>
  - <span data-ttu-id="98735-184">**Abhängigkeiten:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="98735-184">**Dependencies:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`</span></span>

- <span data-ttu-id="98735-185">`dotnet-hostfxr-[major].[minor]`: Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="98735-185">`dotnet-hostfxr-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="98735-186">**Version:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="98735-186">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="98735-187">**Beispiel:** dotnet-hostfxr-3.0</span><span class="sxs-lookup"><span data-stu-id="98735-187">**Example:** dotnet-hostfxr-3.0</span></span>
  - <span data-ttu-id="98735-188">**Enthält:** (2)</span><span class="sxs-lookup"><span data-stu-id="98735-188">**Contains:** (2)</span></span>
  - <span data-ttu-id="98735-189">**Abhängigkeiten:** `dotnet-host`</span><span class="sxs-lookup"><span data-stu-id="98735-189">**Dependencies:** `dotnet-host`</span></span>

- <span data-ttu-id="98735-190">`dotnet-host`: Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="98735-190">`dotnet-host` - dependency</span></span>
  - <span data-ttu-id="98735-191">**Version:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="98735-191">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="98735-192">**Beispiel:** dotnet-host</span><span class="sxs-lookup"><span data-stu-id="98735-192">**Example:** dotnet-host</span></span>
  - <span data-ttu-id="98735-193">**Enthält:** (1),(8),(9),(10),(16)</span><span class="sxs-lookup"><span data-stu-id="98735-193">**Contains:** (1),(8),(9),(10),(16)</span></span>

- <span data-ttu-id="98735-194">`dotnet-apphost-pack-[major].[minor]`: Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="98735-194">`dotnet-apphost-pack-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="98735-195">**Version:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="98735-195">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="98735-196">**Enthält:** (13)</span><span class="sxs-lookup"><span data-stu-id="98735-196">**Contains:** (13)</span></span>

- <span data-ttu-id="98735-197">`dotnet-targeting-pack-[major].[minor]`: ermöglicht eine ältere Runtime als Ziel.</span><span class="sxs-lookup"><span data-stu-id="98735-197">`dotnet-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="98735-198">**Version:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="98735-198">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="98735-199">**Enthält:** (12)</span><span class="sxs-lookup"><span data-stu-id="98735-199">**Contains:** (12)</span></span>

- <span data-ttu-id="98735-200">`aspnetcore-targeting-pack-[major].[minor]`: ermöglicht eine ältere Runtime als Ziel.</span><span class="sxs-lookup"><span data-stu-id="98735-200">`aspnetcore-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="98735-201">**Version:** \<aspnetcore runtime version></span><span class="sxs-lookup"><span data-stu-id="98735-201">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="98735-202">**Enthält:** (11)</span><span class="sxs-lookup"><span data-stu-id="98735-202">**Contains:** (11)</span></span>

- <span data-ttu-id="98735-203">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`: ermöglicht eine NetStandard-Zielversion</span><span class="sxs-lookup"><span data-stu-id="98735-203">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]` - Allows targeting a netstandard version</span></span>
  - <span data-ttu-id="98735-204">**Version:** \<sdk version></span><span class="sxs-lookup"><span data-stu-id="98735-204">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="98735-205">**Enthält:** (15)</span><span class="sxs-lookup"><span data-stu-id="98735-205">**Contains:** (15)</span></span>

- `dotnet-templates-[major].[minor]`
  - <span data-ttu-id="98735-206">**Version:** \<sdk version></span><span class="sxs-lookup"><span data-stu-id="98735-206">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="98735-207">**Enthält:** (15)</span><span class="sxs-lookup"><span data-stu-id="98735-207">**Contains:** (15)</span></span>

<span data-ttu-id="98735-208">Für `dotnet-runtime-deps-[major].[minor]` ist ein Verständnis der _distributionsspezifischen Abhängigkeiten_ erforderlich.</span><span class="sxs-lookup"><span data-stu-id="98735-208">The `dotnet-runtime-deps-[major].[minor]` requires understanding the _distro-specific dependencies_.</span></span> <span data-ttu-id="98735-209">Da das Buildsystem der Verteilung dies möglicherweise automatisch ableiten kann, ist das Paket optional. In diesem Falle werden diese Abhängigkeiten direkt zum `dotnet-runtime-[major].[minor]`-Paket hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="98735-209">Because the distro build system may be able to derive this automatically, the package is optional, in which case these dependencies are added directly to the `dotnet-runtime-[major].[minor]` package.</span></span>

<span data-ttu-id="98735-210">Wenn Paketinhalte sich in einem Ordner mit Versionsangabe befinden, stimmt der Paketname `[major].[minor]` mit der Ordnernamen mit Versionsangabe überein.</span><span class="sxs-lookup"><span data-stu-id="98735-210">When package content is under a versioned folder, the package name `[major].[minor]` match the versioned folder name.</span></span> <span data-ttu-id="98735-211">Für alle Pakete (außer `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`) stimmt dieser auch mit der .NET Core-Version überein.</span><span class="sxs-lookup"><span data-stu-id="98735-211">For all packages, except the `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, this also matches with the .NET Core version.</span></span>

<span data-ttu-id="98735-212">Abhängigkeiten zwischen Paketen sollten eine _identische oder höhere_ erforderliche Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="98735-212">Dependencies between packages should use an _equal or greater than_ version requirement.</span></span> <span data-ttu-id="98735-213">`dotnet-sdk-2.2:2.2.401` erfordert beispielsweise `aspnetcore-runtime-2.2 >= 2.2.6`.</span><span class="sxs-lookup"><span data-stu-id="98735-213">For example, `dotnet-sdk-2.2:2.2.401` requires `aspnetcore-runtime-2.2 >= 2.2.6`.</span></span> <span data-ttu-id="98735-214">Dies ermöglicht es dem Benutzer, für seine Installation ein Upgrade mithilfe eines Stammpakets (z.B. `dnf update dotnet-sdk-2.2`) durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="98735-214">This makes it possible for the user to upgrade their installation via a root package (for example, `dnf update dotnet-sdk-2.2`).</span></span>

<span data-ttu-id="98735-215">Für die meisten Verteilungen müssen alle Artefakte aus der Quelle erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="98735-215">Most distributions require all artifacts to be built from source.</span></span> <span data-ttu-id="98735-216">Dies wirkt sich auf die Pakete aus:</span><span class="sxs-lookup"><span data-stu-id="98735-216">This has some impact on the packages:</span></span>

- <span data-ttu-id="98735-217">Die Drittanbieterbibliotheken unter `shared/Microsoft.AspNetCore.All` können nicht einfach aus der Quelle erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="98735-217">The third-party libraries under `shared/Microsoft.AspNetCore.All` can't be easily built from source.</span></span> <span data-ttu-id="98735-218">Daher ist dieser Ordner im `aspnetcore-runtime`-Paket nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="98735-218">So that folder is omitted from the `aspnetcore-runtime` package.</span></span>

- <span data-ttu-id="98735-219">Der `NuGetFallbackFolder` wird mithilfe von binären Artefakten aus `nuget.org` aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="98735-219">The `NuGetFallbackFolder` is populated using binary artifacts from `nuget.org`.</span></span> <span data-ttu-id="98735-220">Der Ordner sollte leer bleiben.</span><span class="sxs-lookup"><span data-stu-id="98735-220">It should remain empty.</span></span>

<span data-ttu-id="98735-221">Möglicherweise stellen mehrere `dotnet-sdk`-Pakete die gleichen Dateien für den `NuGetFallbackFolder` bereit.</span><span class="sxs-lookup"><span data-stu-id="98735-221">Multiple `dotnet-sdk` packages may provide the same files for the `NuGetFallbackFolder`.</span></span> <span data-ttu-id="98735-222">Um Probleme mit dem Paket-Manager zu vermeiden, sollten diese Dateien identisch sein (Prüfsumme, Änderungsdatum usw.).</span><span class="sxs-lookup"><span data-stu-id="98735-222">To avoid issues with the package manager, these files should be identical (checksum, modification date, and so on).</span></span>

## <a name="building-packages"></a><span data-ttu-id="98735-223">Erstellen von Paketen</span><span class="sxs-lookup"><span data-stu-id="98735-223">Building packages</span></span>

<span data-ttu-id="98735-224">Das Repository [dotnet/source-build](https://github.com/dotnet/source-build) stellt Anweisungen zum Erstellen eines Quell-Tarballs des .NET Core SDK und aller zugehörigen Komponenten bereit.</span><span class="sxs-lookup"><span data-stu-id="98735-224">The [dotnet/source-build](https://github.com/dotnet/source-build) repository provides instructions on how to build a source tarball of the .NET Core SDK and all its components.</span></span> <span data-ttu-id="98735-225">Die Ausgabe des source-build-Repositorys entspricht der Anordnung, die im ersten Abschnitt dieses Artikels beschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="98735-225">The output of the source-build repository matches the layout described in the first section of this article.</span></span>
