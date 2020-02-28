---
ms.openlocfilehash: 276268d31670b5e7dcd0ae9c0b7a61c3c38ca663
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77451886"
---
### <a name="resource-manifest-file-names"></a><span data-ttu-id="a4629-101">Manifestdateinamen von Ressourcen</span><span class="sxs-lookup"><span data-stu-id="a4629-101">Resource manifest file names</span></span>

<span data-ttu-id="a4629-102">Ab .Net Core 3.0 hat sich der generierte Manifestdateiname von Ressourcen geändert.</span><span class="sxs-lookup"><span data-stu-id="a4629-102">Starting in .NET Core 3.0, the generated resource manifest file name has changed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a4629-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a4629-103">Version introduced</span></span>

<span data-ttu-id="a4629-104">3.0</span><span class="sxs-lookup"><span data-stu-id="a4629-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="a4629-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="a4629-105">Change description</span></span>

<span data-ttu-id="a4629-106">Wenn vor . NET Core 3.0 [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile)-Metadaten für eine Ressourcendatei ( *.resx*) in der MSBuild-Projektdatei festgelegt wurden, lautete der generierte Manifestname *Namespace.Classname.resources*.</span><span class="sxs-lookup"><span data-stu-id="a4629-106">Prior to .NET Core 3.0, when [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) metadata was set for a resource (*.resx*) file in the MSBuild project file, the generated manifest name was *Namespace.Classname.resources*.</span></span> <span data-ttu-id="a4629-107">Wenn [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) nicht festgelegt wurde, lautete der generierte Manifestname *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.</span><span class="sxs-lookup"><span data-stu-id="a4629-107">When [DependentUpon](/visualstudio/msbuild/common-msbuild-project-items#compile) was not set, the generated manifest name was *Namespace.Classname.FolderPathRelativeToRoot.Culture.resources*.</span></span>

<span data-ttu-id="a4629-108">Ab .NET Core 3.0 wird, wenn eine *RESX*-Datei mit einer gleichnamigen Quelldatei zusammengestellt wird, z. B. in Windows Forms-Anwendungen, der Manifestname der Ressource aus dem vollständigen Namen des ersten Typs in der Quelldatei generiert.</span><span class="sxs-lookup"><span data-stu-id="a4629-108">Starting in .NET Core 3.0, when a *.resx* file is colocated with a source file of the same name, for example, in Windows Forms apps, the resource manifest name is generated from the full name of the first type in the source file.</span></span> <span data-ttu-id="a4629-109">Wenn beispielsweise *Type.cs* mit *Type.resx* zusammengestellt wird, lautet der generierte Manifestname *Namespace.Classname.resources*.</span><span class="sxs-lookup"><span data-stu-id="a4629-109">For example, if *Type.cs* is colocated with *Type.resx*, the generated manifest name is *Namespace.Classname.resources*.</span></span> <span data-ttu-id="a4629-110">Wenn Sie jedoch eines der Attribute der `EmbeddedResource`-Eigenschaft in der *RESX*-Datei ändern, kann der generierte Manifestdateiname anders lauten:</span><span class="sxs-lookup"><span data-stu-id="a4629-110">However, if you modify any of the attributes on the `EmbeddedResource` property for the *.resx* file, the generated manifest file name may be different:</span></span>

- <span data-ttu-id="a4629-111">Wenn das `LogicalName`-Attribut der `EmbeddedResource`-Eigenschaft festgelegt ist, wird dieser Wert als Manifestdateiname der Ressource verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4629-111">If the `LogicalName` attribute on the `EmbeddedResource` property is set, that value is used as the resource manifest file name.</span></span>

  <span data-ttu-id="a4629-112">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="a4629-112">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" LogicalName="SomeName.resources" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" LogicalName="SomeName.resources" />
  ```

  <span data-ttu-id="a4629-113">**Generierter Manifestdateiname der Ressource**: *SomeName.resources* (unabhängig vom *RESX*-Dateinamen oder der Kultur oder anderen Metadaten).</span><span class="sxs-lookup"><span data-stu-id="a4629-113">**Generated resource manifest file name**: *SomeName.resources* (regardless of the *.resx* file name or culture or any other metadata).</span></span>

- <span data-ttu-id="a4629-114">Falls `LogicalName` nicht festgelegt ist, aber das `ManifestResourceName`-Attribut der `EmbeddedResource`-Eigenschaft festgelegt ist, wird sein Wert in Kombination mit der Dateierweiterung *.resources* als Manifestdateiname der Ressource verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4629-114">If `LogicalName` is not set, but the `ManifestResourceName` attribute on the `EmbeddedResource` property is set, its value, combined with the file extension *.resources*, is used as the resource manifest file name.</span></span>

  <span data-ttu-id="a4629-115">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="a4629-115">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" ManifestResourceName="SomeName" />
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" ManifestResourceName="SomeName.fr-FR" />
  ```

  <span data-ttu-id="a4629-116">**Generierter Manifestdateiname der Ressource**: *SomeName.resources* oder *SomeName.fr-FR.resources*.</span><span class="sxs-lookup"><span data-stu-id="a4629-116">**Generated resource manifest file name**: *SomeName.resources* or *SomeName.fr-FR.resources*.</span></span>

- <span data-ttu-id="a4629-117">Wenn die vorherigen Regeln nicht zutreffen und das `DependentUpon`-Attribut des `EmbeddedResource`-Elements auf eine Quelldatei festgelegt ist, wird der Typname der ersten Klasse in der Quelldatei im Manifestdateinamen der Ressource verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4629-117">If the previous rules don't apply, and the `DependentUpon` attribute on the `EmbeddedResource` element is set to a source file, the type name of the first class in the source file is used in the resource manifest file name.</span></span> <span data-ttu-id="a4629-118">Genauer gesagt lautet der generierte Dateiname *Namespace.Classname\[.Culture].resources*.</span><span class="sxs-lookup"><span data-stu-id="a4629-118">More specifically, the generated file name is *Namespace.Classname\[.Culture].resources*.</span></span>

  <span data-ttu-id="a4629-119">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="a4629-119">Examples:</span></span>

  ```xml
  <EmbeddedResource Include="X.resx" DependentUpon="MyTypes.cs">
  -or-
  <EmbeddedResource Include="X.fr-FR.resx" DependentUpon="MyTypes.cs">
  ```

  <span data-ttu-id="a4629-120">**Generierter Manifestdateiname der Ressource**: *Namespace.Classname.resources* oder *Namespace.Classname.fr-FR.resources* (wobei `Namespace.Classname` der Name der ersten Klasse in *MyTypes.cs* ist).</span><span class="sxs-lookup"><span data-stu-id="a4629-120">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>

- <span data-ttu-id="a4629-121">Wenn die vorherigen Regeln nicht zutreffen, ist `EmbeddedResourceUseDependentUponConvention` gleich `true` (Standard für .NET Core), und es eine mit einer *RESX*-Datei zusammengestellte Quelldatei gibt, die den gleichen Basisdateinamen hat, wird die *RESX*-Datei von der übereinstimmenden Quelldatei abhängig gemacht. Der generierte Name ist der gleiche wie in der vorherigen Regel.</span><span class="sxs-lookup"><span data-stu-id="a4629-121">If the previous rules don't apply, `EmbeddedResourceUseDependentUponConvention` is `true` (the default for .NET Core), and there's a source file colocated with a *.resx* file that has the same base file name, the *.resx* file is made dependent upon the matching source file, and the generated name is the same as in the previous rule.</span></span> <span data-ttu-id="a4629-122">Dies ist die Standardeinstellungsregel für .NET Core-Projekte.</span><span class="sxs-lookup"><span data-stu-id="a4629-122">This is the "default settings" rule for .NET Core projects.</span></span>
  
  <span data-ttu-id="a4629-123">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="a4629-123">Examples:</span></span>
  
  <span data-ttu-id="a4629-124">Die Dateien *MyTypes.cs* und *MyTypes.resx* oder *MyTypes.fr-FR.resx* befinden sich im gleichen Ordner.</span><span class="sxs-lookup"><span data-stu-id="a4629-124">Files *MyTypes.cs* and *MyTypes.resx* or *MyTypes.fr-FR.resx* exist in the same folder.</span></span>
  
  <span data-ttu-id="a4629-125">**Generierter Manifestdateiname der Ressource**: *Namespace.Classname.resources* oder *Namespace.Classname.fr-FR.resources* (wobei `Namespace.Classname` der Name der ersten Klasse in *MyTypes.cs* ist).</span><span class="sxs-lookup"><span data-stu-id="a4629-125">**Generated resource manifest file name**: *Namespace.Classname.resources* or *Namespace.Classname.fr-FR.resources* (where `Namespace.Classname` is the name of the first class in *MyTypes.cs*).</span></span>
    
- <span data-ttu-id="a4629-126">Wenn keine der vorherigen Regeln zutrifft, lautet der Name der generierten Manifestdatei der Ressource *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span><span class="sxs-lookup"><span data-stu-id="a4629-126">If none of the previous rules apply, the generated resource manifest file name is *RootNamespace.RelativePathWithDotsForSlashes.\[Culture.]resources*.</span></span> <span data-ttu-id="a4629-127">Der relative Pfad ist der Wert des `Link`-Attributs des `EmbeddedResource`-Elements, falls festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a4629-127">The relative path is the value of the `Link` attribute of the `EmbeddedResource` element if it's set.</span></span> <span data-ttu-id="a4629-128">Andernfalls ist der relative Pfad der Wert des `Identity`-Attributs des `EmbeddedResource`-Elements.</span><span class="sxs-lookup"><span data-stu-id="a4629-128">Otherwise, the relative path is the value of the `Identity` attribute of the `EmbeddedResource` element.</span></span> <span data-ttu-id="a4629-129">In Visual Studio ist dies der Pfad vom Projektstamm zur Datei im Projektmappen-Explorer.</span><span class="sxs-lookup"><span data-stu-id="a4629-129">In Visual Studio, this is the path from the project root to the file in Solution Explorer.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a4629-130">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="a4629-130">Recommended action</span></span>

<span data-ttu-id="a4629-131">Wenn Sie mit den generierten Manifestnamen unzufrieden sind, haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="a4629-131">If you're unsatisfied with the generated manifest names, you can:</span></span>

- <span data-ttu-id="a4629-132">Ändern Sie die Metadaten Ihrer Ressourcendatei gemäß einer der zuvor beschriebenen Benennungsregeln.</span><span class="sxs-lookup"><span data-stu-id="a4629-132">Modify your resource file metadata according to one of the previously described naming rules.</span></span>

- <span data-ttu-id="a4629-133">Legen Sie in Ihrer Projektdatei `EmbeddedResourceUseDependentUponConvention` auf `false` fest, um die neue Konvention vollständig abzulehnen:</span><span class="sxs-lookup"><span data-stu-id="a4629-133">Set `EmbeddedResourceUseDependentUponConvention` to `false` in your project file to opt out of the new convention entirely:</span></span>

   ```xml
   <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
   ```

   > [!NOTE]
   > <span data-ttu-id="a4629-134">Wenn die Attribute `LogicalName` oder `ManifestResourceName` vorhanden sind, werden ihre Werte weiterhin für den generierten Dateinamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a4629-134">If the `LogicalName` or `ManifestResourceName` attributes are present, their values will still be used for the generated file name.</span></span>

#### <a name="category"></a><span data-ttu-id="a4629-135">Kategorie</span><span class="sxs-lookup"><span data-stu-id="a4629-135">Category</span></span>

<span data-ttu-id="a4629-136">MSBuild</span><span class="sxs-lookup"><span data-stu-id="a4629-136">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a4629-137">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a4629-137">Affected APIs</span></span>

<span data-ttu-id="a4629-138">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="a4629-138">N/A</span></span>
