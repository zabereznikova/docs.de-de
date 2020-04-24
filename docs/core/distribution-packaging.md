---
title: Verpacken einer Verteilung von .NET Core
description: Erfahren Sie, wie Sie .NET Core für die Verteilung verpacken, benennen und mit einer Versionsnummer versehen.
author: tmds
ms.date: 10/09/2019
ms.openlocfilehash: a345aeded29b3058c6c56abbff439ea26cbc7afb
ms.sourcegitcommit: cdf5084648bf5e77970cbfeaa23f1cab3e6e234e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/01/2020
ms.locfileid: "81386639"
---
# <a name="net-core-distribution-packaging"></a><span data-ttu-id="f6146-103">Verpacken einer Verteilung von .NET Core</span><span class="sxs-lookup"><span data-stu-id="f6146-103">.NET Core distribution packaging</span></span>

<span data-ttu-id="f6146-104">Da .NET Core auf immer mehr Plattformen verfügbar wird, ist es hilfreich zu erfahren, wie man es verpackt, benennt und mit einer Versionsnummer versieht.</span><span class="sxs-lookup"><span data-stu-id="f6146-104">As .NET Core becomes available on more and more platforms, it's useful to learn how to package, name, and version it.</span></span> <span data-ttu-id="f6146-105">Auf diese Weise kann mithilfe von Paketverwaltern eine konsistente Benutzererfahrung sichergestellt werden, unabhängig davon, wo Benutzer .NET ausführen.</span><span class="sxs-lookup"><span data-stu-id="f6146-105">This way, package maintainers can help ensure a consistent experience no matter where users choose to run .NET.</span></span> <span data-ttu-id="f6146-106">Dieser Artikel ist für Benutzer hilfreich, die</span><span class="sxs-lookup"><span data-stu-id="f6146-106">This article is useful for users that are:</span></span>

- <span data-ttu-id="f6146-107">versuchen, .NET Core von der Quelle aus zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f6146-107">Attempting to build .NET Core from source.</span></span>
- <span data-ttu-id="f6146-108">Änderungen an der .NET Core-CLI vornehmen möchten, die sich auf das resultierende Layout oder die erzeugten Pakete auswirken könnten.</span><span class="sxs-lookup"><span data-stu-id="f6146-108">Wanting to make changes to the .NET Core CLI that could impact the resulting layout or packages produced.</span></span>

## <a name="disk-layout"></a><span data-ttu-id="f6146-109">Datenträgerlayout</span><span class="sxs-lookup"><span data-stu-id="f6146-109">Disk layout</span></span>

<span data-ttu-id="f6146-110">.NET Core besteht aus mehreren Komponenten, die im Dateisystem folgendermaßen angeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="f6146-110">When installed, .NET Core consists of several components that are laid out as follows in the filesystem:</span></span>

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

- <span data-ttu-id="f6146-111">(1) **dotnet**: Der Host (auch bekannt als „Muxer“) führt zwei unterschiedliche Rollen aus: das Aktivieren einer Runtime, um eine Anwendung zu starten, und das Aktivieren eines SDK, um Befehle an dieses weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="f6146-111">(1) **dotnet** The host (also known as the "muxer") has two distinct roles: activate a runtime to launch an application, and activate an SDK to dispatch commands to it.</span></span> <span data-ttu-id="f6146-112">Der Host ist eine native ausführbare Datei (`dotnet.exe`).</span><span class="sxs-lookup"><span data-stu-id="f6146-112">The host is a native executable (`dotnet.exe`).</span></span>

<span data-ttu-id="f6146-113">Es gibt nur einen Host, die meisten anderen Komponenten befinden sich jedoch in Verzeichnissen mit Versionsangabe (2, 3, 5, 6).</span><span class="sxs-lookup"><span data-stu-id="f6146-113">While there's a single host, most of the other components are in versioned directories (2,3,5,6).</span></span> <span data-ttu-id="f6146-114">Das bedeutet, dass auf dem System mehrere Versionen vorhanden sein können, da sie nebeneinander installiert werden können.</span><span class="sxs-lookup"><span data-stu-id="f6146-114">This means multiple versions can be present on the system since they're installed side by side.</span></span>

