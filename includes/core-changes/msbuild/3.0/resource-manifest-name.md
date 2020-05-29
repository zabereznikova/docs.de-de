---
ms.openlocfilehash: f24a29a00a1bff34a452c43716d76bf72ef277b5
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206213"
---
### <a name="resource-manifest-file-name-change"></a><span data-ttu-id="1c3a6-101">Änderung des Manifestdateinamens der Ressource</span><span class="sxs-lookup"><span data-stu-id="1c3a6-101">Resource manifest file name change</span></span>

<span data-ttu-id="1c3a6-102">Ab .NET Core 3.0 generiert MSBuild im Standardfall einen anderen Manifestdateinamen für Ressourcendateien.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-102">Starting in .NET Core 3.0, in the default case, MSBuild generates a different manifest file name for resource files.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1c3a6-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="1c3a6-103">Version introduced</span></span>

<span data-ttu-id="1c3a6-104">3.0</span><span class="sxs-lookup"><span data-stu-id="1c3a6-104">3.0</span></span>

#### <a name="change-description"></a><span data-ttu-id="1c3a6-105">Änderungsbeschreibung</span><span class="sxs-lookup"><span data-stu-id="1c3a6-105">Change description</span></span>

<span data-ttu-id="1c3a6-106">Vor .NET Core 3.0 hat MSBuild im Muster `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources` einen Manifestdateinamen generiert, wenn für ein `EmbeddedResource`-Element in der Projektdatei nicht `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-106">Prior to .NET Core 3.0, if no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata was specified for an `EmbeddedResource` item in the project file, MSBuild generated a manifest file name in the pattern `<RootNamespace>.<ResourceFilePathFromProjectRoot>.resources`.</span></span> <span data-ttu-id="1c3a6-107">Wenn `RootNamespace` nicht in der Projektdatei definiert ist, wird standardmäßig der Projektname verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-107">If `RootNamespace` is not defined in the project file, it defaults to the project name.</span></span> <span data-ttu-id="1c3a6-108">Beispielsweise lautete der Name des generierten Manifests für eine Ressourcendatei mit dem Namen *Form1.resx* im Stammverzeichnis des Projekts *MyProject.Form1.resources*.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-108">For example, the generated manifest name for a resource file named *Form1.resx* in the root project directory was *MyProject.Form1.resources*.</span></span>

<span data-ttu-id="1c3a6-109">Ab .NET Core 3.0 verwendet MSBuild Typinformationen aus der Quelldatei, wenn eine Ressourcendatei mit einer Quelldatei desselben Namens (z. B. *Form1.resx* und *Form1.cs*) angeordnet wird, um den Manifestdateinamen im Muster `<Namespace>.<ClassName>.resources` zu generieren.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-109">Starting in .NET Core 3.0, if a resource file is colocated with a source file of the same name (for example, *Form1.resx* and *Form1.cs*), MSBuild uses type information from the source file to generate the manifest file name in the pattern `<Namespace>.<ClassName>.resources`.</span></span> <span data-ttu-id="1c3a6-110">Der Namespace- und Klassenname werden aus dem ersten Typ in der angeordneten Quelldatei extrahiert.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-110">The namespace and class name are extracted from the first type in the colocated source file.</span></span> <span data-ttu-id="1c3a6-111">Beispielsweise lautet der generierte Manifestname für eine Ressourcendatei mit dem Namen *Form1.resx*, die mit einer Quelldatei mit dem Namen *Form1.cs* angeordnet wird, *MyNamespace.Form1.resources*.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-111">For example, the generated manifest name for a resource file named *Form1.resx* that's colocated with a source file named *Form1.cs* is *MyNamespace.Form1.resources*.</span></span> <span data-ttu-id="1c3a6-112">Wichtig ist zu beachten, dass der erste Teil des Dateinamens sich von früheren Versionen von .NET Core unterscheidet (*MyNamespace* anstelle von *MyProject*).</span><span class="sxs-lookup"><span data-stu-id="1c3a6-112">The key thing to note is that the first part of the file name is different to prior versions of .NET Core (*MyNamespace* instead of *MyProject*).</span></span>

> [!NOTE]
> <span data-ttu-id="1c3a6-113">Wenn `LogicalName`-, `ManifestResourceName`- oder `DependentUpon`-Metadaten für ein `EmbeddedResource`-Element in der Projektdatei angegeben sind, wirkt sich diese Änderung nicht auf diese Ressourcendatei aus.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-113">If you have `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata specified on an `EmbeddedResource` item in the project file, then this change does not affect that resource file.</span></span>

