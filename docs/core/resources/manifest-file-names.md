---
title: Generieren von Manifestdateinamen mit MSBuild
description: Beschreibt die Faktoren bei der Benennung von Manifestdateien von Ressourcen beim Kompilieren mit MSBuild
ms.date: 05/08/2020
ms.topic: conceptual
ms.openlocfilehash: 2e0461e34bbd7f8da35bea1db1913a32915c7117
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970680"
---
# <a name="how-resource-manifest-files-are-named"></a><span data-ttu-id="bb29f-103">Benennen von Manifestdateien von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="bb29f-103">How resource manifest files are named</span></span>

<span data-ttu-id="bb29f-104">Wenn MSBuild ein .NET Core-Projekt kompiliert, werden XML-Ressourcendateien mit der Dateierweiterung *.resx* in *.resources*-Binärdateien konvertiert.</span><span class="sxs-lookup"><span data-stu-id="bb29f-104">When MSBuild compiles a .NET Core project, XML resource files, which have the *.resx* file extension, are converted into binary *.resources* files.</span></span> <span data-ttu-id="bb29f-105">Die Binärdateien werden in die Ausgabe des Compilers eingebettet und können vom <xref:System.Resources.ResourceManager> gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="bb29f-105">The binary files are embedded into the output of the compiler and can be read by the <xref:System.Resources.ResourceManager>.</span></span> <span data-ttu-id="bb29f-106">In diesem Artikel wird beschrieben, wie MSBuild die Namen für die jeweiligen *.resources*-Dateien auswählt.</span><span class="sxs-lookup"><span data-stu-id="bb29f-106">This article describes how MSBuild chooses a name for each *.resources* file.</span></span>