- <span data-ttu-id="f6146-115">(2) **host/fxr/\<fxr version>** : Enthält die vom Host verwendete Framework-Auflösungslogik.</span><span class="sxs-lookup"><span data-stu-id="f6146-115">(2) **host/fxr/\<fxr version>** contains the framework resolution logic used by the host.</span></span> <span data-ttu-id="f6146-116">Der Host verwendet die neueste installierte hostfxr-Version.</span><span class="sxs-lookup"><span data-stu-id="f6146-116">The host uses the latest hostfxr that is installed.</span></span> <span data-ttu-id="f6146-117">„hostfxr“ ist für die Auswahl der geeigneten Runtime beim Ausführen einer .NET Core-Anwendung zuständig.</span><span class="sxs-lookup"><span data-stu-id="f6146-117">The hostfxr is responsible for selecting the appropriate runtime when executing a .NET Core application.</span></span> <span data-ttu-id="f6146-118">Eine Anwendung, die für .NET Core 2.0.0 erstellt wurde, verwendet beispielsweise die Runtime 2.0.5, wenn sie verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="f6146-118">For example, an application built for .NET Core 2.0.0 uses the 2.0.5 runtime when it's available.</span></span> <span data-ttu-id="f6146-119">Ebenso wählt „hostfxr“ während der Entwicklung das geeignete SDK aus.</span><span class="sxs-lookup"><span data-stu-id="f6146-119">Similarly, hostfxr selects the appropriate SDK during development.</span></span>

- <span data-ttu-id="f6146-120">(3) **sdk/\<sdk version>** : Das SDK (auch bekannt als „die Tools“) ist ein Satz verwalteter Tools, die zum Schreiben und Erstellen von .NET Core-Bibliotheken und -Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f6146-120">(3) **sdk/\<sdk version>** The SDK (also known as "the tooling") is a set of managed tools that are used to write and build .NET Core libraries and applications.</span></span> <span data-ttu-id="f6146-121">Das SDK enthält die .NET Core-CLI, die verwalteten Sprachcompiler, MSBuild und zugehörige Buildtasks und -ziele, NuGet, neue Projektvorlagen usw.</span><span class="sxs-lookup"><span data-stu-id="f6146-121">The SDK includes the .NET Core CLI, the managed languages compilers, MSBuild, and associated build tasks and targets, NuGet, new project templates, and so on.</span></span>