<span data-ttu-id="1c3a6-114">Dieser Breaking Change wurde mit dem Hinzufügen der `EmbeddedResourceUseDependentUponConvention`-Eigenschaft zu .NET Core-Projekten eingeführt.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-114">This breaking change was introduced with the addition of the `EmbeddedResourceUseDependentUponConvention` property to .NET Core projects.</span></span> <span data-ttu-id="1c3a6-115">Standardmäßig werden Ressourcendateien nicht explizit in einer .NET Core-Projektdatei aufgelistet, sodass Ihnen keine `DependentUpon`-Metadaten zur Verfügung stehen, um anzugeben, wie die generierte *RESOURCES*-Datei benannt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-115">By default, resource files aren't explicitly listed in a .NET Core project file, so they have no `DependentUpon` metadata to specify how to name the generated *.resources* file.</span></span> <span data-ttu-id="1c3a6-116">Wenn `EmbeddedResourceUseDependentUponConvention` dem Standard entsprechend auf `true` festgelegt ist, sucht MSBuild nach einer angeordneten Quelldatei und extrahiert einen Namespace- und Klassennamen aus dieser Datei.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-116">When `EmbeddedResourceUseDependentUponConvention` is set to `true`, which is the default, MSBuild looks for a colocated source file and extracts a namespace and class name from that file.</span></span> <span data-ttu-id="1c3a6-117">Wenn Sie `EmbeddedResourceUseDependentUponConvention` auf `false` festlegen, generiert MSBuild den Namen des Manifests gemäß dem vorherigen Verhalten, wobei `RootNamespace` und der relative Dateipfad kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-117">If you set `EmbeddedResourceUseDependentUponConvention` to `false`, MSBuild generates the manifest name according to the previous behavior, which combines `RootNamespace` and the relative file path.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1c3a6-118">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="1c3a6-118">Recommended action</span></span>

<span data-ttu-id="1c3a6-119">In den meisten Fällen ist keine Aktion seitens des Entwicklers erforderlich, und Ihre App sollte weiterhin funktionieren.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-119">In most cases, no action is required on the part of the developer, and your app should continue to work.</span></span> <span data-ttu-id="1c3a6-120">Wenn diese Änderung jedoch Ihre App beeinträchtigt, haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="1c3a6-120">However, if this change breaks your app, you can either:</span></span>

- <span data-ttu-id="1c3a6-121">Ändern Sie den Code so, dass er den neuen Manifestnamen erwartet.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-121">Change your code to expect the new manifest name.</span></span>

- <span data-ttu-id="1c3a6-122">Um die neue Namenskonvention zu umgehen, legen Sie in Ihrer Projektdatei `EmbeddedResourceUseDependentUponConvention` auf `false` fest.</span><span class="sxs-lookup"><span data-stu-id="1c3a6-122">Opt out of the new naming convention by setting `EmbeddedResourceUseDependentUponConvention` to `false` in your project file.</span></span>

  ```xml
  <PropertyGroup>
    <EmbeddedResourceUseDependentUponConvention>false</EmbeddedResourceUseDependentUponConvention>
  </PropertyGroup>
  ```

#### <a name="category"></a><span data-ttu-id="1c3a6-123">Kategorie</span><span class="sxs-lookup"><span data-stu-id="1c3a6-123">Category</span></span>

<span data-ttu-id="1c3a6-124">MSBuild</span><span class="sxs-lookup"><span data-stu-id="1c3a6-124">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1c3a6-125">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="1c3a6-125">Affected APIs</span></span>

<span data-ttu-id="1c3a6-126">Nicht zutreffend</span><span class="sxs-lookup"><span data-stu-id="1c3a6-126">N/A</span></span>