> [!TIP]
> <span data-ttu-id="bb29f-107">Wenn Sie der Projektdatei explizit ein Ressourcenelement hinzufügen und dieses auch [in den standardmäßigen Include-Globs für .NET Core](../project-sdk/overview.md#default-includes-and-excludes) enthalten ist, erhalten Sie einen Buildfehler.</span><span class="sxs-lookup"><span data-stu-id="bb29f-107">If you explicitly add a resource item to your project file, and it's also [included with the default include globs for .NET Core](../project-sdk/overview.md#default-includes-and-excludes), you will get a build error.</span></span> <span data-ttu-id="bb29f-108">Um Ressourcendateien manuell als `EmbeddedResource`-Elemente einzubeziehen, legen Sie die `EnableDefaultEmbeddedResourceItems`-Eigenschaft auf „false“ fest.</span><span class="sxs-lookup"><span data-stu-id="bb29f-108">To manually include resource files as `EmbeddedResource` items, set the `EnableDefaultEmbeddedResourceItems` property to false.</span></span>

## <a name="default-name"></a><span data-ttu-id="bb29f-109">Standardname</span><span class="sxs-lookup"><span data-stu-id="bb29f-109">Default name</span></span>

<span data-ttu-id="bb29f-110">In .NET Core 3.0 und höher wird für ein Ressourcenmanifest der Standardname verwendet, wenn die beiden folgenden Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="bb29f-110">In .NET Core 3.0 and later, the default name for a resource manifest is used when both of the following conditions are met:</span></span>

- <span data-ttu-id="bb29f-111">Die Ressourcendatei ist nicht explizit in der Projektdatei als `EmbeddedResource`-Element mit den Metadaten `LogicalName`, `ManifestResourceName` oder `DependentUpon` enthalten.</span><span class="sxs-lookup"><span data-stu-id="bb29f-111">The resource file is not explicitly included in the project file as an `EmbeddedResource` item with `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata.</span></span>
- <span data-ttu-id="bb29f-112">Die `EmbeddedResourceUseDependentUponConvention`-Eigenschaft ist in der Projektdatei nicht auf `false` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bb29f-112">The `EmbeddedResourceUseDependentUponConvention` property is not set to `false` in the project file.</span></span> <span data-ttu-id="bb29f-113">Standardmäßig ist diese Eigenschaft auf `true`festgelegt.</span><span class="sxs-lookup"><span data-stu-id="bb29f-113">By default, this property is set to `true`.</span></span> <span data-ttu-id="bb29f-114">Weitere Informationen finden Sie unter [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention).</span><span class="sxs-lookup"><span data-stu-id="bb29f-114">For more information, see [EmbeddedResourceUseDependentUponConvention](../project-sdk/msbuild-props.md#embeddedresourceusedependentuponconvention).</span></span>

<span data-ttu-id="bb29f-115">Wenn die Ressourcendatei mit einer Quelldatei ( *.cs* oder *.vb*) desselben Stammdateinamens zusammengestellt wird, wird der vollständige Name des ersten Typs, der in der Quelldatei definiert ist, als Manifestdateiname verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb29f-115">If the resource file is colocated with a source file (*.cs* or *.vb*) of the same root file name, the full name of the first type that's defined in the source file is used for the manifest file name.</span></span> <span data-ttu-id="bb29f-116">Wenn beispielsweise `MyNamespace.Form1` der erste Typ ist, der in der *Form1.cs*-Datei definiert ist, und *Form1.cs* mit *Form1.resx* angeordnet ist, lautet der generierte Manifestname für diese Ressourcendatei *MyNamespace.Form1.resources*.</span><span class="sxs-lookup"><span data-stu-id="bb29f-116">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, and *Form1.cs* is colocated with *Form1.resx*, the generated manifest name for that resource file is *MyNamespace.Form1.resources*.</span></span>

## <a name="logicalname-metadata"></a><span data-ttu-id="bb29f-117">LogicalName-Metadaten</span><span class="sxs-lookup"><span data-stu-id="bb29f-117">LogicalName metadata</span></span>

<span data-ttu-id="bb29f-118">Wenn eine Ressourcendatei explizit in der Projektdatei als `EmbeddedResource`-Element mit `LogicalName`-Metadaten enthalten ist, wird der `LogicalName`-Wert als Manifestname verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb29f-118">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `LogicalName` metadata, the `LogicalName` value is used as the manifest name.</span></span> <span data-ttu-id="bb29f-119">`LogicalName` hat Vorrang vor anderen Metadaten oder Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="bb29f-119">`LogicalName` takes precedence over any other metadata or setting.</span></span>

<span data-ttu-id="bb29f-120">Beispielsweise lautet der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, *SomeName.resources*.</span><span class="sxs-lookup"><span data-stu-id="bb29f-120">For example, the manifest name for the resource file that's defined in the following project file snippet is *SomeName.resources*.</span></span>

```xml
<EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
```

<span data-ttu-id="bb29f-121">- oder -</span><span class="sxs-lookup"><span data-stu-id="bb29f-121">-or-</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
```

## <a name="manifestresourcename-metadata"></a><span data-ttu-id="bb29f-122">ManifestResourceName-Metadaten</span><span class="sxs-lookup"><span data-stu-id="bb29f-122">ManifestResourceName metadata</span></span>

<span data-ttu-id="bb29f-123">Wenn eine Ressourcendatei explizit in der Projektdatei als `EmbeddedResource`-Element mit `ManifestResourceName`-Metadaten enthalten ist (und `LogicalName` fehlt), wird als Manifestdateiname der `ManifestResourceName`-Wert in Kombination mit der Dateierweiterung *.resources* verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb29f-123">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `ManifestResourceName` metadata (and `LogicalName` is absent), the `ManifestResourceName` value, combined with the file extension *.resources*, is used as the manifest file name.</span></span>

<span data-ttu-id="bb29f-124">Beispielsweise lautet der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, *SomeName.resources*.</span><span class="sxs-lookup"><span data-stu-id="bb29f-124">For example, the manifest name for the resource file that's defined in the following project file snippet is *SomeName.resources*.</span></span>

```xml
<EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
```

<span data-ttu-id="bb29f-125">Der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, lautet *SomeName.resources*.</span><span class="sxs-lookup"><span data-stu-id="bb29f-125">The manifest name for the resource file that's defined in the following project file snippet is *SomeName.fr-FR.resources*.</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
```

## <a name="dependentupon-metadata"></a><span data-ttu-id="bb29f-126">DependentUpon-Metadaten</span><span class="sxs-lookup"><span data-stu-id="bb29f-126">DependentUpon metadata</span></span>

<span data-ttu-id="bb29f-127">Wenn eine Ressourcendatei explizit in der Projektdatei als `EmbeddedResource`-Element mit `DependentUpon`-Metadaten enthalten ist (und sowohl `LogicalName` als auch `ManifestResourceName` fehlen), werden Informationen aus der Quelldatei, die von `DependentUpon` definiert werden, für den Dateinamen des Ressourcenmanifests verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb29f-127">If a resource file is explicitly included in the project file as an `EmbeddedResource` item with `DependentUpon` metadata (and `LogicalName` and `ManifestResourceName` are absent), information from the source file defined by `DependentUpon` is used for the resource manifest file name.</span></span> <span data-ttu-id="bb29f-128">Genauer gesagt wird der Name des ersten Typs, der in der Quelldatei definiert ist, wie folgt im Manifestnamen verwendet: *Namespace.Classname\[.Culture].resources*.</span><span class="sxs-lookup"><span data-stu-id="bb29f-128">Specifically, the name of the first type that's defined in the source file is used in the manifest name as follows: *Namespace.Classname\[.Culture].resources*.</span></span>

<span data-ttu-id="bb29f-129">Beispielsweise lautet der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, *Namespace.Classname.resources* (wobei `Namespace.Classname` die erste Klasse ist, die in *MyTypes.cs* definiert ist).</span><span class="sxs-lookup"><span data-stu-id="bb29f-129">For example, the manifest name for the resource file that's defined in the following project file snippet is *Namespace.Classname.resources* (where `Namespace.Classname` is the first class that's defined in *MyTypes.cs*).</span></span>

```xml
<EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
```

<span data-ttu-id="bb29f-130">Der Manifestname für die Ressourcendatei, die im folgenden Projektdateiausschnitt definiert ist, lautet *Namespace.Classname.fr-FR.resources* (wobei `Namespace.Classname` die erste Klasse ist, die in *MyTypes.cs* definiert ist).</span><span class="sxs-lookup"><span data-stu-id="bb29f-130">The manifest name for the resource file that's defined in the following project file snippet is *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the first class that's defined in *MyTypes.cs*).</span></span>

```xml
<EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
```

## <a name="embeddedresourceusedependentuponconvention-property"></a><span data-ttu-id="bb29f-131">EmbeddedResourceUseDependentUponConvention-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="bb29f-131">EmbeddedResourceUseDependentUponConvention property</span></span>

<span data-ttu-id="bb29f-132">Wenn `EmbeddedResourceUseDependentUponConvention` auf `false` in der Projektdatei festgelegt ist, basieren die Manifestdateinamen der jeweiligen Ressourcen auf dem Stammnamespace für das Projekt und auf dem relativen Pfad vom Projektstamm zur *.resx*-Datei.</span><span class="sxs-lookup"><span data-stu-id="bb29f-132">If `EmbeddedResourceUseDependentUponConvention` is set to `false` in the project file, each resource manifest file name is based off the root namespace for the project and the relative path from the project root to the *.resx* file.</span></span> <span data-ttu-id="bb29f-133">Genauer gesagt lautet der Name der generierten Manifestdatei der Ressource *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span><span class="sxs-lookup"><span data-stu-id="bb29f-133">More specifically, the generated resource manifest file name is *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span></span> <span data-ttu-id="bb29f-134">Diese Logik wird auch verwendet, um Manifestnamen in .NET Core-Versionen vor 3.0 zu generieren.</span><span class="sxs-lookup"><span data-stu-id="bb29f-134">This is also the logic used to generate manifest names in .NET Core versions prior to 3.0.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="bb29f-135">Wenn `RootNamespace` nicht definiert ist, wird standardmäßig der Projektname verwendet.</span><span class="sxs-lookup"><span data-stu-id="bb29f-135">If `RootNamespace` is not defined, it defaults to the project name.</span></span>
> - <span data-ttu-id="bb29f-136">Wenn `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für ein `EmbeddedResource`-Element in der Projektdatei angegeben werden, gilt diese Benennungsregel nicht für diese Ressourcendatei.</span><span class="sxs-lookup"><span data-stu-id="bb29f-136">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item in the project file, this naming rule does not apply to that resource file.</span></span>

## <a name="see-also"></a><span data-ttu-id="bb29f-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb29f-137">See also</span></span>

- [<span data-ttu-id="bb29f-138">Funktionsweise der Benennung von Manifestressourcen</span><span class="sxs-lookup"><span data-stu-id="bb29f-138">How Manifest Resource Naming Works</span></span>](https://gist.github.com/BenVillalobos/041673b9a73bec60fdc3bf0f86fae62a)
- [<span data-ttu-id="bb29f-139">MSBuild-Eigenschaften für .NET Core SDK-Projekte</span><span class="sxs-lookup"><span data-stu-id="bb29f-139">MSBuild properties for .NET Core SDK projects</span></span>](../project-sdk/msbuild-props.md)
- [<span data-ttu-id="bb29f-140">Breaking Changes in MSBuild</span><span class="sxs-lookup"><span data-stu-id="bb29f-140">MSBuild breaking changes</span></span>](../compatibility/msbuild.md)