- <span data-ttu-id="f6146-122">(4) **sdk/NuGetFallbackFolder** enthält einen Cache der NuGet-Pakete, die von einem SDK während der Wiederherstellung verwendet werden, etwa bei der Ausführung von `dotnet restore` oder `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="f6146-122">(4) **sdk/NuGetFallbackFolder** contains a cache of NuGet packages used by an SDK during the restore operation, such as when running `dotnet restore` or `dotnet build`.</span></span> <span data-ttu-id="f6146-123">Dieser Ordner wird nur vor .NET Core 3.0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6146-123">This folder is only used prior to .NET Core 3.0.</span></span> <span data-ttu-id="f6146-124">Er kann nicht aus der Quelle erstellt werden, da er vorgefertigte binäre Ressourcen aus `nuget.org` enthält.</span><span class="sxs-lookup"><span data-stu-id="f6146-124">It can't be built from source, because it contains prebuilt binary assets from `nuget.org`.</span></span>

<span data-ttu-id="f6146-125">Der Ordner **shared** enthält Frameworks.</span><span class="sxs-lookup"><span data-stu-id="f6146-125">The **shared** folder contains frameworks.</span></span> <span data-ttu-id="f6146-126">Ein gemeinsames (shared) Framework stellt einen Satz Bibliotheken an einem zentralen Speicherort bereit, sodass diese von verschiedenen Anwendungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f6146-126">A shared framework provides a set of libraries at a central location so they can be used by different applications.</span></span>

- <span data-ttu-id="f6146-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** : Dieses Framework enthält die .NET-Runtime und die unterstützenden verwalteten Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="f6146-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** This framework contains the .NET Core runtime and supporting managed libraries.</span></span>

- <span data-ttu-id="f6146-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** enthält die ASP.NET Core-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="f6146-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contains the ASP.NET Core libraries.</span></span> <span data-ttu-id="f6146-129">Die Bibliotheken unter `Microsoft.AspNetCore.App` werden im Rahmen des .NET Core-Projekts entwickelt und unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f6146-129">The libraries under `Microsoft.AspNetCore.App` are developed and supported as part of the .NET Core project.</span></span> <span data-ttu-id="f6146-130">Die Bibliotheken unter `Microsoft.AspNetCore.All` sind ein übergeordnetes Set, das auch Drittanbieterbibliotheken enthält.</span><span class="sxs-lookup"><span data-stu-id="f6146-130">The libraries under `Microsoft.AspNetCore.All` are a superset that also contains third-party libraries.</span></span>

- <span data-ttu-id="f6146-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** enthält die Windows-Desktopbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="f6146-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** contains the Windows desktop libraries.</span></span> <span data-ttu-id="f6146-132">Dies ist nur in Windows enthalten, und nicht in anderen Plattformen.</span><span class="sxs-lookup"><span data-stu-id="f6146-132">This isn't included on non-Windows platforms.</span></span>

- <span data-ttu-id="f6146-133">(8) **LICENSE.txt,ThirdPartyNotices.txt**: Dies sind die .NET Core-Lizenzen und die Lizenzen von Drittanbieterbibliotheken, die in .NET Core jeweils verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f6146-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** are the .NET Core license and licenses of third-party libraries used in .NET Core, respectively.</span></span>

- <span data-ttu-id="f6146-134">(9, 10) **dotnet.1.gz, dotnet**: `dotnet.1.gz` ist die dotnet-Handbuchseite.</span><span class="sxs-lookup"><span data-stu-id="f6146-134">(9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` is the dotnet manual page.</span></span> <span data-ttu-id="f6146-135">`dotnet` ist eine symbolische Verknüpfung mit dem Dotnet-Host (1).</span><span class="sxs-lookup"><span data-stu-id="f6146-135">`dotnet` is a symlink to the dotnet host(1).</span></span> <span data-ttu-id="f6146-136">Diese Dateien werden zur Systemintegration an bekannten Speicherorten installiert.</span><span class="sxs-lookup"><span data-stu-id="f6146-136">These files are installed at well-known locations for system integration.</span></span>

- <span data-ttu-id="f6146-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** beschreibt jeweils die API einer `x.y`-Version von .NET Core und ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="f6146-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** describe the API of an `x.y` version of .NET Core and ASP.NET Core respectively.</span></span> <span data-ttu-id="f6146-138">Diese Pakete werden bei der Kompilierung für diese Zielversionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6146-138">These packs are used when compiling for those target versions.</span></span>

- <span data-ttu-id="f6146-139">(13) **Microsoft.NETCore.App.Host.\<rid>** enthält eine native Binärdatei für die Plattform `rid`.</span><span class="sxs-lookup"><span data-stu-id="f6146-139">(13) **Microsoft.NETCore.App.Host.\<rid>** contains a native binary for platform `rid`.</span></span> <span data-ttu-id="f6146-140">Diese Binärdatei ist eine Vorlage für das Kompilieren einer .NET Core-Anwendung in eine native Binärdatei für diese Plattform.</span><span class="sxs-lookup"><span data-stu-id="f6146-140">This binary is a template when compiling a .NET Core application into a native binary for that platform.</span></span>

