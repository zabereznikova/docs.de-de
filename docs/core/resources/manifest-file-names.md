---
title: Generieren von Manifestdateinamen mit MSBuild
description: Beschreibt die Faktoren bei der Benennung von Manifestdateien von Ressourcen beim Kompilieren mit MSBuild
ms.date: 05/08/2020
ms.topic: conceptual
ms.openlocfilehash: 383bf6a077b0631e70ddaa4721b20e992127a73c
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "97866381"
---
# <a name="how-resource-manifest-files-are-named"></a><span data-ttu-id="6ed68-103">Benennen von Manifestdateien von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="6ed68-103">How resource manifest files are named</span></span>

<span data-ttu-id="6ed68-104">Wenn MSBuild ein .NET Core-Projekt kompiliert, werden XML-Ressourcendateien mit der Dateierweiterung *.resx* in *.resources*-Binärdateien konvertiert.</span><span class="sxs-lookup"><span data-stu-id="6ed68-104">When MSBuild compiles a .NET Core project, XML resource files, which have the *.resx* file extension, are converted into binary *.resources* files.</span></span> <span data-ttu-id="6ed68-105">Die Binärdateien werden in die Ausgabe des Compilers eingebettet und können vom <xref:System.Resources.ResourceManager> gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="6ed68-105">The binary files are embedded into the output of the compiler and can be read by the <xref:System.Resources.ResourceManager>.</span></span> <span data-ttu-id="6ed68-106">In diesem Artikel wird beschrieben, wie MSBuild die Namen für die jeweiligen *.resources*-Dateien auswählt.</span><span class="sxs-lookup"><span data-stu-id="6ed68-106">This article describes how MSBuild chooses a name for each *.resources* file.</span></span>

