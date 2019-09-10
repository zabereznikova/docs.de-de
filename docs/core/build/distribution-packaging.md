---
title: Verpacken einer Verteilung von .NET Core
description: Erfahren Sie, wie Sie .NET Core für die Verteilung verpacken, benennen und mit einer Versionsnummer versehen.
author: tmds
ms.date: 03/02/2018
ms.custom: seodec18
ms.openlocfilehash: d72677cba1e7685f8e05cf479ec508683dd77b55
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70394158"
---
# <a name="net-core-distribution-packaging"></a><span data-ttu-id="26acc-103">Verpacken einer Verteilung von .NET Core</span><span class="sxs-lookup"><span data-stu-id="26acc-103">.NET Core distribution packaging</span></span>

<span data-ttu-id="26acc-104">Da .NET Core auf immer mehr Plattformen verfügbar wird, ist es hilfreich zu erfahren, wie man es verpackt, benennt und mit einer Versionsnummer versieht.</span><span class="sxs-lookup"><span data-stu-id="26acc-104">As .NET Core becomes available on more and more platforms, it's useful to learn how to package, name, and version it.</span></span> <span data-ttu-id="26acc-105">Auf diese Weise kann mithilfe von Paketverwaltern eine konsistente Benutzererfahrung sichergestellt werden, unabhängig davon, wo Benutzer .NET ausführen.</span><span class="sxs-lookup"><span data-stu-id="26acc-105">This way, package maintainers can help ensure a consistent experience no matter where users choose to run .NET.</span></span> <span data-ttu-id="26acc-106">Dieser Artikel ist für Benutzer hilfreich, die</span><span class="sxs-lookup"><span data-stu-id="26acc-106">This article is useful for users that are:</span></span>

- <span data-ttu-id="26acc-107">versuchen, .NET Core von der Quelle aus zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="26acc-107">Attempting to build .NET Core from source.</span></span>
- <span data-ttu-id="26acc-108">Änderungen an der .NET Core-CLI vornehmen möchten, die sich auf das resultierende Layout oder die erzeugten Pakete auswirken könnten.</span><span class="sxs-lookup"><span data-stu-id="26acc-108">Wanting to make changes to the .NET Core CLI that could impact the resulting layout or packages produced.</span></span>

## <a name="disk-layout"></a><span data-ttu-id="26acc-109">Datenträgerlayout</span><span class="sxs-lookup"><span data-stu-id="26acc-109">Disk layout</span></span>

<span data-ttu-id="26acc-110">.NET Core besteht aus mehreren Komponenten, die im Dateisystem folgendermaßen angeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="26acc-110">When installed, .NET Core consists of several components that are laid out as follows in the filesystem:</span></span>

```
.
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host
│   └── fxr
│       └── <fxr version>        (2)
├── sdk
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)
├── packs
│   ├── Microsoft.AspNetCore.App.Ref
│   │   └── <aspnetcore ref version>     (11)
│   ├── Microsoft.NETCore.App.Ref
│   │   └── <netcore ref version>        (12)
│   ├── Microsoft.NETCore.App.Host.<rid>
│   │   └── <apphost version>            (13)
│   ├── Microsoft.WindowsDesktop.App.Ref
│   │   └── <desktop ref version>        (14)
│   └── NETStandard.Library.Ref
│       └── <netstandard version>        (15)
├── shared
│   ├── Microsoft.NETCore.App
│   │   └── <runtime version>     (5)
│   ├── Microsoft.AspNetCore.App
│   │   └── <aspnetcore version>  (6)
│   ├── Microsoft.AspNetCore.All
│   │   └── <aspnetcore version>  (6)
│   └── Microsoft.WindowsDesktop.App
│       └── <desktop app version> (7)
└── templates
│   └── <templates version>      (17)
/
├── etc/dotnet
│       └── install_location     (16)
├── usr/share/man/man1
│       └── dotnet.1.gz          (9)
└── usr/bin
        └── dotnet               (10)
```