- <span data-ttu-id="f6146-141">(14) **Microsoft.WindowsDesktop.App.Ref** beschreibt die API der `x.y`-Version von Windows-Desktopanwendungen.</span><span class="sxs-lookup"><span data-stu-id="f6146-141">(14) **Microsoft.WindowsDesktop.App.Ref** describes the API of `x.y` version of Windows Desktop applications.</span></span> <span data-ttu-id="f6146-142">Diese Dateien werden beim Kompilieren für dieses Ziel verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6146-142">These files are used when compiling for that target.</span></span> <span data-ttu-id="f6146-143">Dies wird nur unter Windows bereitgestellt, und nicht für andere Plattformen.</span><span class="sxs-lookup"><span data-stu-id="f6146-143">This isn't provided on non-Windows platforms.</span></span>

- <span data-ttu-id="f6146-144">(15) **NETStandard.Library.Ref** beschreibt die NetStandard-API `x.y`.</span><span class="sxs-lookup"><span data-stu-id="f6146-144">(15) **NETStandard.Library.Ref** describes the netstandard `x.y` API.</span></span> <span data-ttu-id="f6146-145">Diese Dateien werden beim Kompilieren für dieses Ziel verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6146-145">These files are used when compiling for that target.</span></span>

- <span data-ttu-id="f6146-146">(16) **/etc/dotnet/install_location** ist eine Datei, die den vollständigen Pfad für `{dotnet_root}` enthält.</span><span class="sxs-lookup"><span data-stu-id="f6146-146">(16) **/etc/dotnet/install_location** is a file that contains the full path for `{dotnet_root}`.</span></span> <span data-ttu-id="f6146-147">Der Pfad kann mit einem Zeilenvorschubzeichen enden.</span><span class="sxs-lookup"><span data-stu-id="f6146-147">The path may end with a newline.</span></span> <span data-ttu-id="f6146-148">Es ist nicht erforderlich, diese Datei hinzuzufügen, wenn `/usr/share/dotnet` das Stammverzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="f6146-148">It's not necessary to add this file when the root is `/usr/share/dotnet`.</span></span>

- <span data-ttu-id="f6146-149">(17) **templates** enthält die Vorlagen, die vom SDK verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f6146-149">(17) **templates** contains the templates used by the SDK.</span></span> <span data-ttu-id="f6146-150">Beispielsweise ermittelt `dotnet new` Projektvorlagen in diesem Ordner.</span><span class="sxs-lookup"><span data-stu-id="f6146-150">For example, `dotnet new` finds project templates here.</span></span>

<span data-ttu-id="f6146-151">Die mit `(*)` markierten Ordner werden von mehreren Paketen verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6146-151">The folders marked with `(*)` are used by multiple packages.</span></span> <span data-ttu-id="f6146-152">Einige Paketformate (z.B. `rpm`) erfordern eine besondere Verarbeitung solcher Ordner.</span><span class="sxs-lookup"><span data-stu-id="f6146-152">Some package formats (for example, `rpm`) require special handling of such folders.</span></span> <span data-ttu-id="f6146-153">Der Paketmaintainer muss dafür Sorge tragen.</span><span class="sxs-lookup"><span data-stu-id="f6146-153">The package maintainer must take care of this.</span></span>

## <a name="recommended-packages"></a><span data-ttu-id="f6146-154">Empfohlene Pakete</span><span class="sxs-lookup"><span data-stu-id="f6146-154">Recommended packages</span></span>

