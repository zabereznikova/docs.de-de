---
title: Reduzieren von Paketabhängigkeiten mit „project.json“
description: Reduzieren Sie beim Erstellen von Bibliotheken, die auf project.json basieren, die Paketabhängigkeiten.
author: cartermp
ms.date: 06/20/2016
ms.openlocfilehash: 48ba3ef578388fd98fe7cb830df313512d359483
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740826"
---
# <a name="reducing-package-dependencies-with-projectjson"></a><span data-ttu-id="7205a-103">Reduzieren von Paketabhängigkeiten mit „project.json“</span><span class="sxs-lookup"><span data-stu-id="7205a-103">Reducing Package Dependencies with project.json</span></span>

<span data-ttu-id="7205a-104">Dieser Artikel beschreibt, was Sie über das Reduzieren Ihrer Paketabhängigkeiten beim Erstellen von `project.json`-Bibliotheken wissen müssen.</span><span class="sxs-lookup"><span data-stu-id="7205a-104">This article covers what you need to know about reducing your package dependencies when authoring `project.json` libraries.</span></span> <span data-ttu-id="7205a-105">Am Ende dieses Artikels erfahren Sie, wie Ihre Bibliothek so zusammengesetzt wird, dass sie nur die Abhängigkeiten verwendet, die sie benötigt.</span><span class="sxs-lookup"><span data-stu-id="7205a-105">By the end of this article, you will learn how to compose your library such that it only uses the dependencies it needs.</span></span>

## <a name="why-its-important"></a><span data-ttu-id="7205a-106">Warum dies wichtig ist</span><span class="sxs-lookup"><span data-stu-id="7205a-106">Why it's Important</span></span>

