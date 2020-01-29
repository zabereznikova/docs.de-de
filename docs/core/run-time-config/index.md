---
title: Runtimekonfigurationsoptionen
description: Hier erfahren Sie, wie Sie .NET Core-Anwendungen mithilfe von Runtimekonfigurationseinstellungen konfigurieren.
ms.date: 01/21/2020
ms.openlocfilehash: ddf68c30e620a06856f65e71bd050e1b77618f20
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733441"
---
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="2f0b2-103">Konfigurationseinstellungen für die .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="2f0b2-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="2f0b2-104">.NET Core unterstützt die Verwendung von Konfigurationsdateien und Umgebungsvariablen, um das Verhalten von .NET Core-Anwendungen zur Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="2f0b2-105">Runtimekonfigurationen sind eine geeignete Option, wenn</span><span class="sxs-lookup"><span data-stu-id="2f0b2-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="2f0b2-106">Sie den Quellcode für eine Anwendung nicht besitzen oder steuern und ihn deshalb nicht programmgesteuert konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="2f0b2-107">mehrere Instanzen Ihrer Anwendung zur gleichen Zeit auf einem einzelnen System ausgeführt werden und Sie jede Instanz für die optimale Leistung konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="2f0b2-108">Diese Dokumentation ist in Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-108">This documentation is a work in progress.</span></span> <span data-ttu-id="2f0b2-109">Wenn Sie bemerken, dass die Informationen in diesem Artikel entweder unvollständig oder falsch sind, [öffnen Sie ein Issue](https://github.com/dotnet/docs/issues), um uns darüber zu informieren, oder [reichen Sie einen Pull Request ein](https://github.com/dotnet/docs/pulls), um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="2f0b2-110">Weitere Informationen zum Einreichen von Pull Requests für das dotnet/docs-Repository finden Sie im [Leitfaden für Mitwirkende](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span><span class="sxs-lookup"><span data-stu-id="2f0b2-110">For information about submitting pull requests for the dotnet/docs repository, see the [contributor's guide](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>

<span data-ttu-id="2f0b2-111">.NET Core bietet die folgenden Mechanismen zum Konfigurieren des Verhaltens von Runtimeanwendungen:</span><span class="sxs-lookup"><span data-stu-id="2f0b2-111">.NET Core provides the following mechanisms for configuring run-time application behavior:</span></span>