- <span data-ttu-id="26acc-111">(1) **dotnet**: Der Host (auch bekannt als „Muxer“) führt zwei unterschiedliche Rollen aus: das Aktivieren einer Runtime, um eine Anwendung zu starten, und das Aktivieren eines SDK, um Befehle an dieses weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="26acc-111">(1) **dotnet** The host (also known as the "muxer") has two distinct roles: activate a runtime to launch an application, and activate an SDK to dispatch commands to it.</span></span> <span data-ttu-id="26acc-112">Der Host ist eine native ausführbare Datei (`dotnet.exe`).</span><span class="sxs-lookup"><span data-stu-id="26acc-112">The host is a native executable (`dotnet.exe`).</span></span>

<span data-ttu-id="26acc-113">Es gibt nur einen Host, die meisten anderen Komponenten befinden sich jedoch in Verzeichnissen mit Versionsangabe (2, 3, 5, 6).</span><span class="sxs-lookup"><span data-stu-id="26acc-113">While there's a single host, most of the other components are in versioned directories (2,3,5,6).</span></span> <span data-ttu-id="26acc-114">Das bedeutet, dass auf dem System mehrere Versionen vorhanden sein können, da sie nebeneinander installiert werden können.</span><span class="sxs-lookup"><span data-stu-id="26acc-114">This means multiple versions can be present on the system since they're installed side by side.</span></span>

- <span data-ttu-id="26acc-115">(2) **host/fxr/\<fxr version>** : Enthält die vom Host verwendete Framework-Auflösungslogik.</span><span class="sxs-lookup"><span data-stu-id="26acc-115">(2) **host/fxr/\<fxr version>** contains the framework resolution logic used by the host.</span></span> <span data-ttu-id="26acc-116">Der Host verwendet die neueste installierte hostfxr-Version.</span><span class="sxs-lookup"><span data-stu-id="26acc-116">The host uses the latest hostfxr that is installed.</span></span> <span data-ttu-id="26acc-117">„hostfxr“ ist für die Auswahl der geeigneten Runtime beim Ausführen einer .NET Core-Anwendung zuständig.</span><span class="sxs-lookup"><span data-stu-id="26acc-117">The hostfxr is responsible for selecting the appropriate runtime when executing a .NET Core application.</span></span> <span data-ttu-id="26acc-118">Eine Anwendung, die für .NET Core 2.0.0 erstellt wurde, verwendet beispielsweise die Runtime 2.0.5, wenn sie verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="26acc-118">For example, an application built for .NET Core 2.0.0 uses the 2.0.5 runtime when it's available.</span></span> <span data-ttu-id="26acc-119">Ebenso wählt „hostfxr“ während der Entwicklung das geeignete SDK aus.</span><span class="sxs-lookup"><span data-stu-id="26acc-119">Similarly, hostfxr selects the appropriate SDK during development.</span></span>

- <span data-ttu-id="26acc-120">(3) **sdk/\<sdk version>** : Das SDK (auch bekannt als „die Tools“) ist ein Satz verwalteter Tools, die zum Schreiben und Erstellen von .NET Core-Bibliotheken und -Anwendungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="26acc-120">(3) **sdk/\<sdk version>** The SDK (also known as "the tooling") is a set of managed tools that are used to write and build .NET Core libraries and applications.</span></span> <span data-ttu-id="26acc-121">Das SDK enthält die .NET Core-Befehlszeilenschnittstelle (Command-Line Interface, CLI), die verwalteten Sprachencompiler, MSBuild und zugeordnete Buildaufgaben und Ziele, NuGet, neue Projektvorlagen usw.</span><span class="sxs-lookup"><span data-stu-id="26acc-121">The SDK includes the .NET Core Command-line interface (CLI), the managed languages compilers, MSBuild, and associated build tasks and targets, NuGet, new project templates, and so on.</span></span>

