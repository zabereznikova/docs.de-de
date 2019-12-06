---
title: Runtimekonfiguration
description: Hier erfahren Sie, wie Sie .NET Core-Anwendungen mithilfe von Runtimekonfigurationseinstellungen konfigurieren.
ms.date: 11/13/2019
ms.openlocfilehash: 2665026347e94d26026821beb2bfcf8441f755f6
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2019
ms.locfileid: "74801916"
---
# <a name="net-core-run-time-configuration-settings"></a><span data-ttu-id="2b778-103">Konfigurationseinstellungen für die .NET Core-Runtime</span><span class="sxs-lookup"><span data-stu-id="2b778-103">.NET Core run-time configuration settings</span></span>

<span data-ttu-id="2b778-104">.NET Core unterstützt die Verwendung von Konfigurationsdateien und Umgebungsvariablen, um das Verhalten von .NET Core-Anwendungen zur Laufzeit zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2b778-104">.NET Core supports the use of configuration files and environment variables to configure the behavior of .NET Core applications at run time.</span></span> <span data-ttu-id="2b778-105">Runtimekonfigurationen sind eine geeignete Option, wenn</span><span class="sxs-lookup"><span data-stu-id="2b778-105">Run-time configuration is an attractive option if:</span></span>

- <span data-ttu-id="2b778-106">Sie den Quellcode für eine Anwendung nicht besitzen oder steuern und ihn deshalb nicht programmgesteuert konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="2b778-106">You don't own or control the source code for an application and therefore are unable to configure it programmatically.</span></span>

- <span data-ttu-id="2b778-107">mehrere Instanzen Ihrer Anwendung zur gleichen Zeit auf einem einzelnen System ausgeführt werden und Sie jede Instanz für die optimale Leistung konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2b778-107">Multiple instances of your application run at the same time on a single system, and you want to configure each for optimum performance.</span></span>

> [!NOTE]
> <span data-ttu-id="2b778-108">Diese Dokumentation ist in Bearbeitung.</span><span class="sxs-lookup"><span data-stu-id="2b778-108">This documentation is a work in progress.</span></span> <span data-ttu-id="2b778-109">Wenn Sie bemerken, dass die Informationen in diesem Artikel entweder unvollständig oder falsch sind, [öffnen Sie ein Issue](https://github.com/dotnet/docs/issues), um uns darüber zu informieren, oder [reichen Sie einen Pull Request ein](https://github.com/dotnet/docs/pulls), um das Problem zu beheben.</span><span class="sxs-lookup"><span data-stu-id="2b778-109">If you notice that the information presented here is either incomplete or inaccurate, either [open an issue](https://github.com/dotnet/docs/issues) to let us know about it, or [submit a pull request](https://github.com/dotnet/docs/pulls) to address the issue.</span></span> <span data-ttu-id="2b778-110">Weitere Informationen zum Einreichen von Pull Requests für das dotnet/docs-Repository finden Sie im [Leitfaden für Mitwirkende](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span><span class="sxs-lookup"><span data-stu-id="2b778-110">For information on submitting pull requests for the dotnet/docs repository, see the [contributor's guide](https://github.com/dotnet/docs/blob/master/CONTRIBUTING.md).</span></span>

<span data-ttu-id="2b778-111">.NET Core bietet die folgenden Mechanismen zum Konfigurieren von Anwendungen zur Laufzeit:</span><span class="sxs-lookup"><span data-stu-id="2b778-111">.NET Core provides the following mechanisms for configuring applications at run time:</span></span>

- <span data-ttu-id="2b778-112">die [runtimeconfig.json](#runtimeconfigjson)-Datei</span><span class="sxs-lookup"><span data-stu-id="2b778-112">The [runtimeconfig.json file](#runtimeconfigjson)</span></span>

- [<span data-ttu-id="2b778-113">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="2b778-113">Environment variables</span></span>](#environment-variables)

<span data-ttu-id="2b778-114">Die Artikel in diesem Teil der Dokumentation sind nach Kategorie geordnet, z. B. Debuggen und Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="2b778-114">The articles in this section of the documentation include are organized by category, for example, debugging and garbage collection.</span></span> <span data-ttu-id="2b778-115">Konfigurationsoptionen werden ggf. für *runtimeconfig.json* (nur .NET Core), *app.config* (nur .NET Framework) und Umgebungsvariablen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2b778-115">Where applicable, configuration options are shown for *runtimeconfig.json* (.NET Core only), *app.config* (.NET Framework only), and environment variables.</span></span>

## <a name="runtimeconfigjson"></a><span data-ttu-id="2b778-116">runtimeconfig.json</span><span class="sxs-lookup"><span data-stu-id="2b778-116">runtimeconfig.json</span></span>

<span data-ttu-id="2b778-117">Geben Sie die Konfigurationsoptionen für die Runtime im Abschnitt **configproperties** der *runtimeconfig.json*-Datei der App an.</span><span class="sxs-lookup"><span data-stu-id="2b778-117">Specify run-time configuration options in the **configProperties** section of the app's *runtimeconfig.json* file.</span></span> <span data-ttu-id="2b778-118">Dieser Abschnitt hat das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="2b778-118">This section has the form:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "config-property-name1": "config-value1",
         "config-property-name2": "config-value2"
      }
   }
}
```

<span data-ttu-id="2b778-119">Hier ist ein Beispiel für eine Datei:</span><span class="sxs-lookup"><span data-stu-id="2b778-119">Here is an example file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.GC.Concurrent": true,
         "System.GC.RetainVM": true,
         "System.Threading.ThreadPool.MinThreads": "4",
         "System.Threading.ThreadPool.MaxThreads": "25"
      }
   }
}
```

