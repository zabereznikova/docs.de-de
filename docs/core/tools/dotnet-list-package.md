---
title: Befehl „dotnet list package“
description: Der Befehl „dotnet list package“ bietet eine praktische Option zum Listen von Pakettverweisen auf ein Projekt oder eine Projektmappe.
ms.date: 04/09/2019
ms.openlocfilehash: 88ef3302a955eadc4167384312e4eb721dd496fb
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631768"
---
# <a name="dotnet-list-package"></a><span data-ttu-id="5f9c7-103">dotnet list package</span><span class="sxs-lookup"><span data-stu-id="5f9c7-103">dotnet list package</span></span>

[!INCLUDE [topic-appliesto-net-core-22plus](../../../includes/topic-appliesto-net-core-22plus.md)]

## <a name="name"></a><span data-ttu-id="5f9c7-104">name</span><span class="sxs-lookup"><span data-stu-id="5f9c7-104">Name</span></span>

<span data-ttu-id="5f9c7-105">`dotnet list package`: Hiermit listen Sie die Paketverweise für ein Projekt oder eine Projektmappe auf.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-105">`dotnet list package` - Lists the package references for a project or solution.</span></span>

## <a name="synopsis"></a><span data-ttu-id="5f9c7-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="5f9c7-106">Synopsis</span></span>

```
dotnet list [<PROJECT | SOLUTION>] package [--config] [--framework] [--highest-minor] [--highest-patch] 
   [--include-prerelease] [--include-transitive] [--outdated] [--source]
dotnet list package [-h|--help]
```

## <a name="description"></a><span data-ttu-id="5f9c7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f9c7-107">Description</span></span>

<span data-ttu-id="5f9c7-108">Der Befehl `dotnet list package` bietet eine praktische Option zum Listen aller NuGet-Pakettverweise auf ein bestimmtes Projekt oder eine Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-108">The `dotnet list package` command provides a convenient option to list all NuGet package references for a specific project or a solution.</span></span> <span data-ttu-id="5f9c7-109">Sie müssen zuerst das Projekt erstellen, um die Ressourcen zu haben, die für diesen Befehl zur Verarbeitung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-109">You first need to build the project in order to have the assets needed for this command to process.</span></span> <span data-ttu-id="5f9c7-110">Das folgende Beispiel zeigt die Ausgabe des Befehls `dotnet list package` für das Projekt [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis):</span><span class="sxs-lookup"><span data-stu-id="5f9c7-110">The following example shows the output of the `dotnet list package` command for the [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) project:</span></span>

```output
Project 'SentimentAnalysis' has the following package references
   [netcoreapp2.1]:
   Top-level Package               Requested   Resolved
   > Microsoft.ML                  0.11.0      0.11.0
   > Microsoft.NETCore.App   (A)   [2.1.0, )   2.1.0

(A) : Auto-referenced package.
```