- <span data-ttu-id="26acc-122">(4) **sdk/NuGetFallbackFolder** enthält einen Cache der NuGet-Pakete, die von einem SDK während der Wiederherstellung verwendet werden, etwa bei der Ausführung von `dotnet restore` oder `dotnet build /t:Restore`.</span><span class="sxs-lookup"><span data-stu-id="26acc-122">(4) **sdk/NuGetFallbackFolder** contains a cache of NuGet packages used by an SDK during the restore operation, such as when running `dotnet restore` or `dotnet build /t:Restore`.</span></span> <span data-ttu-id="26acc-123">Dieser Ordner wird nur vor .NET Core 3.0 verwendet.</span><span class="sxs-lookup"><span data-stu-id="26acc-123">This folder is only used prior to .NET Core 3.0.</span></span> <span data-ttu-id="26acc-124">Er kann nicht aus der Quelle erstellt werden, da er vorgefertigte binäre Ressourcen aus `nuget.org` enthält.</span><span class="sxs-lookup"><span data-stu-id="26acc-124">It can't be built from source, because it contains prebuilt binary assets from `nuget.org`.</span></span>

<span data-ttu-id="26acc-125">Der Ordner **shared** enthält Frameworks.</span><span class="sxs-lookup"><span data-stu-id="26acc-125">The **shared** folder contains frameworks.</span></span> <span data-ttu-id="26acc-126">Ein gemeinsames (shared) Framework stellt einen Satz Bibliotheken an einem zentralen Speicherort bereit, sodass diese von verschiedenen Anwendungen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="26acc-126">A shared framework provides a set of libraries at a central location so they can be used by different applications.</span></span>

- <span data-ttu-id="26acc-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** : Dieses Framework enthält die .NET-Runtime und die unterstützenden verwalteten Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="26acc-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** This framework contains the .NET Core runtime and supporting managed libraries.</span></span>

- <span data-ttu-id="26acc-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** enthält die ASP.NET Core-Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="26acc-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contains the ASP.NET Core libraries.</span></span> <span data-ttu-id="26acc-129">Die Bibliotheken unter `Microsoft.AspNetCore.App` werden im Rahmen des .NET Core-Projekts entwickelt und unterstützt.</span><span class="sxs-lookup"><span data-stu-id="26acc-129">The libraries under `Microsoft.AspNetCore.App` are developed and supported as part of the .NET Core project.</span></span> <span data-ttu-id="26acc-130">Die Bibliotheken unter `Microsoft.AspNetCore.All` sind ein übergeordnetes Set, das auch Drittanbieterbibliotheken enthält.</span><span class="sxs-lookup"><span data-stu-id="26acc-130">The libraries under `Microsoft.AspNetCore.All` are a superset that also contains third-party libraries.</span></span>

- <span data-ttu-id="26acc-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** enthält die Windows-Desktopbibliotheken.</span><span class="sxs-lookup"><span data-stu-id="26acc-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** contains the Windows desktop libraries.</span></span> <span data-ttu-id="26acc-132">Dies ist nur in Windows enthalten, und nicht in anderen Plattformen.</span><span class="sxs-lookup"><span data-stu-id="26acc-132">This isn't included on non-Windows platforms.</span></span>

- <span data-ttu-id="26acc-133">(8) **LICENSE.txt,ThirdPartyNotices.txt**: Dies sind die .NET Core-Lizenzen und die Lizenzen von Drittanbieterbibliotheken, die in .NET Core jeweils verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="26acc-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** are the .NET Core license and licenses of third-party libraries used in .NET Core, respectively.</span></span>