<span data-ttu-id="7205a-107">.NET Core ist ein Produkt, das aus NuGet-Paketen besteht.</span><span class="sxs-lookup"><span data-stu-id="7205a-107">.NET Core is a product made up of NuGet packages.</span></span>  <span data-ttu-id="7205a-108">Ein wichtiges Paket ist das [.NETStandard.Library metapackage (.NETStandard.Library-Metapaket)](https://www.nuget.org/packages/NETStandard.Library), wobei es sich um ein NuGet-Paket handelt, das aus anderen Paketen besteht.</span><span class="sxs-lookup"><span data-stu-id="7205a-108">An essential package is the [.NETStandard.Library metapackage](https://www.nuget.org/packages/NETStandard.Library), which is a NuGet package composed of other packages.</span></span> <span data-ttu-id="7205a-109">Es stellt die Reihe von Paketen bereit, bei denen gewährleistet wird, dass sie in mehreren .NET-Implementierungen wie .NET Framework, .NET Core und Xamarin/Mono funktionieren.</span><span class="sxs-lookup"><span data-stu-id="7205a-109">It provides you with the set of packages that are guaranteed to work on multiple .NET implementations, such as .NET Framework, .NET Core, and Xamarin/Mono.</span></span>

<span data-ttu-id="7205a-110">Jedoch ist die Wahrscheinlichkeit hoch, dass Ihre Bibliothek nicht jedes einzelne Paket verwenden wird, das enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="7205a-110">However, there's a good chance that your library won't use every single package it contains.</span></span>  <span data-ttu-id="7205a-111">Beim Erstellen einer Bibliothek und Verteilen dieser Bibliothek über NuGet ist eine empfohlene Vorgehensweise das „Beschränken“ Ihrer Abhängigkeiten auf nur die Pakete, die Sie tatsächlich verwenden.</span><span class="sxs-lookup"><span data-stu-id="7205a-111">When authoring a library and distributing it over NuGet, it's a best practice to "trim" your dependencies down to only the packages you actually use.</span></span>  <span data-ttu-id="7205a-112">Dies führt zu einem kleineren allgemeinen Speicherbedarf für NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="7205a-112">This results in a smaller overall footprint for NuGet packages.</span></span>

## <a name="how-to-do-it"></a><span data-ttu-id="7205a-113">So gehen Sie vor</span><span class="sxs-lookup"><span data-stu-id="7205a-113">How to do it</span></span>

<span data-ttu-id="7205a-114">Derzeit gibt es keinen offiziellen `dotnet`-Befehl, der Paketverweise beschränkt.</span><span class="sxs-lookup"><span data-stu-id="7205a-114">Currently, there is no official `dotnet` command that trims package references.</span></span>  <span data-ttu-id="7205a-115">Stattdessen müssen Sie dies manuell tun.</span><span class="sxs-lookup"><span data-stu-id="7205a-115">Instead, you'll have to do it manually.</span></span>  <span data-ttu-id="7205a-116">Der allgemeine Prozess sieht folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="7205a-116">The general process looks like the following:</span></span>

1. <span data-ttu-id="7205a-117">Verweisen Sie auf `NETStandard.Library` Version `1.6.0` in einem `dependencies`-Abschnitt Ihrer `project.json`.</span><span class="sxs-lookup"><span data-stu-id="7205a-117">Reference `NETStandard.Library` version `1.6.0` in a `dependencies` section of your `project.json`.</span></span>
2. <span data-ttu-id="7205a-118">Stellen Sie Pakete mit `dotnet restore` ([siehe Hinweis](#dotnet-restore-note)) über die Befehlszeile wieder her.</span><span class="sxs-lookup"><span data-stu-id="7205a-118">Restore packages with `dotnet restore` ([see note](#dotnet-restore-note)) from the command line.</span></span>
3. <span data-ttu-id="7205a-119">Prüfen Sie die Datei `project.lock.json`, und suchen Sie den Abschnitt `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="7205a-119">Inspect the `project.lock.json` file and find the `NETStandard.Library` section.</span></span>  <span data-ttu-id="7205a-120">Er befindet sich nahe dem Anfang der Datei.</span><span class="sxs-lookup"><span data-stu-id="7205a-120">It's near the beginning of the file.</span></span>
4. <span data-ttu-id="7205a-121">Kopieren Sie alle unter `dependencies` aufgeführten Pakete.</span><span class="sxs-lookup"><span data-stu-id="7205a-121">Copy all of the listed packages under `dependencies`.</span></span>
5. <span data-ttu-id="7205a-122">Entfernen Sie den `.NETStandard.Library`-Verweis, und ersetzen Sie ihn durch die kopierten Pakete.</span><span class="sxs-lookup"><span data-stu-id="7205a-122">Remove the `.NETStandard.Library` reference and replace it with the copied packages.</span></span>
6. <span data-ttu-id="7205a-123">Entfernen Sie Verweise auf Pakete, die Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="7205a-123">Remove references to packages you don't need.</span></span>

<span data-ttu-id="7205a-124">Auf eine der folgenden Weisen können Sie herausfinden, welche Pakete Sie nicht benötigen:</span><span class="sxs-lookup"><span data-stu-id="7205a-124">You can find out which packages you don't need by one of the following ways:</span></span>

1. <span data-ttu-id="7205a-125">Ausprobieren:</span><span class="sxs-lookup"><span data-stu-id="7205a-125">Trial and error.</span></span> <span data-ttu-id="7205a-126">Bei dieser Methode entfernen Sie ein Paket, stellen es wieder her, nehmen zur Kenntnis, ob Ihre Bibliothek immer noch kompiliert, und wiederholen diesen Prozess.</span><span class="sxs-lookup"><span data-stu-id="7205a-126">This involves removing a package, restoring, seeing if your library still compiles, and repeating this process.</span></span>
2. <span data-ttu-id="7205a-127">Verwenden eines Tools zum Ansehen von Verweisen wie z.B. [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) oder [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector), um zu sehen, was Ihr Code tatsächlich verwendet.</span><span class="sxs-lookup"><span data-stu-id="7205a-127">Using a tool such as [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) or [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector) to peek at references to see what your code is actually using.</span></span> <span data-ttu-id="7205a-128">Anschließend können Sie Pakete entfernen, die nicht den Typen entsprechen, die Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="7205a-128">You can then remove packages that don't correspond to types you're using.</span></span>

## <a name="example"></a><span data-ttu-id="7205a-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7205a-129">Example</span></span>

<span data-ttu-id="7205a-130">Stellen Sie sich vor, dass Sie eine Bibliothek geschrieben haben, die zusätzliche Funktionen für generische Sammlungstypen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7205a-130">Imagine that you wrote a library that provided additional functionality to generic collection types.</span></span> <span data-ttu-id="7205a-131">Eine solche Bibliothek müsste von Paketen wie z.B. `System.Collections` abhängen, hängt möglicherweise aber überhaupt nicht von Paketen wie z.B. `System.Net.Http` ab.</span><span class="sxs-lookup"><span data-stu-id="7205a-131">Such a library would need to depend on packages such as `System.Collections`, but may not at all depend on packages such as `System.Net.Http`.</span></span> <span data-ttu-id="7205a-132">Daher wäre es gut, Paketabhängigkeiten auf nur das zu beschränken, was die Bibliothek tatsächlich benötigt.</span><span class="sxs-lookup"><span data-stu-id="7205a-132">As such, it would be good to trim package dependencies down to only what this library required!</span></span>

<span data-ttu-id="7205a-133">Um diese Bibliothek zu beschränken, beginnen Sie mit der `project.json`-Datei, und fügen Sie einen Verweis zu `NETStandard.Library` Version `1.6.0` hinzu.</span><span class="sxs-lookup"><span data-stu-id="7205a-133">To trim this library, you start with the `project.json` file and add a reference to `NETStandard.Library` version `1.6.0`.</span></span>

```json
{
    "version":"1.0.0",
    "dependencies":{
        "NETStandard.Library":"1.6.0"
    },
    "frameworks": {
        "netstandard1.0": {}
     }
}
```

<span data-ttu-id="7205a-134">Als Nächstes stellen Sie Pakete mit `dotnet restore` wieder her ([siehe Hinweis](#dotnet-restore-note)), prüfen die Datei `project.lock.json` und suchen alle für `NETStandard.Library` wiederhergestellten Pakete.</span><span class="sxs-lookup"><span data-stu-id="7205a-134">Next, you restore packages with `dotnet restore` ([see note](#dotnet-restore-note)), inspect the `project.lock.json` file, and find all the packages restored for `NETStandard.Library`.</span></span>

<span data-ttu-id="7205a-135">So sieht der entsprechende Abschnitt in der Datei `project.lock.json` aus, wenn auf `netstandard1.0` abgezielt wird:</span><span class="sxs-lookup"><span data-stu-id="7205a-135">Here's what the relevant section in the `project.lock.json` file looks like when targeting `netstandard1.0`:</span></span>

```json
"NETStandard.Library/1.6.0":{
    "type": "package",
    "dependencies": {
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    }
}
```

<span data-ttu-id="7205a-136">Kopieren Sie als Nächstes die Paketverweise in den `dependencies`-Abschnitt der `project.json`-Datei der Bibliothek, und ersetzen Sie den `NETStandard.Library`-Verweis:</span><span class="sxs-lookup"><span data-stu-id="7205a-136">Next, copy over the package references into the `dependencies` section of the library's `project.json` file, replacing the `NETStandard.Library` reference:</span></span>

```json
{
    "version":"1.0.0",
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Diagnostics.Debug": "4.0.11",
        "System.Diagnostics.Tools": "4.0.1",
        "System.Globalization": "4.0.11",
        "System.IO": "4.1.0",
        "System.Linq": "4.1.0",
        "System.Net.Primitives": "4.0.11",
        "System.ObjectModel": "4.0.12",
        "System.Reflection": "4.1.0",
        "System.Reflection.Extensions": "4.0.1",
        "System.Reflection.Primitives": "4.0.1",
        "System.Resources.ResourceManager": "4.0.1",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Text.Encoding": "4.0.11",
        "System.Text.Encoding.Extensions": "4.0.11",
        "System.Text.RegularExpressions": "4.1.0",
        "System.Threading": "4.0.11",
        "System.Threading.Tasks": "4.0.11",
        "System.Xml.ReaderWriter": "4.0.11",
        "System.Xml.XDocument": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
    }
}
```

<span data-ttu-id="7205a-137">Das sind ziemlich viele Pakete, von denen viele zum Erweitern von Sammlungstypen sicherlich nicht benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="7205a-137">That's quite a lot of packages, many of which certainly aren't necessary for extending collection types.</span></span>  <span data-ttu-id="7205a-138">Sie können Pakete entweder manuell entfernen oder ein Tool wie z.B. [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) oder [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector/) verwenden, um zu bestimmen, welche Pakete Ihr Code tatsächlich verwendet.</span><span class="sxs-lookup"><span data-stu-id="7205a-138">You can either remove packages manually or use a tool such as [ILSpy](https://github.com/icsharpcode/ILSpy#ilspy-------) or [.NET Reflector](https://www.red-gate.com/products/dotnet-development/reflector/) to identify which packages your code actually uses.</span></span>

<span data-ttu-id="7205a-139">So könnte ein eingeschränktes Paket aussehen:</span><span class="sxs-lookup"><span data-stu-id="7205a-139">Here's what a trimmed package could look like:</span></span>

```json
{
    "dependencies":{
        "Microsoft.NETCore.Platforms": "1.0.1",
        "Microsoft.NETCore.Runtime": "1.0.2",
        "System.Collections": "4.0.11",
        "System.Linq": "4.1.0",
        "System.Runtime": "4.1.0",
        "System.Runtime.Extensions": "4.1.0",
        "System.Runtime.Handles": "4.0.1",
        "System.Runtime.InteropServices": "4.1.0",
        "System.Runtime.InteropServices.RuntimeInformation": "4.0.0",
        "System.Threading.Tasks": "4.0.11"
    },
    "frameworks":{
        "netstandard1.0": {}
     }
}
```

<span data-ttu-id="7205a-140">Nun hat es einen geringeren Speicherbedarf als wenn es vom `NETStandard.Library`-Metapaket abhängen würde.</span><span class="sxs-lookup"><span data-stu-id="7205a-140">Now, it has a smaller footprint than if it had depended on the `NETStandard.Library` metapackage.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