<span data-ttu-id="f6146-155">Die .NET Core-Versionierung basiert auf dem Versionsnummernmuster `[major].[minor]` der Runtimekomponente.</span><span class="sxs-lookup"><span data-stu-id="f6146-155">.NET Core versioning is based on the runtime component `[major].[minor]` version numbers.</span></span>
<span data-ttu-id="f6146-156">Die SDK-Version verwendet das gleiche `[major].[minor]`-Muster und weist eine unabhängige `[patch]`-Zeichenfolge auf, die die Feature- und Patchsemantik für das SDK kombiniert.</span><span class="sxs-lookup"><span data-stu-id="f6146-156">The SDK version uses the same `[major].[minor]` and has an independent `[patch]` that combines feature and patch semantics for the SDK.</span></span>
<span data-ttu-id="f6146-157">Zum Beispiel: Die SDK-Version 2.2.302 ist das zweite Patchrelease des dritten Featurerelease des SDK, das die Runtimeversion 2.2 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f6146-157">For example: SDK version 2.2.302 is the second patch release of the third feature release of the SDK that supports the 2.2 runtime.</span></span> <span data-ttu-id="f6146-158">Weitere Informationen zur Funktionsweise der Versionsverwaltung finden Sie unter [.NET Core-Versionskontrolle: Übersicht](./versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="f6146-158">For more information about how versioning works, see [.NET Core versioning overview](./versions/index.md).</span></span>

<span data-ttu-id="f6146-159">Einige Pakete enthalten einen Teil der Versionsnummer im Namen.</span><span class="sxs-lookup"><span data-stu-id="f6146-159">Some of the packages include part of the version number in their name.</span></span> <span data-ttu-id="f6146-160">Dies ermöglicht Ihnen, eine bestimmte Version zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f6146-160">This allows you to install a specific version.</span></span>
<span data-ttu-id="f6146-161">Der Rest der Version ist im Versionsnamen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f6146-161">The rest of the version isn't included in the version name.</span></span> <span data-ttu-id="f6146-162">Dies ermöglicht dem Paket-Manager des Betriebssystems, die Pakete zu aktualisieren (z.B. durch automatisches Installieren von Sicherheitsfixes).</span><span class="sxs-lookup"><span data-stu-id="f6146-162">This allows the OS package manager to update the packages (for example, automatically installing security fixes).</span></span> <span data-ttu-id="f6146-163">Unterstützte Paket-Manager sind Linux-spezifisch.</span><span class="sxs-lookup"><span data-stu-id="f6146-163">Supported package managers are Linux specific.</span></span>

<span data-ttu-id="f6146-164">Im Folgenden werden die empfohlenen Pakete aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="f6146-164">The following lists the recommended packages:</span></span>

- <span data-ttu-id="f6146-165">`dotnet-sdk-[major].[minor]`: installiert das neueste SDK für eine spezifische Runtime.</span><span class="sxs-lookup"><span data-stu-id="f6146-165">`dotnet-sdk-[major].[minor]` - Installs the latest sdk for specific runtime</span></span>
  - <span data-ttu-id="f6146-166">**Version:** \<runtimeversion></span><span class="sxs-lookup"><span data-stu-id="f6146-166">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="f6146-167">**Beispiel:** dotnet-sdk-2.1</span><span class="sxs-lookup"><span data-stu-id="f6146-167">**Example:** dotnet-sdk-2.1</span></span>
  - <span data-ttu-id="f6146-168">**Enthält:** (3), (4)</span><span class="sxs-lookup"><span data-stu-id="f6146-168">**Contains:** (3),(4)</span></span>
  - <span data-ttu-id="f6146-169">**Abhängigkeiten:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="f6146-169">**Dependencies:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span></span>