- <span data-ttu-id="26acc-134">(9, 10) **dotnet.1.gz, dotnet**: `dotnet.1.gz` ist die Dotnet-Handbuchseite.</span><span class="sxs-lookup"><span data-stu-id="26acc-134">(9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` is the dotnet manual page.</span></span> <span data-ttu-id="26acc-135">`dotnet` ist eine symbolische Verknüpfung mit dem Dotnet-Host (1).</span><span class="sxs-lookup"><span data-stu-id="26acc-135">`dotnet` is a symlink to the dotnet host(1).</span></span> <span data-ttu-id="26acc-136">Diese Dateien werden zur Systemintegration an bekannten Speicherorten installiert.</span><span class="sxs-lookup"><span data-stu-id="26acc-136">These files are installed at well known locations for system integration.</span></span>

- <span data-ttu-id="26acc-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** beschreibt jeweils die API einer `x.y`-Version von .NET Core und ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="26acc-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** describe the API of an `x.y` version of .NET Core and ASP.NET Core respectively.</span></span> <span data-ttu-id="26acc-138">Diese Pakete werden bei der Kompilierung für diese Zielversionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="26acc-138">These packs are used when compiling for those target versions.</span></span>

- <span data-ttu-id="26acc-139">(13) **Microsoft.NETCore.App.Host.\<rid>** enthält eine native Binärdatei für die Plattform `rid`.</span><span class="sxs-lookup"><span data-stu-id="26acc-139">(13) **Microsoft.NETCore.App.Host.\<rid>** contains a native binary for platform `rid`.</span></span> <span data-ttu-id="26acc-140">Diese Binärdatei ist eine Vorlage für das Kompilieren einer .NET Core-Anwendung in eine native Binärdatei für diese Plattform.</span><span class="sxs-lookup"><span data-stu-id="26acc-140">This binary is a template when compiling a .NET Core application into a native binary for that platform.</span></span>

- <span data-ttu-id="26acc-141">(14) **Microsoft.WindowsDesktop.App.Ref** beschreibt die API der `x.y`-Version von Windows-Desktopanwendungen.</span><span class="sxs-lookup"><span data-stu-id="26acc-141">(14) **Microsoft.WindowsDesktop.App.Ref** describes the API of `x.y` version of Windows Desktop applications.</span></span> <span data-ttu-id="26acc-142">Diese Dateien werden beim Kompilieren für dieses Ziel verwendet.</span><span class="sxs-lookup"><span data-stu-id="26acc-142">These files are used when compiling for that target.</span></span> <span data-ttu-id="26acc-143">Dies wird nur unter Windows bereitgestellt, und nicht für andere Plattformen.</span><span class="sxs-lookup"><span data-stu-id="26acc-143">This isn't provided on non-Windows platforms.</span></span>

- <span data-ttu-id="26acc-144">(15) **NETStandard.Library.Ref** beschreibt die NetStandard-API `x.y`.</span><span class="sxs-lookup"><span data-stu-id="26acc-144">(15) **NETStandard.Library.Ref** describes the netstandard `x.y` API.</span></span> <span data-ttu-id="26acc-145">Diese Dateien werden beim Kompilieren für dieses Ziel verwendet.</span><span class="sxs-lookup"><span data-stu-id="26acc-145">These files are used when compiling for that target.</span></span>

- <span data-ttu-id="26acc-146">(16) **/etc/dotnet/install_location** ist eine Datei, die den vollständigen Pfad zu dem Ordner enthält, der die `dotnet`-Hostbinärdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="26acc-146">(16) **/etc/dotnet/install_location** is a file that contains the full path to the folder that contains the `dotnet` host binary.</span></span> <span data-ttu-id="26acc-147">Der Pfad kann mit einem Zeilenumbruch gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="26acc-147">The path may be terminated with a newline.</span></span> <span data-ttu-id="26acc-148">Es ist nicht erforderlich, diese Datei hinzuzufügen, wenn `/usr/share/dotnet` das Stammverzeichnis ist.</span><span class="sxs-lookup"><span data-stu-id="26acc-148">It's not necessary to add this file when the root is `/usr/share/dotnet`.</span></span>

- <span data-ttu-id="26acc-149">(17) **templates** enthält die Vorlagen, die vom SDK verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="26acc-149">(17) **templates** contains the templates used by the SDK.</span></span> <span data-ttu-id="26acc-150">Beispielsweise ermittelt `dotnet new` Projektvorlagen in diesem Ordner.</span><span class="sxs-lookup"><span data-stu-id="26acc-150">For example, `dotnet new` finds project templates here.</span></span>

## <a name="recommended-packages"></a><span data-ttu-id="26acc-151">Empfohlene Pakete</span><span class="sxs-lookup"><span data-stu-id="26acc-151">Recommended packages</span></span>

<span data-ttu-id="26acc-152">Die .NET Core-Versionierung basiert auf dem Versionsnummernmuster `[major].[minor]` der Runtimekomponente.</span><span class="sxs-lookup"><span data-stu-id="26acc-152">.NET Core versioning is based on the runtime component `[major].[minor]` version numbers.</span></span>
<span data-ttu-id="26acc-153">Die SDK-Version verwendet das gleiche `[major].[minor]`-Muster und weist eine unabhängige `[patch]`-Zeichenfolge auf, die die Feature- und Patchsemantik für das SDK kombiniert.</span><span class="sxs-lookup"><span data-stu-id="26acc-153">The SDK version uses the same `[major].[minor]` and has an independent `[patch]` that combines feature and patch semantics for the SDK.</span></span>
<span data-ttu-id="26acc-154">Beispiel: Die SDK-Version 2.2.302 ist das zweite Patchrelease des dritten Featurerelease des SDK, das die Runtimeversion 2.2 unterstützt.</span><span class="sxs-lookup"><span data-stu-id="26acc-154">For example: SDK version 2.2.302 is the second patch release of the third feature release of the SDK that supports the 2.2 runtime.</span></span> <span data-ttu-id="26acc-155">Weitere Informationen zur Funktionsweise der Versionsverwaltung finden Sie unter [.NET Core-Versionskontrolle: Übersicht](../versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="26acc-155">For more information about how versioning works, see [.NET Core versioning overview](../versions/index.md).</span></span>

<span data-ttu-id="26acc-156">Einige Pakete enthalten einen Teil der Versionsnummer im Namen.</span><span class="sxs-lookup"><span data-stu-id="26acc-156">Some of the packages include part of the version number in their name.</span></span> <span data-ttu-id="26acc-157">Dies ermöglicht Ihnen, eine bestimmte Version zu installieren.</span><span class="sxs-lookup"><span data-stu-id="26acc-157">This allows you to install a specific version.</span></span>
<span data-ttu-id="26acc-158">Der Rest der Version ist im Versionsnamen nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="26acc-158">The rest of the version isn't included in the version name.</span></span> <span data-ttu-id="26acc-159">Dies ermöglicht dem Paket-Manager des Betriebssystems, die Pakete zu aktualisieren (z.B. durch automatisches Installieren von Sicherheitsfixes).</span><span class="sxs-lookup"><span data-stu-id="26acc-159">This allows the OS package manager to update the packages (for example, automatically installing security fixes).</span></span> <span data-ttu-id="26acc-160">Unterstützte Paket-Manager sind Linux-spezifisch.</span><span class="sxs-lookup"><span data-stu-id="26acc-160">Supported package managers are Linux specific.</span></span>

<span data-ttu-id="26acc-161">Im Folgenden werden die empfohlenen Pakete aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="26acc-161">The following lists the recommended packages:</span></span>

- <span data-ttu-id="26acc-162">`dotnet-sdk-[major].[minor]`: installiert das neueste SDK für eine spezifische Runtime.</span><span class="sxs-lookup"><span data-stu-id="26acc-162">`dotnet-sdk-[major].[minor]` - Installs the latest sdk for specific runtime</span></span>
  - <span data-ttu-id="26acc-163">**Version:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="26acc-163">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="26acc-164">**Beispiel:** dotnet-sdk-2.1</span><span class="sxs-lookup"><span data-stu-id="26acc-164">**Example:** dotnet-sdk-2.1</span></span>
  - <span data-ttu-id="26acc-165">**Enthält:** (3), (4)</span><span class="sxs-lookup"><span data-stu-id="26acc-165">**Contains:** (3),(4)</span></span>
  - <span data-ttu-id="26acc-166">**Abhängigkeiten:** `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="26acc-166">**Dependencies:** `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span></span>

- <span data-ttu-id="26acc-167">`aspnetcore-runtime-[major].[minor]`: installiert eine spezifische ASP.NET Core-Runtime.</span><span class="sxs-lookup"><span data-stu-id="26acc-167">`aspnetcore-runtime-[major].[minor]` - Installs a specific ASP.NET Core runtime</span></span>
  - <span data-ttu-id="26acc-168">**Version:** \<aspnetcore runtime version></span><span class="sxs-lookup"><span data-stu-id="26acc-168">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="26acc-169">**Beispiel:** aspnetcore-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="26acc-169">**Example:** aspnetcore-runtime-2.1</span></span>
  - <span data-ttu-id="26acc-170">**Enthält:**  (6)</span><span class="sxs-lookup"><span data-stu-id="26acc-170">**Contains:** (6)</span></span>
  - <span data-ttu-id="26acc-171">**Abhängigkeiten:** `dotnet-runtime-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="26acc-171">**Dependencies:** `dotnet-runtime-[major].[minor]`</span></span>

- <span data-ttu-id="26acc-172">`dotnet-runtime-deps-[major].[minor]` _(Optional):_ installiert die Abhängigkeiten zum Ausführen eigenständiger Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="26acc-172">`dotnet-runtime-deps-[major].[minor]` _(Optional)_ - Installs the dependencies for running self-contained applications</span></span>
  - <span data-ttu-id="26acc-173">**Version:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="26acc-173">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="26acc-174">**Beispiel:** dotnet-runtime-deps-2.1</span><span class="sxs-lookup"><span data-stu-id="26acc-174">**Example:** dotnet-runtime-deps-2.1</span></span>
  - <span data-ttu-id="26acc-175">**Abhängigkeiten:** _Abhängigkeiten für spezifische Verteilungen_</span><span class="sxs-lookup"><span data-stu-id="26acc-175">**Dependencies:** _distro specific dependencies_</span></span>

- <span data-ttu-id="26acc-176">`dotnet-runtime-[major].[minor]`: installiert eine spezifische Runtime</span><span class="sxs-lookup"><span data-stu-id="26acc-176">`dotnet-runtime-[major].[minor]` - Installs a specific runtime</span></span>
  - <span data-ttu-id="26acc-177">**Version:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="26acc-177">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="26acc-178">**Beispiel:** dotnet-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="26acc-178">**Example:** dotnet-runtime-2.1</span></span>
  - <span data-ttu-id="26acc-179">**Enthält:** (5)</span><span class="sxs-lookup"><span data-stu-id="26acc-179">**Contains:** (5)</span></span>
  - <span data-ttu-id="26acc-180">**Abhängigkeiten:** `dotnet-hostfxr:<runtime version>+`, `dotnet-runtime-deps-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="26acc-180">**Dependencies:** `dotnet-hostfxr:<runtime version>+`, `dotnet-runtime-deps-[major].[minor]`</span></span>

- <span data-ttu-id="26acc-181">`dotnet-hostfxr`: Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="26acc-181">`dotnet-hostfxr` - dependency</span></span>
  - <span data-ttu-id="26acc-182">**Version:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="26acc-182">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="26acc-183">**Beispiel:** dotnet-hostfxr</span><span class="sxs-lookup"><span data-stu-id="26acc-183">**Example:** dotnet-hostfxr</span></span>
  - <span data-ttu-id="26acc-184">**Enthält:** (2)</span><span class="sxs-lookup"><span data-stu-id="26acc-184">**Contains:** (2)</span></span>
  - <span data-ttu-id="26acc-185">**Abhängigkeiten:** `host:<runtime version>+`</span><span class="sxs-lookup"><span data-stu-id="26acc-185">**Dependencies:** `host:<runtime version>+`</span></span>

- <span data-ttu-id="26acc-186">`dotnet-host`: Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="26acc-186">`dotnet-host` - dependency</span></span>
  - <span data-ttu-id="26acc-187">**Version:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="26acc-187">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="26acc-188">**Beispiel:** dotnet-host</span><span class="sxs-lookup"><span data-stu-id="26acc-188">**Example:** dotnet-host</span></span>
  - <span data-ttu-id="26acc-189">**Enthält:** (1),(8),(9),(10),(16)</span><span class="sxs-lookup"><span data-stu-id="26acc-189">**Contains:** (1),(8),(9),(10),(16)</span></span>

- <span data-ttu-id="26acc-190">`dotnet-apphost-pack-[major].[minor]`: Abhängigkeit</span><span class="sxs-lookup"><span data-stu-id="26acc-190">`dotnet-apphost-pack-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="26acc-191">**Version:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="26acc-191">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="26acc-192">**Enthält:** (13)</span><span class="sxs-lookup"><span data-stu-id="26acc-192">**Contains:** (13)</span></span>

- <span data-ttu-id="26acc-193">`dotnet-targeting-pack-[major].[minor]`: ermöglicht eine ältere Runtime als Ziel.</span><span class="sxs-lookup"><span data-stu-id="26acc-193">`dotnet-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="26acc-194">**Version:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="26acc-194">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="26acc-195">**Enthält:** (12)</span><span class="sxs-lookup"><span data-stu-id="26acc-195">**Contains:** (12)</span></span>

- <span data-ttu-id="26acc-196">`aspnetcore-targeting-pack-[major].[minor]`: ermöglicht eine ältere Runtime als Ziel.</span><span class="sxs-lookup"><span data-stu-id="26acc-196">`aspnetcore-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="26acc-197">**Version:** \<aspnetcore runtime version></span><span class="sxs-lookup"><span data-stu-id="26acc-197">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="26acc-198">**Enthält:** (11)</span><span class="sxs-lookup"><span data-stu-id="26acc-198">**Contains:** (11)</span></span>

- <span data-ttu-id="26acc-199">`netstandard-targeting-pack-[major].[minor]`: ermöglicht eine NetStandard-Zielversion</span><span class="sxs-lookup"><span data-stu-id="26acc-199">`netstandard-targeting-pack-[major].[minor]` - Allows targeting a netstandard version</span></span>
  - <span data-ttu-id="26acc-200">**Version:** \<sdk version></span><span class="sxs-lookup"><span data-stu-id="26acc-200">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="26acc-201">**Enthält:** (15)</span><span class="sxs-lookup"><span data-stu-id="26acc-201">**Contains:** (15)</span></span>

- `dotnet-templates-[major].[minor]`
  - <span data-ttu-id="26acc-202">**Version:** \<sdk version></span><span class="sxs-lookup"><span data-stu-id="26acc-202">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="26acc-203">**Enthält:** (15)</span><span class="sxs-lookup"><span data-stu-id="26acc-203">**Contains:** (15)</span></span>

<span data-ttu-id="26acc-204">Für `dotnet-runtime-deps-[major].[minor]` sind Kenntnisse der _Abhängigkeiten für spezifische Verteilungen_ erforderlich.</span><span class="sxs-lookup"><span data-stu-id="26acc-204">The `dotnet-runtime-deps-[major].[minor]` requires understanding the _distro specific dependencies_.</span></span> <span data-ttu-id="26acc-205">Da das Buildsystem der Verteilung dies möglicherweise automatisch ableiten kann, ist das Paket optional. In diesem Falle werden diese Abhängigkeiten direkt zum `dotnet-runtime-[major].[minor]`-Paket hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="26acc-205">Because the distro build system may be able to derive this automatically, the package is optional, in which case these dependencies are added directly to the `dotnet-runtime-[major].[minor]` package.</span></span>

<span data-ttu-id="26acc-206">Wenn Paketinhalte sich in einem Ordner mit Versionsangabe befinden, stimmt der Paketname `[major].[minor]` mit der Ordnernamen mit Versionsangabe überein.</span><span class="sxs-lookup"><span data-stu-id="26acc-206">When package content is under a versioned folder, the package name `[major].[minor]` match the versioned folder name.</span></span> <span data-ttu-id="26acc-207">Für alle Pakete (außer `netstandard-targeting-pack-[major].[minor]`) stimmt dieser auch mit der .NET Core-Version überein.</span><span class="sxs-lookup"><span data-stu-id="26acc-207">For all packages, except the `netstandard-targeting-pack-[major].[minor]`, this also matches with the .NET Core version.</span></span>

<span data-ttu-id="26acc-208">Abhängigkeiten zwischen Paketen sollten eine _identische oder höhere_ erforderliche Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="26acc-208">Dependencies between packages should use a _equal or greater than_ version requirement.</span></span> <span data-ttu-id="26acc-209">`dotnet-sdk-2.2:2.2.401` erfordert beispielsweise `aspnetcore-runtime-2.2 >= 2.2.6`.</span><span class="sxs-lookup"><span data-stu-id="26acc-209">For example, `dotnet-sdk-2.2:2.2.401` requires `aspnetcore-runtime-2.2 >= 2.2.6`.</span></span> <span data-ttu-id="26acc-210">Dies ermöglicht dem Benutzer, für ihre Installation ein Upgrade mithilfe eines Stammpakets (z. B. `dnf update dotnet-sdk-2.2`) durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="26acc-210">This makes it possible for the user to upgrade their installation via a root package (e.g. `dnf update dotnet-sdk-2.2`).</span></span>

<span data-ttu-id="26acc-211">Für die meisten Verteilungen müssen alle Artefakte aus der Quelle erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="26acc-211">Most distributions require all artifacts to be built from source.</span></span> <span data-ttu-id="26acc-212">Dies wirkt sich auf die Pakete aus:</span><span class="sxs-lookup"><span data-stu-id="26acc-212">This has some impact on the packages:</span></span>

- <span data-ttu-id="26acc-213">Die Drittanbieterbibliotheken unter `shared/Microsoft.AspNetCore.All` können nicht einfach aus der Quelle erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="26acc-213">The third-party libraries under `shared/Microsoft.AspNetCore.All` can't be easily built from source.</span></span> <span data-ttu-id="26acc-214">Daher ist dieser Ordner im `aspnetcore-runtime`-Paket nicht enthalten.</span><span class="sxs-lookup"><span data-stu-id="26acc-214">So that folder is omitted from the `aspnetcore-runtime` package.</span></span>

- <span data-ttu-id="26acc-215">Der `NuGetFallbackFolder` wird mithilfe von binären Artefakten aus `nuget.org` aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="26acc-215">The `NuGetFallbackFolder` is populated using binary artifacts from `nuget.org`.</span></span> <span data-ttu-id="26acc-216">Der Ordner sollte leer bleiben.</span><span class="sxs-lookup"><span data-stu-id="26acc-216">It should remain empty.</span></span>

<span data-ttu-id="26acc-217">Möglicherweise stellen mehrere `dotnet-sdk`-Pakete die gleichen Dateien für den `NuGetFallbackFolder` bereit.</span><span class="sxs-lookup"><span data-stu-id="26acc-217">Multiple `dotnet-sdk` packages may provide the same files for the `NuGetFallbackFolder`.</span></span> <span data-ttu-id="26acc-218">Um Probleme mit dem Paket-Manager zu vermeiden, sollten diese Dateien identisch sein (Prüfsumme, Änderungsdatum usw.).</span><span class="sxs-lookup"><span data-stu-id="26acc-218">To avoid issues with the package manager, these files should be identical (checksum, modification date, and so on).</span></span>

## <a name="building-packages"></a><span data-ttu-id="26acc-219">Erstellen von Paketen</span><span class="sxs-lookup"><span data-stu-id="26acc-219">Building packages</span></span>

<span data-ttu-id="26acc-220">Das Repository [dotnet/source-build](https://github.com/dotnet/source-build) stellt Anweisungen zum Erstellen eines Quell-Tarballs des .NET Core SDK und aller zugehörigen Komponenten bereit.</span><span class="sxs-lookup"><span data-stu-id="26acc-220">The [dotnet/source-build](https://github.com/dotnet/source-build) repository provides instructions on how to build a source tarball of the .NET Core SDK and all its components.</span></span> <span data-ttu-id="26acc-221">Die Ausgabe des source-build-Repositorys entspricht der Anordnung, die im ersten Abschnitt dieses Artikels beschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="26acc-221">The output of the source-build repository matches the layout described in the first section of this article.</span></span>
