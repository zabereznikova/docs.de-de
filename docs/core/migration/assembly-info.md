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
# <a name="map-assemblyinfo-attributes-to-properties"></a>Zuordnen von AssemblyInfo-Attributen zu Eigenschaften

[Assemblyattribute](../../standard/assembly/set-attributes.md) wurden in .NET Core 2.0 und früher üblicherweise in einer *AssemblyInfo*-Datei erfasst. Ab .NET Core 2.1 werden diese jedoch automatisch aus MSBuild-Eigenschaften generiert.

## <a name="properties-per-attribute"></a>Eigenschaften pro Attribut

Wie in der folgenden Tabelle gezeigt, ist für jedes Attribut eine zugehörige Eigenschaft vorhanden, die seinen Inhalt definiert, und eine weitere zum Deaktivieren seiner Generierung:

| Attribut                                                      | Eigenschaft               | Eigenschaft zum Deaktivieren                             |
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

Notizen:

- `AssemblyVersion` und `FileVersion` nehmen standardmäßig den Wert von `$(Version)` ohne Suffix an. Wenn `$(Version)` beispielsweise `1.2.3-beta.4` ist, wäre der Wert `1.2.3`.
- `InformationalVersion` hat standardmäßig den Wert von `$(Version)`.
- Wenn die Eigenschaft `$(SourceRevisionId)` vorhanden ist, wird sie an `InformationalVersion` angefügt. Sie können dieses Verhalten mithilfe von `IncludeSourceRevisionInInformationalVersion` deaktivieren.
- Die Eigenschaften `Copyright` und `Description` werden auch für NuGet-Metadaten verwendet.
- `Configuration` weist standardmäßig den Wert `Debug` auf und wird für alle MSBuild-Ziele freigegeben. Sie können die Eigenschaft über die Option `--configuration` in `dotnet`-Befehlen wie [dotnet pack](../tools/dotnet-pack.md) festlegen.

## <a name="generateassemblyinfo"></a>GenerateAssemblyInfo

Dies ist ein boolescher Wert, der die AssemblyInfo-Generierung aktiviert oder deaktiviert. Der Standardwert ist `true`.

## <a name="generatedassemblyinfofile"></a>GeneratedAssemblyInfoFile

Dies ist der relative oder absolute Pfad der generierten AssemblyInfo-Datei. Standardmäßig handelt es sich dabei um eine Datei mit dem Namensformat *[projektame].AssemblyInfo.[cs|vb]* im Verzeichnis `$(IntermediateOutputPath)` (*obj*).