- <span data-ttu-id="f6146-170">`aspnetcore-runtime-[major].[minor]`: installiert eine spezifische ASP.NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="f6146-170">`aspnetcore-runtime-[major].[minor]` - Installs a specific ASP.NET Core runtime</span></span>
  - <span data-ttu-id="f6146-171">**Version:** \<aspnetcore runtimeversion></span><span class="sxs-lookup"><span data-stu-id="f6146-171">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="f6146-172">**Beispiel:** aspnetcore-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="f6146-172">**Example:** aspnetcore-runtime-2.1</span></span>
  - <span data-ttu-id="f6146-173">**Enthält:** (6)</span><span class="sxs-lookup"><span data-stu-id="f6146-173">**Contains:** (6)</span></span>
  - <span data-ttu-id="f6146-174">**Abhängigkeiten:** `dotnet-runtime-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="f6146-174">**Dependencies:** `dotnet-runtime-[major].[minor]`</span></span>

- <span data-ttu-id="f6146-175">`dotnet-runtime-deps-[major].[minor]` _(Optional):_ Installiert die Abhängigkeiten zum Ausführen eigenständiger Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="f6146-175">`dotnet-runtime-deps-[major].[minor]` _(Optional)_ - Installs the dependencies for running self-contained applications</span></span>
  - <span data-ttu-id="f6146-176">**Version:** \<runtimeversion></span><span class="sxs-lookup"><span data-stu-id="f6146-176">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="f6146-177">**Beispiel:** dotnet-runtime-deps-2.1</span><span class="sxs-lookup"><span data-stu-id="f6146-177">**Example:** dotnet-runtime-deps-2.1</span></span>
  - <span data-ttu-id="f6146-178">**Abhängigkeiten:** _Verteilungsspezifische Abhängigkeiten_</span><span class="sxs-lookup"><span data-stu-id="f6146-178">**Dependencies:** _distribution-specific dependencies_</span></span>

- <span data-ttu-id="f6146-179">`dotnet-runtime-[major].[minor]`: installiert eine spezifische Runtime</span><span class="sxs-lookup"><span data-stu-id="f6146-179">`dotnet-runtime-[major].[minor]` - Installs a specific runtime</span></span>
  - <span data-ttu-id="f6146-180">**Version:** \<runtimeversion></span><span class="sxs-lookup"><span data-stu-id="f6146-180">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="f6146-181">**Beispiel:** dotnet-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="f6146-181">**Example:** dotnet-runtime-2.1</span></span>
  - <span data-ttu-id="f6146-182">**Enthält:** (5)</span><span class="sxs-lookup"><span data-stu-id="f6146-182">**Contains:** (5)</span></span>
  - <span data-ttu-id="f6146-183">**Abhängigkeiten:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="f6146-183">**Dependencies:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`</span></span>

- <span data-ttu-id="f6146-184">`dotnet-hostfxr-[major].[minor]`: Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="f6146-184">`dotnet-hostfxr-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="f6146-185">**Version:** \<runtimeversion></span><span class="sxs-lookup"><span data-stu-id="f6146-185">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="f6146-186">**Beispiel:** dotnet-hostfxr-3.0</span><span class="sxs-lookup"><span data-stu-id="f6146-186">**Example:** dotnet-hostfxr-3.0</span></span>
  - <span data-ttu-id="f6146-187">**Enthält:** (2)</span><span class="sxs-lookup"><span data-stu-id="f6146-187">**Contains:** (2)</span></span>
  - <span data-ttu-id="f6146-188">**Abhängigkeiten:** `dotnet-host`</span><span class="sxs-lookup"><span data-stu-id="f6146-188">**Dependencies:** `dotnet-host`</span></span>

- <span data-ttu-id="f6146-189">`dotnet-host`: Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="f6146-189">`dotnet-host` - dependency</span></span>
  - <span data-ttu-id="f6146-190">**Version:** \<runtimeversion></span><span class="sxs-lookup"><span data-stu-id="f6146-190">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="f6146-191">**Beispiel:** dotnet-host</span><span class="sxs-lookup"><span data-stu-id="f6146-191">**Example:** dotnet-host</span></span>
  - <span data-ttu-id="f6146-192">**Enthält:** (1),(8),(9),(10),(16)</span><span class="sxs-lookup"><span data-stu-id="f6146-192">**Contains:** (1),(8),(9),(10),(16)</span></span>

- <span data-ttu-id="f6146-193">`dotnet-apphost-pack-[major].[minor]`: Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="f6146-193">`dotnet-apphost-pack-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="f6146-194">**Version:** \<runtimeversion></span><span class="sxs-lookup"><span data-stu-id="f6146-194">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="f6146-195">**Enthält:** (13)</span><span class="sxs-lookup"><span data-stu-id="f6146-195">**Contains:** (13)</span></span>