<span data-ttu-id="5f9c7-111">Die Spalte **Angefordert** bezieht sich auf die in der Projektdatei angegebene Paketversion und kann ein Bereich sein.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-111">The **Requested** column refers to the package version specified in the project file and can be a range.</span></span> <span data-ttu-id="5f9c7-112">Die Spalte **Gelöst** listet die Version auf, die das Projekt gerade verwendet, und ist immer ein Einzelwert.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-112">The **Resolved** column lists the version that the project is currently using and is always a single value.</span></span> <span data-ttu-id="5f9c7-113">Die Pakete, die ein `(A)` direkt neben ihren Namen anzeigen, repräsentieren [implizite Paketverweise](csproj.md#implicit-package-references), die aus Ihren Projekteinstellungen abgeleitet werden (Typ `Sdk`, Eigenschaft `<TargetFramework>` oder `<TargetFrameworks>`, etc.).</span><span class="sxs-lookup"><span data-stu-id="5f9c7-113">The packages displaying an `(A)` right next to their names represent [implicit package references](csproj.md#implicit-package-references) that are inferred from your project settings (`Sdk` type, `<TargetFramework>` or `<TargetFrameworks>` property, etc.)</span></span>

<span data-ttu-id="5f9c7-114">Verwenden Sie die Option `--outdated`, um herauszufinden, ob es neuere Versionen der Pakete gibt, die Sie in Ihren Projekten verwenden.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-114">Use the `--outdated` option to find out if there are newer versions available of the packages you're using in your projects.</span></span> <span data-ttu-id="5f9c7-115">Standardmäßig listet `--outdated` die neuesten stabilen Pakete auf, es sei denn, die gelöste Version ist auch eine Vorabversion.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-115">By default, `--outdated` lists the latest stable packages unless the resolved version is also a prerelease version.</span></span> <span data-ttu-id="5f9c7-116">Um Vorabversionen in die Liste neuerer Versionen aufzunehmen, geben Sie auch die Option `--include-prerelease` an.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-116">To include prerelease versions when listing newer versions, also specify the `--include-prerelease` option.</span></span> <span data-ttu-id="5f9c7-117">Die folgenden Beispiele zeigen die Ausgabe des Befehls `dotnet list package --outdated --include-prerelease` für das gleiche Projekt wie das vorherige Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5f9c7-117">The following examples shows the output of the `dotnet list package --outdated --include-prerelease` command for the same project as the previous example:</span></span>

```output
The following sources were used:
   https://api.nuget.org/v3/index.json

Project `SentimentAnalysis` has the following updates to its packages
   [netcoreapp2.1]:
   Top-level Package      Requested   Resolved   Latest
   > Microsoft.ML         0.11.0      0.11.0     1.0.0-preview
```

<span data-ttu-id="5f9c7-118">Wenn Sie herausfinden möchten, ob Ihr Projekt transitive Abhängigkeiten aufweist, verwenden Sie die Option `--include-transitive`.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-118">If you need to find out whether your project has transitive dependencies, use the `--include-transitive` option.</span></span> <span data-ttu-id="5f9c7-119">Transitive Abhängigkeiten treten auf, wenn Sie ein Paket zu Ihrem Projekt hinzufügen, das wiederum von einem anderen Paket abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-119">Transitive dependencies occur when you add a package to your project that in turn relies on another package.</span></span> <span data-ttu-id="5f9c7-120">Das folgende Beispiel zeigt die Ausgabe des Befehls `dotnet list package --include-transitive` für das Projekt [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin), das Pakete auf oberster Ebene und die von ihnen abhängigen Pakete anzeigt:</span><span class="sxs-lookup"><span data-stu-id="5f9c7-120">The following example shows the output from running the `dotnet list package --include-transitive` command for the [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) project, which displays top-level packages and the packages they depend on:</span></span>

```output
Project 'HelloPlugin' has the following package references
   [netcoreapp3.0]:
   Top-level Package                      Requested                    Resolved
   > Microsoft.NETCore.Platforms    (A)   [3.0.0-preview3.19128.7, )   3.0.0-preview3.19128.7
   > Microsoft.WindowsDesktop.App   (A)   [3.0.0-preview3-27504-2, )   3.0.0-preview3-27504-2

   Transitive Package               Resolved
   > Microsoft.NETCore.Targets      2.0.0
   > PluginBase                     1.0.0

(A) : Auto-referenced package.
```

## <a name="arguments"></a><span data-ttu-id="5f9c7-121">Argumente</span><span class="sxs-lookup"><span data-stu-id="5f9c7-121">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="5f9c7-122">Die zu verwendende Projekt- oder Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-122">The project or solution file to operate on.</span></span> <span data-ttu-id="5f9c7-123">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-123">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="5f9c7-124">Wenn mehr als eine Projektmappe oder ein Projekt gefunden wird, wird ein Fehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-124">If more than one solution or project is found, an error is thrown.</span></span>

## <a name="options"></a><span data-ttu-id="5f9c7-125">Optionen</span><span class="sxs-lookup"><span data-stu-id="5f9c7-125">Options</span></span>

* **`--config <SOURCE>`**

  <span data-ttu-id="5f9c7-126">Die bei der Suche nach neueren Paketen zu verwendenden NuGet-Quellen.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-126">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="5f9c7-127">Hierfür ist die Option `--outdated` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-127">Requires the `--outdated` option.</span></span>

* **`--framework <FRAMEWORK>`**

  <span data-ttu-id="5f9c7-128">Zeigt nur die Pakete an, die für das angegebene [Zielframework](../../standard/frameworks.md) gelten.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-128">Displays only the packages applicable for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="5f9c7-129">Um mehrere Frameworks anzugeben, wiederholen Sie die Option mehrmals.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-129">To specify multiple frameworks, repeat the option multiple times.</span></span> <span data-ttu-id="5f9c7-130">Beispiel: `--framework netcoreapp2.2 --framework netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-130">For example: `--framework netcoreapp2.2 --framework netstandard2.0`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="5f9c7-131">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-131">Prints out a short help for the command.</span></span>

* **`--highest-minor`**

  <span data-ttu-id="5f9c7-132">Hiermit werden bei der Suche nach neueren Paketen nur die Pakete mit übereinstimmender Hauptversionsnummer berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-132">Considers only the packages with a matching major version number when searching for newer packages.</span></span> <span data-ttu-id="5f9c7-133">Hierfür ist die Option `--outdated` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-133">Requires the `--outdated` option.</span></span>

* **`--highest-patch`**

  <span data-ttu-id="5f9c7-134">Hiermit werden bei der Suche nach neueren Paketen nur die Pakete mit übereinstimmender Haupt- und Nebenversionsnummer berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-134">Considers only the packages with a matching major and minor version numbers when searching for newer packages.</span></span> <span data-ttu-id="5f9c7-135">Hierfür ist die Option `--outdated` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-135">Requires the `--outdated` option.</span></span>

* **`--include-prerelease`**

  <span data-ttu-id="5f9c7-136">Hiermit werden bei der Suche nach neueren Pakete auch Pakete mit Vorabversionen berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-136">Considers packages with prerelease versions when searching for newer packages.</span></span> <span data-ttu-id="5f9c7-137">Hierfür ist die Option `--outdated` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-137">Requires the `--outdated` option.</span></span>

* **`--include-transitive`**

  <span data-ttu-id="5f9c7-138">Listet transitive Pakete zusätzlich zu den Paketen auf der obersten Ebene auf.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-138">Lists transitive packages, in addition to the top-level packages.</span></span> <span data-ttu-id="5f9c7-139">Wenn Sie diese Option angeben, erhalten Sie eine Liste der Pakete, von denen die Pakete auf der obersten Ebene abhängen.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-139">When specifying this option, you get a list of packages that the top-level packages depend on.</span></span>

* **`--outdated`**

  <span data-ttu-id="5f9c7-140">Listet Pakete auf, für die neuere Versionen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-140">Lists packages that have newer versions available.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="5f9c7-141">Die bei der Suche nach neueren Paketen zu verwendenden NuGet-Quellen.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-141">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="5f9c7-142">Hierfür ist die Option `--outdated` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5f9c7-142">Requires the `--outdated` option.</span></span>

## <a name="examples"></a><span data-ttu-id="5f9c7-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="5f9c7-143">Examples</span></span>

* <span data-ttu-id="5f9c7-144">Liste der Paketverweise eines bestimmten Projekts:</span><span class="sxs-lookup"><span data-stu-id="5f9c7-144">List package references of a specific project:</span></span>

  ```console
  dotnet list SentimentAnalysis.csproj package
  ```

* <span data-ttu-id="5f9c7-145">Liste von Paketverweisen, für die neuere Versionen verfügbar sind, einschließlich Vorabversionen:</span><span class="sxs-lookup"><span data-stu-id="5f9c7-145">List package references that have newer versions available, including prerelease versions:</span></span>

  ```console
  dotnet list package --outdated --include-prerelease
  ```

* <span data-ttu-id="5f9c7-146">Liste von Paketverweisen für ein bestimmtes Zielframework:</span><span class="sxs-lookup"><span data-stu-id="5f9c7-146">List package references for a specific target framework:</span></span>

  ```console
  dotnet list package --framework netcoreapp3.0
  ```
