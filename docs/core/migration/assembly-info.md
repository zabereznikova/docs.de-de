---
title: AssemblyInfo-Eigenschaften
description: Hier erfahren Sie mehr über Assemblyattribute und den entsprechenden MSBuild-Eigenschaften in .NET Core 2.1 und höher.
ms.topic: reference
ms.date: 01/08/2021
ms.openlocfilehash: a2c431b3fe3da428f21582624ca5f357887e2815
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "98192873"
---
# <a name="map-assemblyinfo-attributes-to-properties"></a><span data-ttu-id="160b9-103">Zuordnen von AssemblyInfo-Attributen zu Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="160b9-103">Map AssemblyInfo attributes to properties</span></span>

<span data-ttu-id="160b9-104">[Assemblyattribute](../../standard/assembly/set-attributes.md) wurden in .NET Core 2.0 und früher üblicherweise in einer *AssemblyInfo*-Datei erfasst. Ab .NET Core 2.1 werden diese jedoch automatisch aus MSBuild-Eigenschaften generiert.</span><span class="sxs-lookup"><span data-stu-id="160b9-104">[Assembly attributes](../../standard/assembly/set-attributes.md) that were typically present in an *AssemblyInfo* file in .NET Core 2.0 and earlier versions are automatically generated from MSBuild properties, starting in .NET Core 2.1.</span></span>

## <a name="properties-per-attribute"></a><span data-ttu-id="160b9-105">Eigenschaften pro Attribut</span><span class="sxs-lookup"><span data-stu-id="160b9-105">Properties per attribute</span></span>

<span data-ttu-id="160b9-106">Wie in der folgenden Tabelle gezeigt, ist für jedes Attribut eine zugehörige Eigenschaft vorhanden, die seinen Inhalt definiert, und eine weitere zum Deaktivieren seiner Generierung:</span><span class="sxs-lookup"><span data-stu-id="160b9-106">As shown in the following table, each attribute has a corresponding property that controls its content and another that disables its generation:</span></span>

| <span data-ttu-id="160b9-107">Attribut</span><span class="sxs-lookup"><span data-stu-id="160b9-107">Attribute</span></span>                                                      | <span data-ttu-id="160b9-108">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="160b9-108">Property</span></span>               | <span data-ttu-id="160b9-109">Eigenschaft zum Deaktivieren</span><span class="sxs-lookup"><span data-stu-id="160b9-109">Property to disable</span></span>                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

<span data-ttu-id="160b9-110">Notizen:</span><span class="sxs-lookup"><span data-stu-id="160b9-110">Notes:</span></span>

- <span data-ttu-id="160b9-111">`AssemblyVersion` und `FileVersion` nehmen standardmäßig den Wert von `$(Version)` ohne Suffix an.</span><span class="sxs-lookup"><span data-stu-id="160b9-111">`AssemblyVersion` and `FileVersion` default to the value of `$(Version)` without the suffix.</span></span> <span data-ttu-id="160b9-112">Wenn `$(Version)` beispielsweise `1.2.3-beta.4` ist, wäre der Wert `1.2.3`.</span><span class="sxs-lookup"><span data-stu-id="160b9-112">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
- <span data-ttu-id="160b9-113">`InformationalVersion` hat standardmäßig den Wert von `$(Version)`.</span><span class="sxs-lookup"><span data-stu-id="160b9-113">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
- <span data-ttu-id="160b9-114">Wenn die Eigenschaft `$(SourceRevisionId)` vorhanden ist, wird sie an `InformationalVersion` angefügt.</span><span class="sxs-lookup"><span data-stu-id="160b9-114">If the `$(SourceRevisionId)` property is present, it's appended to `InformationalVersion`.</span></span> <span data-ttu-id="160b9-115">Sie können dieses Verhalten mithilfe von `IncludeSourceRevisionInInformationalVersion` deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="160b9-115">You can disable this behavior using `IncludeSourceRevisionInInformationalVersion`.</span></span>
- <span data-ttu-id="160b9-116">Die Eigenschaften `Copyright` und `Description` werden auch für NuGet-Metadaten verwendet.</span><span class="sxs-lookup"><span data-stu-id="160b9-116">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
- <span data-ttu-id="160b9-117">`Configuration` weist standardmäßig den Wert `Debug` auf und wird für alle MSBuild-Ziele freigegeben.</span><span class="sxs-lookup"><span data-stu-id="160b9-117">`Configuration`, which defaults to `Debug`, is shared with all MSBuild targets.</span></span> <span data-ttu-id="160b9-118">Sie können die Eigenschaft über die Option `--configuration` in `dotnet`-Befehlen wie [dotnet pack](../tools/dotnet-pack.md) festlegen.</span><span class="sxs-lookup"><span data-stu-id="160b9-118">You can set it via the `--configuration` option of `dotnet` commands, for example, [dotnet pack](../tools/dotnet-pack.md).</span></span>

## <a name="generateassemblyinfo"></a><span data-ttu-id="160b9-119">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="160b9-119">GenerateAssemblyInfo</span></span>

<span data-ttu-id="160b9-120">Dies ist ein boolescher Wert, der die AssemblyInfo-Generierung aktiviert oder deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="160b9-120">A Boolean that enables or disables the AssemblyInfo generation.</span></span> <span data-ttu-id="160b9-121">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="160b9-121">The default value is `true`.</span></span>

## <a name="generatedassemblyinfofile"></a><span data-ttu-id="160b9-122">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="160b9-122">GeneratedAssemblyInfoFile</span></span>

<span data-ttu-id="160b9-123">Dies ist der relative oder absolute Pfad der generierten AssemblyInfo-Datei.</span><span class="sxs-lookup"><span data-stu-id="160b9-123">The relative or absolute path of the generated assembly info file.</span></span> <span data-ttu-id="160b9-124">Standardmäßig handelt es sich dabei um eine Datei mit dem Namensformat *[projektame].AssemblyInfo.[cs|vb]* im Verzeichnis `$(IntermediateOutputPath)` (*obj*).</span><span class="sxs-lookup"><span data-stu-id="160b9-124">Defaults to a file named *[project-name].AssemblyInfo.[cs|vb]* in the `$(IntermediateOutputPath)` (*obj*) directory.</span></span>