- <span data-ttu-id="f6146-196">`dotnet-targeting-pack-[major].[minor]`: ermöglicht eine ältere Runtime als Ziel.</span><span class="sxs-lookup"><span data-stu-id="f6146-196">`dotnet-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="f6146-197">**Version:** \<runtimeversion></span><span class="sxs-lookup"><span data-stu-id="f6146-197">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="f6146-198">**Enthält:** (12)</span><span class="sxs-lookup"><span data-stu-id="f6146-198">**Contains:** (12)</span></span>

- <span data-ttu-id="f6146-199">`aspnetcore-targeting-pack-[major].[minor]`: ermöglicht eine ältere Runtime als Ziel.</span><span class="sxs-lookup"><span data-stu-id="f6146-199">`aspnetcore-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="f6146-200">**Version:** \<aspnetcore runtimeversion></span><span class="sxs-lookup"><span data-stu-id="f6146-200">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="f6146-201">**Enthält:** (11)</span><span class="sxs-lookup"><span data-stu-id="f6146-201">**Contains:** (11)</span></span>

- <span data-ttu-id="f6146-202">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`: ermöglicht eine NetStandard-Zielversion</span><span class="sxs-lookup"><span data-stu-id="f6146-202">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]` - Allows targeting a netstandard version</span></span>
  - <span data-ttu-id="f6146-203">**Version:** \<sdk version></span><span class="sxs-lookup"><span data-stu-id="f6146-203">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="f6146-204">**Enthält:** (15)</span><span class="sxs-lookup"><span data-stu-id="f6146-204">**Contains:** (15)</span></span>

- `dotnet-templates-[major].[minor]`
  - <span data-ttu-id="f6146-205">**Version:** \<sdk version></span><span class="sxs-lookup"><span data-stu-id="f6146-205">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="f6146-206">**Enthält:** (15)</span><span class="sxs-lookup"><span data-stu-id="f6146-206">**Contains:** (15)</span></span>

<span data-ttu-id="f6146-207">Für `dotnet-runtime-deps-[major].[minor]` ist ein Verständnis der _distributionsspezifischen Abhängigkeiten_ erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f6146-207">The `dotnet-runtime-deps-[major].[minor]` requires understanding the _distro-specific dependencies_.</span></span> <span data-ttu-id="f6146-208">Da das Buildsystem der Verteilung dies möglicherweise automatisch ableiten kann, ist das Paket optional. In diesem Falle werden diese Abhängigkeiten direkt zum `dotnet-runtime-[major].[minor]`-Paket hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f6146-208">Because the distro build system may be able to derive this automatically, the package is optional, in which case these dependencies are added directly to the `dotnet-runtime-[major].[minor]` package.</span></span>