- <span data-ttu-id="2f0b2-112">die [runtimeconfig.json](#runtimeconfigjson)-Datei</span><span class="sxs-lookup"><span data-stu-id="2f0b2-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="2f0b2-113">MSBuild-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2f0b2-113">MSBuild properties</span></span>](#msbuild-properties)

- [<span data-ttu-id="2f0b2-114">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="2f0b2-114">Environment variables</span></span>](#environment-variables)

<span data-ttu-id="2f0b2-115">Einige Konfigurationswerte können auch programmgesteuert festgelegt werden, indem die <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-115">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="2f0b2-116">Die Artikel in diesem Teil der Dokumentation sind nach Kategorie geordnet, z. B. [Debuggen](debugging-profiling.md) und [Garbage Collection](garbage-collector.md).</span><span class="sxs-lookup"><span data-stu-id="2f0b2-116">The articles in this section of the documentation are organized by category, for example, [debugging](debugging-profiling.md) and [garbage collection](garbage-collector.md).</span></span> <span data-ttu-id="2f0b2-117">Gegebenenfalls werden Konfigurationsoptionen für *runtimeconfig.json*-Dateien, MSBuild-Eigenschaften, Umgebungsvariablen und, als Querverweis, *app.config*-Dateien für .NET Framework-Projekte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-117">Where applicable, configuration options are shown for *runtimeconfig.json* files, MSBuild properties, environment variables, and, for cross-reference, *app.config* files for .NET Framework projects.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="2f0b2-118">runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="2f0b2-118">runtimeconfig.json</span></span>

<span data-ttu-id="2f0b2-119">Wenn ein Projekt [erstellt](../tools/dotnet-build.md) wird, wird im Ausgabeverzeichnis eine Datei namens *[App-Name].runtimeconfig.json* generiert.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-119">When a project is [built](../tools/dotnet-build.md), an *[appname].runtimeconfig.json* file is generated in the output directory.</span></span> <span data-ttu-id="2f0b2-120">Wenn eine *runtimeconfig.template.json*-Datei im selben Ordner liegt wie eine Projektdatei, werden alle in ihr enthaltenen Konfigurationsoptionen in der Datei *[App-Name].runtimeconfig.json* zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-120">If a *runtimeconfig.template.json* file exists in the same folder as the project file, any configuration options it contains are merged into the *[appname].runtimeconfig.json* file.</span></span> <span data-ttu-id="2f0b2-121">Wenn Sie die App selbst erstellen, legen Sie alle Konfigurationsoptionen in der Datei *runtimeconfig.template.json* fest.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-121">If you're building the app yourself, put any configuration options in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="2f0b2-122">Wenn Sie die App nur ausführen, fügen Sie sie direkt in die Datei *[App-Name].runtimeconfig.json* ein.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-122">If you're just running the app, insert them directly into the *[appname].runtimeconfig.json* file.</span></span>

> [!NOTE]
> <span data-ttu-id="2f0b2-123">Die Datei *[App-Name].runtimeconfig.json* wird bei nachfolgenden Builds überschrieben.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-123">The *[appname].runtimeconfig.json* file will get overwritten on subsequent builds.</span></span>

<span data-ttu-id="2f0b2-124">Geben Sie die Runtimekonfigurationsoptionen im Abschnitt **configProperties** der Datei *runtimeconfig.json* an.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-124">Specify run-time configuration options in the **configProperties** section of the *runtimeconfig.json* files.</span></span> <span data-ttu-id="2f0b2-125">Dieser Abschnitt hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="2f0b2-125">This section has the form:</span></span>

```json
"configProperties": {
  "config-property-name1": "config-value1",
  "config-property-name2": "config-value2"
}
```

### <a name="example-appnameruntimeconfigjson-file"></a><span data-ttu-id="2f0b2-126">Beispiel einer „[App-Name].runtimeconfig.jason“-Datei</span><span class="sxs-lookup"><span data-stu-id="2f0b2-126">Example [appname].runtimeconfig.json file</span></span>

<span data-ttu-id="2f0b2-127">Wenn Sie die Optionen in der JSON-Ausgabedatei angeben möchten, platzieren Sie sie unter der Eigenschaft `runtimeOptions`.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-127">If you're placing the options in the output JSON file, nest them under the `runtimeOptions` property.</span></span>

```json
{
  "runtimeOptions": {
    "tfm": "netcoreapp3.1",
    "framework": {
      "name": "Microsoft.NETCore.App",
      "version": "3.1.0"
    },
    "configProperties": {
      "System.GC.Concurrent": false,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

### <a name="example-runtimeconfigtemplatejson-file"></a><span data-ttu-id="2f0b2-128">Beispiel einer „runtimeconfig.template.json“-Datei</span><span class="sxs-lookup"><span data-stu-id="2f0b2-128">Example runtimeconfig.template.json file</span></span>

<span data-ttu-id="2f0b2-129">Wenn Sie die Optionen in der template.json-Datei platzieren, lassen Sie die Eigenschaft `runtimeOptions` weg.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-129">If you're placing the options in the template JSON file, omit the `runtimeOptions` property.</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": false,
    "System.Threading.ThreadPool.MinThreads": "4",
    "System.Threading.ThreadPool.MaxThreads": "25"
  }
}
```

## <a name="msbuild-properties"></a><span data-ttu-id="2f0b2-130">MSBuild-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2f0b2-130">MSBuild properties</span></span>

<span data-ttu-id="2f0b2-131">Manche Runtimekonfigurationsoptionen können mithilfe von MSBuild-Eigenschaften in den Dateien *.csproj* oder *.vbproj* von .NET Core-Projekten im SDK-Stil festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-131">Some run-time configuration options can be set using MSBuild properties in the *.csproj* or *.vbproj* file of SDK-style .NET Core projects.</span></span> <span data-ttu-id="2f0b2-132">MSBuild-Eigenschaften haben Vorrang vor Optionen, die in der Datei *runtimeconfig.template.json* festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-132">MSBuild properties take precedence over options set in the *runtimeconfig.template.json* file.</span></span> <span data-ttu-id="2f0b2-133">Außerdem überschreiben sie alle Optionen, die Sie zur Buildzeit in der Datei *[App-Name].runtimeconfig.json* festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-133">They also overwrite any options you set in the *[appname].runtimeconfig.json* file at build time.</span></span>

<span data-ttu-id="2f0b2-134">Hier sehen Sie ein Beispiel für eine Projektdatei im SDK-Stil mit MSBuild-Eigenschaften zum Konfigurieren des Runtimeverhaltens:</span><span class="sxs-lookup"><span data-stu-id="2f0b2-134">Here is an example SDK-style project file with MSBuild properties for configuring run-time behavior:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>

  <PropertyGroup>
    <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
    <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="2f0b2-135">Die MSBuild-Eigenschaften zum Konfigurieren des Runtimeverhaltens finden Sie in den Artikeln für die einzelnen Bereiche, z. B. [Garbage Collection](garbage-collector.md).</span><span class="sxs-lookup"><span data-stu-id="2f0b2-135">MSBuild properties for configuring run-time behavior are noted in the individual articles for each area, for example, [garbage collection](garbage-collector.md).</span></span>

## <a name="environment-variables"></a><span data-ttu-id="2f0b2-136">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="2f0b2-136">Environment variables</span></span>

<span data-ttu-id="2f0b2-137">Umgebungsvariablen können verwendet werden, um einige Informationen zur Runtimekonfiguration bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-137">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="2f0b2-138">Konfigurationseinstellungen, die als Umgebungsvariablen angegeben werden, verfügen generell über das Präfix **COMPlus_**.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-138">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="2f0b2-139">Sie können Umgebungsvariablen über die Windows-Systemsteuerung, die Befehlszeile oder programmgesteuert durch Aufruf der <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType>-Methode jeweils auf den Windows- und Linux-basierten Systemen definieren.</span><span class="sxs-lookup"><span data-stu-id="2f0b2-139">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="2f0b2-140">In den folgenden Beispielen wird dargestellt, wie eine Umgebungsvariable in der Befehlszeile festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="2f0b2-140">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