> [!TIP]
> <span data-ttu-id="6ed68-107">Wenn Sie der Projektdatei explizit ein Ressourcenelement hinzufügen und dieses auch [in den standardmäßigen Include-Globs für .NET Core](../project-sdk/overview.md#default-compilation-includes) enthalten ist, erhalten Sie einen Buildfehler.</span><span class="sxs-lookup"><span data-stu-id="6ed68-107">If you explicitly add a resource item to your project file, and it's also [included with the default include globs for .NET Core](../project-sdk/overview.md#default-compilation-includes), you will get a build error.</span></span> <span data-ttu-id="6ed68-108">Um Ressourcendateien manuell als `EmbeddedResource`-Elemente einzubeziehen, legen Sie die `EnableDefaultEmbeddedResourceItems`-Eigenschaft auf „false“ fest.</span><span class="sxs-lookup"><span data-stu-id="6ed68-108">To manually include resource files as `EmbeddedResource` items, set the `EnableDefaultEmbeddedResourceItems` property to false.</span></span>

## <a name="default-name"></a><span data-ttu-id="6ed68-109">Standardname</span><span class="sxs-lookup"><span data-stu-id="6ed68-109">Default name</span></span>

<span data-ttu-id="6ed68-110">In .NET Core 3.0 und höher wird für ein Ressourcenmanifest der Standardname verwendet, wenn die beiden folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="6ed68-110">In .NET Core 3.0 and later, the default name for a resource manifest is used when both of the following conditions are met:</span></span>

- <span data-ttu-id="6ed68-111">Die Ressourcendatei ist nicht explizit in der Projektdatei als `EmbeddedResource`-Element mit den Metadaten `LogicalName`, `ManifestResourceName` oder `DependentUpon` enthalten.</span><span class="sxs-lookup"><span data-stu-id="6ed68-111">The resource file is not explicitly included in the project file as an `EmbeddedResource` item with `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata.</span></span>
- <span data-ttu-id="6ed68-112">Die `EmbeddedResourceUseDependentUponConvention`-Eigenschaft ist in der Projektdatei nicht auf `false` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6ed68-112">The `EmbeddedResourceUseDependentUponConvention` property is not set to `false` in the project file.</span></span> <span data-ttu-id="6ed68-113">Standardmäßig ist diese Eigenschaft auf `true`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6ed68-113">By default, this property is set to `true`.</span></span> <span data-ttu-id="6ed68-114">Weitere Informationen finden Sie unter [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention).</span><span class="sxs-lookup"><span data-stu-id="6ed68-114">For more information, see [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention).</span></span>

<span data-ttu-id="6ed68-115">Wenn die Ressourcendatei mit einer Quelldatei ( *.cs* oder *.vb*) desselben Stammdateinamens zusammengestellt wird, wird der vollständige Name des ersten Typs, der in der Quelldatei definiert ist, als Manifestdateiname verwendet.</span><span class="sxs-lookup"><span data-stu-id="6ed68-115">If the resource file is colocated with a source file (*.cs* or *.vb*) of the same root file name, the full name of the first type that's defined in the source file is used for the manifest file name.</span></span> <span data-ttu-id="6ed68-116">Wenn beispielsweise `MyNamespace.Form1` der erste Typ ist, der in der *Form1.cs*-Datei definiert ist, und *Form1.cs* mit *Form1.resx* angeordnet ist, lautet der generierte Manifestname für diese Ressourcendatei *MyNamespace.Form1.resources*.</span><span class="sxs-lookup"><span data-stu-id="6ed68-116">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, and *Form1.cs* is colocated with *Form1.resx*, the generated manifest name for that resource file is *MyNamespace.Form1.resources*.</span></span>

## <a name="logicalname-metadata"></a><span data-ttu-id="6ed68-117">LogicalName-Metadaten</span><span class="sxs-lookup"><span data-stu-id="6ed68-117">LogicalName metadata</span></span>

<span data-ttu-id="6ed68-118">Wenn eine Ressourcendatei explizit in der Projektdatei als `EmbeddedResource`-Element mit `LogicalName`-Metadaten enthalten ist, wird der `LogicalName`-Wert als Manifestname verwendet.</span><span class="sxs-lookup"><span data-stu-id="6ed68-118">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `LogicalName` metadata, the `LogicalName` value is used as the manifest name.</span></span> <span data-ttu-id="6ed68-119">`LogicalName` hat Vorrang vor anderen Metadaten oder Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="6ed68-119">`LogicalName` takes precedence over any other metadata or setting.</span></span>

<span data-ttu-id="6ed68-120">Beispielsweise lautet der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, *SomeName.resources*.</span><span class="sxs-lookup"><span data-stu-id="6ed68-120">For example, the manifest name for the resource file that's defined in the following project file snippet is *SomeName.resources*.</span></span>

```xml
<EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
```

<span data-ttu-id="6ed68-121">Oder</span><span class="sxs-lookup"><span data-stu-id="6ed68-121">-or-</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
```

## <a name="manifestresourcename-metadata"></a><span data-ttu-id="6ed68-122">ManifestResourceName-Metadaten</span><span class="sxs-lookup"><span data-stu-id="6ed68-122">ManifestResourceName metadata</span></span>

<span data-ttu-id="6ed68-123">Wenn eine Ressourcendatei explizit in der Projektdatei als `EmbeddedResource`-Element mit `ManifestResourceName`-Metadaten enthalten ist (und `LogicalName` fehlt), wird als Manifestdateiname der `ManifestResourceName`-Wert in Kombination mit der Dateierweiterung *.resources* verwendet.</span><span class="sxs-lookup"><span data-stu-id="6ed68-123">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `ManifestResourceName` metadata (and `LogicalName` is absent), the `ManifestResourceName` value, combined with the file extension *.resources*, is used as the manifest file name.</span></span>

<span data-ttu-id="6ed68-124">Beispielsweise lautet der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, *SomeName.resources*.</span><span class="sxs-lookup"><span data-stu-id="6ed68-124">For example, the manifest name for the resource file that's defined in the following project file snippet is *SomeName.resources*.</span></span>

```xml
<EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
```

<span data-ttu-id="6ed68-125">Der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, lautet *SomeName.resources*.</span><span class="sxs-lookup"><span data-stu-id="6ed68-125">The manifest name for the resource file that's defined in the following project file snippet is *SomeName.fr-FR.resources*.</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
```

## <a name="dependentupon-metadata"></a><span data-ttu-id="6ed68-126">DependentUpon-Metadaten</span><span class="sxs-lookup"><span data-stu-id="6ed68-126">DependentUpon metadata</span></span>

<span data-ttu-id="6ed68-127">Wenn eine Ressourcendatei explizit in der Projektdatei als `EmbeddedResource`-Element mit `DependentUpon`-Metadaten enthalten ist (und sowohl `LogicalName` als auch `ManifestResourceName` fehlen), werden Informationen aus der Quelldatei, die von `DependentUpon` definiert werden, für den Dateinamen des Ressourcenmanifests verwendet.</span><span class="sxs-lookup"><span data-stu-id="6ed68-127">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `DependentUpon` metadata (and `LogicalName` and `ManifestResourceName` are absent), information from the source file defined by `DependentUpon` is used for the resource manifest file name.</span></span> <span data-ttu-id="6ed68-128">Genauer gesagt wird der Name des ersten Typs, der in der Quelldatei definiert ist, wie folgt im Manifestnamen verwendet: *Namespace.Classname\[.Culture].resources*.</span><span class="sxs-lookup"><span data-stu-id="6ed68-128">Specifically, the name of the first type that's defined in the source file is used in the manifest name as follows: *Namespace.Classname\[.Culture].resources*.</span></span>

<span data-ttu-id="6ed68-129">Beispielsweise lautet der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, *Namespace.Classname.resources* (wobei `Namespace.Classname` die erste Klasse ist, die in *MyTypes.cs* definiert ist).</span><span class="sxs-lookup"><span data-stu-id="6ed68-129">For example, the manifest name for the resource file that's defined in the following project file snippet is *Namespace.Classname.resources* (where `Namespace.Classname` is the first class that's defined in *MyTypes.cs*).</span></span>

```xml
<EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
```

<span data-ttu-id="6ed68-130">Der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, lautet *Namespace.Classname.fr-FR.resources* (wobei `Namespace.Classname` die erste Klasse ist, die in *MyTypes.cs* definiert ist).</span><span class="sxs-lookup"><span data-stu-id="6ed68-130">The manifest name for the resource file that's defined in the following project file snippet is *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the first class that's defined in *MyTypes.cs*).</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
```

## <a name="embeddedresourceusedependentuponconvention-property"></a><span data-ttu-id="6ed68-131">EmbeddedResourceUseDependentUponConvention-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="6ed68-131">EmbeddedResourceUseDependentUponConvention property</span></span>

<span data-ttu-id="6ed68-132">Wenn `EmbeddedResourceUseDependentUponConvention` auf `false` in der Projektdatei festgelegt ist, basieren die Manifestdateinamen der jeweiligen Ressourcen auf dem Stammnamespace für das Projekt und auf dem relativen Pfad vom Projektstamm zur *.resx*-Datei.</span><span class="sxs-lookup"><span data-stu-id="6ed68-132">If `EmbeddedResourceUseDependentUponConvention` is set to `false` in the project file, each resource manifest file name is based off the root namespace for the project and the relative path from the project root to the *.resx* file.</span></span> <span data-ttu-id="6ed68-133">Genauer gesagt lautet der Name der generierten Manifestdatei der Ressource *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span><span class="sxs-lookup"><span data-stu-id="6ed68-133">More specifically, the generated resource manifest file name is *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span></span> <span data-ttu-id="6ed68-134">Diese Logik wird auch verwendet, um Manifestnamen in .NET Core-Versionen vor 3.0 zu generieren.</span><span class="sxs-lookup"><span data-stu-id="6ed68-134">This is also the logic used to generate manifest names in .NET Core versions prior to 3.0.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="6ed68-135">Wenn `RootNamespace` nicht definiert ist, wird standardmäßig der Projektname verwendet.</span><span class="sxs-lookup"><span data-stu-id="6ed68-135">If `RootNamespace` is not defined, it defaults to the project name.</span></span>
> - <span data-ttu-id="6ed68-136">Wenn `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für ein `EmbeddedResource`-Element in der Projektdatei angegeben werden, gilt diese Benennungsregel nicht für diese Ressourcendatei.</span><span class="sxs-lookup"><span data-stu-id="6ed68-136">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item in the project file, this naming rule does not apply to that resource file.</span></span>

## <a name="see-also"></a><span data-ttu-id="6ed68-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ed68-137">See also</span></span>

- [<span data-ttu-id="6ed68-138">Funktionsweise der Benennung von Manifestressourcen</span><span class="sxs-lookup"><span data-stu-id="6ed68-138">How Manifest Resource Naming Works</span></span>](https://gist.github.com/BenVillalobos/041673b9a73bec60fdc3bf0f86fae62a)
- [<span data-ttu-id="6ed68-139">MSBuild-Eigenschaften für .NET Core SDK-Projekte</span><span class="sxs-lookup"><span data-stu-id="6ed68-139">MSBuild properties for .NET Core SDK projects</span></span>](../project-sdk/msbuild-props.md)
- [<span data-ttu-id="6ed68-140">Breaking Changes in MSBuild</span><span class="sxs-lookup"><span data-stu-id="6ed68-140">MSBuild breaking changes</span></span>](../compatibility/msbuild.md)
