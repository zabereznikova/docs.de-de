---
title: Befehl „dotnet list package“
description: Der Befehl „dotnet list package“ bietet eine praktische Option zum Listen von Pakettverweisen auf ein Projekt oder eine Projektmappe.
ms.date: 02/14/2020
ms.openlocfilehash: 12d64600d178ea8cf490a0d6917e67bd3d8c6d21
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463662"
---
# <a name="dotnet-list-package"></a><span data-ttu-id="313ea-103">dotnet list package</span><span class="sxs-lookup"><span data-stu-id="313ea-103">dotnet list package</span></span>

<span data-ttu-id="313ea-104">**Dieser Artikel gilt für:** ✔️ .NET Core 2.2 SDK und neuere Versionen</span><span class="sxs-lookup"><span data-stu-id="313ea-104">**This article applies to:** ✔️ .NET Core 2.2 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="313ea-105">name</span><span class="sxs-lookup"><span data-stu-id="313ea-105">Name</span></span>

<span data-ttu-id="313ea-106">`dotnet list package`: Hiermit listen Sie die Paketverweise für ein Projekt oder eine Projektmappe auf.</span><span class="sxs-lookup"><span data-stu-id="313ea-106">`dotnet list package` - Lists the package references for a project or solution.</span></span>

## <a name="synopsis"></a><span data-ttu-id="313ea-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="313ea-107">Synopsis</span></span>

```dotnetcli
dotnet list [<PROJECT>|<SOLUTION>] package [--config <SOURCE>]
    [--framework <FRAMEWORK>] [--highest-minor] [--highest-patch]
    [--include-prerelease] [--include-transitive] [--interactive]
    [--outdated] [--source <SOURCE>]

dotnet list package -h|--help
```

## <a name="description"></a><span data-ttu-id="313ea-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="313ea-108">Description</span></span>

<span data-ttu-id="313ea-109">Der Befehl `dotnet list package` bietet eine praktische Option zum Listen aller NuGet-Pakettverweise auf ein bestimmtes Projekt oder eine Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="313ea-109">The `dotnet list package` command provides a convenient option to list all NuGet package references for a specific project or a solution.</span></span> <span data-ttu-id="313ea-110">Sie müssen zuerst das Projekt erstellen, um die Ressourcen zu haben, die für diesen Befehl zur Verarbeitung benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="313ea-110">You first need to build the project in order to have the assets needed for this command to process.</span></span> <span data-ttu-id="313ea-111">Das folgende Beispiel zeigt die Ausgabe des Befehls `dotnet list package` für das Projekt [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis):</span><span class="sxs-lookup"><span data-stu-id="313ea-111">The following example shows the output of the `dotnet list package` command for the [SentimentAnalysis](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) project:</span></span>

```output
Project 'SentimentAnalysis' has the following package references
   [netcoreapp2.1]:
   Top-level Package               Requested   Resolved
   > Microsoft.ML                  1.4.0       1.4.0
   > Microsoft.NETCore.App   (A)   [2.1.0, )   2.1.0

(A) : Auto-referenced package.
```