<span data-ttu-id="2b778-120">Die Datei *runtimeconfig.json* wird automatisch vom [dotnet build](../tools/dotnet-build.md)-Befehl im Buildverzeichnis erstellt.</span><span class="sxs-lookup"><span data-stu-id="2b778-120">The *runtimeconfig.json* file is automatically created in the build directory by the [dotnet build](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="2b778-121">Sie wird auch erstellt, wenn Sie die Menüoption **Erstellen** in Visual Studio auswählen.</span><span class="sxs-lookup"><span data-stu-id="2b778-121">It's also created when you select the **Build** menu option in Visual Studio.</span></span> <span data-ttu-id="2b778-122">Sie können die Datei bearbeiten, wenn sie erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2b778-122">You can then edit the file once it's created.</span></span>

<span data-ttu-id="2b778-123">Einige Konfigurationswerte können auch programmgesteuert festgelegt werden, indem die <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType>-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="2b778-123">Some configuration values can also be set programmatically by calling the <xref:System.AppContext.SetSwitch%2A?displayProperty=nameWithType> method.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="2b778-124">Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="2b778-124">Environment variables</span></span>

<span data-ttu-id="2b778-125">Umgebungsvariablen können verwendet werden, um einige Informationen zur Runtimekonfiguration bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2b778-125">Environment variables can be used to supply some run-time configuration information.</span></span> <span data-ttu-id="2b778-126">Konfigurationseinstellungen, die als Umgebungsvariablen angegeben werden, verfügen generell über das Präfix **COMPlus_** .</span><span class="sxs-lookup"><span data-stu-id="2b778-126">Configuration knobs specified as environment variables generally have the prefix **COMPlus_**.</span></span>

<span data-ttu-id="2b778-127">Sie können Umgebungsvariablen über die Windows-Systemsteuerung, die Befehlszeile oder programmgesteuert durch Aufruf der <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType>-Methode jeweils auf den Windows- und Linux-basierten Systemen definieren.</span><span class="sxs-lookup"><span data-stu-id="2b778-127">You can define environment variables from the Windows Control Panel, at the command line, or programmatically by calling the <xref:System.Environment.SetEnvironmentVariable(System.String,System.String)?displayProperty=nameWithType> method on both Windows and Unix-based systems.</span></span>

<span data-ttu-id="2b778-128">In den folgenden Beispielen wird dargestellt, wie eine Umgebungsvariable in der Befehlszeile festgelegt wird:</span><span class="sxs-lookup"><span data-stu-id="2b778-128">The following examples show how to set an environment variable at the command line:</span></span>

```shell
# Windows
set COMPlus_GCRetainVM=1

# Powershell
$env:COMPlus_GCRetainVM="1"

# Unix
export COMPlus_GCRetainVM=1
```