<span data-ttu-id="f6146-209">Wenn Paketinhalte sich in einem Ordner mit Versionsangabe befinden, stimmt der Paketname `[major].[minor]` mit der Ordnernamen mit Versionsangabe überein.</span><span class="sxs-lookup"><span data-stu-id="f6146-209">When package content is under a versioned folder, the package name `[major].[minor]` match the versioned folder name.</span></span> <span data-ttu-id="f6146-210">Für alle Pakete (außer `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`) stimmt dieser auch mit der .NET Core-Version überein.</span><span class="sxs-lookup"><span data-stu-id="f6146-210">For all packages, except the `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, this also matches with the .NET Core version.</span></span>

<span data-ttu-id="f6146-211">Abhängigkeiten zwischen Paketen sollten eine _identische oder höhere_ erforderliche Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6146-211">Dependencies between packages should use an _equal or greater than_ version requirement.</span></span> <span data-ttu-id="f6146-212">`dotnet-sdk-2.2:2.2.401` erfordert beispielsweise `aspnetcore-runtime-2.2 >= 2.2.6`.</span><span class="sxs-lookup"><span data-stu-id="f6146-212">For example, `dotnet-sdk-2.2:2.2.401` requires `aspnetcore-runtime-2.2 >= 2.2.6`.</span></span> <span data-ttu-id="f6146-213">Dies ermöglicht es dem Benutzer, für seine Installation ein Upgrade mithilfe eines Stammpakets (z.B. `dnf update dotnet-sdk-2.2`) durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="f6146-213">This makes it possible for the user to upgrade their installation via a root package (for example, `dnf update dotnet-sdk-2.2`).</span></span>

<span data-ttu-id="f6146-214">Für die meisten Verteilungen müssen alle Artefakte aus der Quelle erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f6146-214">Most distributions require all artifacts to be built from source.</span></span> <span data-ttu-id="f6146-215">Dies wirkt sich auf die Pakete aus:</span><span class="sxs-lookup"><span data-stu-id="f6146-215">This has some impact on the packages:</span></span>

- <span data-ttu-id="f6146-216">Die Drittanbieterbibliotheken unter `shared/Microsoft.AspNetCore.All` können nicht einfach aus der Quelle erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="f6146-216">The third-party libraries under `shared/Microsoft.AspNetCore.All` can't be easily built from source.</span></span> <span data-ttu-id="f6146-217">Daher ist dieser Ordner im `aspnetcore-runtime`-Paket nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="f6146-217">So that folder is omitted from the `aspnetcore-runtime` package.</span></span>

- <span data-ttu-id="f6146-218">Der `NuGetFallbackFolder` wird mithilfe von binären Artefakten aus `nuget.org` aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="f6146-218">The `NuGetFallbackFolder` is populated using binary artifacts from `nuget.org`.</span></span> <span data-ttu-id="f6146-219">Der Ordner sollte leer bleiben.</span><span class="sxs-lookup"><span data-stu-id="f6146-219">It should remain empty.</span></span>

<span data-ttu-id="f6146-220">Möglicherweise stellen mehrere `dotnet-sdk`-Pakete die gleichen Dateien für den `NuGetFallbackFolder` bereit.</span><span class="sxs-lookup"><span data-stu-id="f6146-220">Multiple `dotnet-sdk` packages may provide the same files for the `NuGetFallbackFolder`.</span></span> <span data-ttu-id="f6146-221">Um Probleme mit dem Paket-Manager zu vermeiden, sollten diese Dateien identisch sein (Prüfsumme, Änderungsdatum usw.).</span><span class="sxs-lookup"><span data-stu-id="f6146-221">To avoid issues with the package manager, these files should be identical (checksum, modification date, and so on).</span></span>

## <a name="building-packages"></a><span data-ttu-id="f6146-222">Erstellen von Paketen</span><span class="sxs-lookup"><span data-stu-id="f6146-222">Building packages</span></span>

<span data-ttu-id="f6146-223">Das Repository [dotnet/source-build](https://github.com/dotnet/source-build) stellt Anweisungen zum Erstellen eines Quell-Tarballs des .NET Core SDK und aller zugehörigen Komponenten bereit.</span><span class="sxs-lookup"><span data-stu-id="f6146-223">The [dotnet/source-build](https://github.com/dotnet/source-build) repository provides instructions on how to build a source tarball of the .NET Core SDK and all its components.</span></span> <span data-ttu-id="f6146-224">Die Ausgabe des source-build-Repositorys entspricht der Anordnung, die im ersten Abschnitt dieses Artikels beschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="f6146-224">The output of the source-build repository matches the layout described in the first section of this article.</span></span>