<span data-ttu-id="313ea-112">Die Spalte **Angefordert** bezieht sich auf die in der Projektdatei angegebene Paketversion und kann ein Bereich sein.</span><span class="sxs-lookup"><span data-stu-id="313ea-112">The **Requested** column refers to the package version specified in the project file and can be a range.</span></span> <span data-ttu-id="313ea-113">Die Spalte **Gelöst** listet die Version auf, die das Projekt gerade verwendet, und ist immer ein Einzelwert.</span><span class="sxs-lookup"><span data-stu-id="313ea-113">The **Resolved** column lists the version that the project is currently using and is always a single value.</span></span> <span data-ttu-id="313ea-114">Die Pakete, die ein `(A)` direkt neben ihren Namen anzeigen, repräsentieren [implizite Paketverweise](csproj.md#implicit-package-references), die aus Ihren Projekteinstellungen abgeleitet werden (Typ `Sdk`, Eigenschaft `<TargetFramework>` oder `<TargetFrameworks>`, etc.).</span><span class="sxs-lookup"><span data-stu-id="313ea-114">The packages displaying an `(A)` right next to their names represent [implicit package references](csproj.md#implicit-package-references) that are inferred from your project settings (`Sdk` type, `<TargetFramework>` or `<TargetFrameworks>` property, etc.)</span></span>

<span data-ttu-id="313ea-115">Verwenden Sie die Option `--outdated`, um herauszufinden, ob es neuere Versionen der Pakete gibt, die Sie in Ihren Projekten verwenden.</span><span class="sxs-lookup"><span data-stu-id="313ea-115">Use the `--outdated` option to find out if there are newer versions available of the packages you're using in your projects.</span></span> <span data-ttu-id="313ea-116">Standardmäßig listet `--outdated` die neuesten stabilen Pakete auf, es sei denn, die gelöste Version ist auch eine Vorabversion.</span><span class="sxs-lookup"><span data-stu-id="313ea-116">By default, `--outdated` lists the latest stable packages unless the resolved version is also a prerelease version.</span></span> <span data-ttu-id="313ea-117">Um Vorabversionen in die Liste neuerer Versionen aufzunehmen, geben Sie auch die Option `--include-prerelease` an.</span><span class="sxs-lookup"><span data-stu-id="313ea-117">To include prerelease versions when listing newer versions, also specify the `--include-prerelease` option.</span></span> <span data-ttu-id="313ea-118">Die folgenden Beispiele zeigen die Ausgabe des Befehls `dotnet list package --outdated --include-prerelease` für das gleiche Projekt wie das vorherige Beispiel:</span><span class="sxs-lookup"><span data-stu-id="313ea-118">The following examples shows the output of the `dotnet list package --outdated --include-prerelease` command for the same project as the previous example:</span></span>

```output
The following sources were used:
   https://api.nuget.org/v3/index.json
   C:\Program Files (x86)\Microsoft SDKs\NuGetPackages\

Project `SentimentAnalysis` has the following updates to its packages
   [netcoreapp2.1]:
   Top-level Package      Requested   Resolved   Latest
   > Microsoft.ML         1.4.0       1.4.0      1.5.0-preview
```

<span data-ttu-id="313ea-119">Wenn Sie herausfinden möchten, ob Ihr Projekt transitive Abhängigkeiten aufweist, verwenden Sie die Option `--include-transitive`.</span><span class="sxs-lookup"><span data-stu-id="313ea-119">If you need to find out whether your project has transitive dependencies, use the `--include-transitive` option.</span></span> <span data-ttu-id="313ea-120">Transitive Abhängigkeiten treten auf, wenn Sie ein Paket zu Ihrem Projekt hinzufügen, das wiederum von einem anderen Paket abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="313ea-120">Transitive dependencies occur when you add a package to your project that in turn relies on another package.</span></span> <span data-ttu-id="313ea-121">Das folgende Beispiel zeigt die Ausgabe des Befehls `dotnet list package --include-transitive` für das Projekt [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin), das Pakete auf oberster Ebene und die von ihnen abhängigen Pakete anzeigt:</span><span class="sxs-lookup"><span data-stu-id="313ea-121">The following example shows the output from running the `dotnet list package --include-transitive` command for the [HelloPlugin](https://github.com/dotnet/samples/tree/master/core/extensions/AppWithPlugin/HelloPlugin) project, which displays top-level packages and the packages they depend on:</span></span>

```output
Project 'HelloPlugin' has the following package references
   [netcoreapp3.0]:
   Transitive Package      Resolved
   > PluginBase            1.0.0
```

## <a name="arguments"></a><span data-ttu-id="313ea-122">Argumente</span><span class="sxs-lookup"><span data-stu-id="313ea-122">Arguments</span></span>

`PROJECT | SOLUTION`

<span data-ttu-id="313ea-123">Die zu verwendende Projekt- oder Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="313ea-123">The project or solution file to operate on.</span></span> <span data-ttu-id="313ea-124">Wenn keine angegeben ist, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="313ea-124">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="313ea-125">Wenn mehr als eine Projektmappe oder ein Projekt gefunden wird, wird ein Fehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="313ea-125">If more than one solution or project is found, an error is thrown.</span></span>

## <a name="options"></a><span data-ttu-id="313ea-126">Optionen</span><span class="sxs-lookup"><span data-stu-id="313ea-126">Options</span></span>

- **`--config <SOURCE>`**

  <span data-ttu-id="313ea-127">Die bei der Suche nach neueren Paketen zu verwendenden NuGet-Quellen.</span><span class="sxs-lookup"><span data-stu-id="313ea-127">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="313ea-128">Hierfür ist die Option `--outdated` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="313ea-128">Requires the `--outdated` option.</span></span>

- **`--framework <FRAMEWORK>`**

  <span data-ttu-id="313ea-129">Zeigt nur die Pakete an, die für das angegebene [Zielframework](../../standard/frameworks.md) gelten.</span><span class="sxs-lookup"><span data-stu-id="313ea-129">Displays only the packages applicable for the specified [target framework](../../standard/frameworks.md).</span></span> <span data-ttu-id="313ea-130">Um mehrere Frameworks anzugeben, wiederholen Sie die Option mehrmals.</span><span class="sxs-lookup"><span data-stu-id="313ea-130">To specify multiple frameworks, repeat the option multiple times.</span></span> <span data-ttu-id="313ea-131">Beispiel: `--framework netcoreapp2.2 --framework netstandard2.0`.</span><span class="sxs-lookup"><span data-stu-id="313ea-131">For example: `--framework netcoreapp2.2 --framework netstandard2.0`.</span></span>

- **`-h|--help`**

  <span data-ttu-id="313ea-132">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="313ea-132">Prints out a short help for the command.</span></span>

- **`--highest-minor`**

  <span data-ttu-id="313ea-133">Hiermit werden bei der Suche nach neueren Paketen nur die Pakete mit übereinstimmender Hauptversionsnummer berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="313ea-133">Considers only the packages with a matching major version number when searching for newer packages.</span></span> <span data-ttu-id="313ea-134">Hierfür ist die Option `--outdated` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="313ea-134">Requires the `--outdated` option.</span></span>

- **`--highest-patch`**

  <span data-ttu-id="313ea-135">Hiermit werden bei der Suche nach neueren Paketen nur die Pakete mit übereinstimmender Haupt- und Nebenversionsnummer berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="313ea-135">Considers only the packages with a matching major and minor version numbers when searching for newer packages.</span></span> <span data-ttu-id="313ea-136">Hierfür ist die Option `--outdated` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="313ea-136">Requires the `--outdated` option.</span></span>

- **`--include-prerelease`**

  <span data-ttu-id="313ea-137">Hiermit werden bei der Suche nach neueren Pakete auch Pakete mit Vorabversionen berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="313ea-137">Considers packages with prerelease versions when searching for newer packages.</span></span> <span data-ttu-id="313ea-138">Hierfür ist die Option `--outdated` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="313ea-138">Requires the `--outdated` option.</span></span>

- **`--include-transitive`**

  <span data-ttu-id="313ea-139">Listet transitive Pakete zusätzlich zu den Paketen auf der obersten Ebene auf.</span><span class="sxs-lookup"><span data-stu-id="313ea-139">Lists transitive packages, in addition to the top-level packages.</span></span> <span data-ttu-id="313ea-140">Wenn Sie diese Option angeben, erhalten Sie eine Liste der Pakete, von denen die Pakete auf der obersten Ebene abhängen.</span><span class="sxs-lookup"><span data-stu-id="313ea-140">When specifying this option, you get a list of packages that the top-level packages depend on.</span></span>

- **`--interactive`**

  <span data-ttu-id="313ea-141">Ermöglicht dem Befehl, anzuhalten und auf Benutzereingaben oder Aktionen zu warten.</span><span class="sxs-lookup"><span data-stu-id="313ea-141">Allows the command to stop and wait for user input or action.</span></span> <span data-ttu-id="313ea-142">Beispielsweise, um die Authentifizierung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="313ea-142">For example, to complete authentication.</span></span> <span data-ttu-id="313ea-143">Verfügbar seit .NET Core 3.0 SDK.</span><span class="sxs-lookup"><span data-stu-id="313ea-143">Available since .NET Core 3.0 SDK.</span></span>

- **`--outdated`**

  <span data-ttu-id="313ea-144">Listet Pakete auf, für die neuere Versionen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="313ea-144">Lists packages that have newer versions available.</span></span>

- **`-s|--source <SOURCE>`**

  <span data-ttu-id="313ea-145">Die bei der Suche nach neueren Paketen zu verwendenden NuGet-Quellen.</span><span class="sxs-lookup"><span data-stu-id="313ea-145">The NuGet sources to use when searching for newer packages.</span></span> <span data-ttu-id="313ea-146">Hierfür ist die Option `--outdated` erforderlich.</span><span class="sxs-lookup"><span data-stu-id="313ea-146">Requires the `--outdated` option.</span></span>

## <a name="examples"></a><span data-ttu-id="313ea-147">Beispiele</span><span class="sxs-lookup"><span data-stu-id="313ea-147">Examples</span></span>

- <span data-ttu-id="313ea-148">Liste der Paketverweise eines bestimmten Projekts:</span><span class="sxs-lookup"><span data-stu-id="313ea-148">List package references of a specific project:</span></span>

  ```dotnetcli
  dotnet list SentimentAnalysis.csproj package
  ```

- <span data-ttu-id="313ea-149">Liste von Paketverweisen, für die neuere Versionen verfügbar sind, einschließlich Vorabversionen:</span><span class="sxs-lookup"><span data-stu-id="313ea-149">List package references that have newer versions available, including prerelease versions:</span></span>

  ```dotnetcli
  dotnet list package --outdated --include-prerelease
  ```

- <span data-ttu-id="313ea-150">Liste von Paketverweisen für ein bestimmtes Zielframework:</span><span class="sxs-lookup"><span data-stu-id="313ea-150">List package references for a specific target framework:</span></span>

  ```dotnetcli
  dotnet list package --framework netcoreapp3.0
  ```
