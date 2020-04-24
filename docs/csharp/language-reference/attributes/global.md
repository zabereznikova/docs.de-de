---
title: 'Reservierte C#-Attribute: Globale Attribute'
ms.date: 04/09/2020
description: Attribute stellen dem Compiler Metadaten bereit, damit dieser die Semantik Ihres Programms besser versteht.
ms.openlocfilehash: f855f32cd7349da34ffbd20fededdf42c3023938
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389805"
---
# <a name="reserved-attributes-assembly-level-attributes"></a>Reservierte Attribute: Attribute auf Assemblyebene

Die meisten Attribute werden auf spezifische Sprachelemente wie Klassen oder Methoden angewendet. Einige Attribute sind jedoch global – sie gelten für eine gesamte Assembly oder ein Modul. Zum Beispiel kann das <xref:System.Reflection.AssemblyVersionAttribute>-Attribut zum Einbetten von Versionsinformationen in eine Assembly verwendet werden. Diese sieht wie folgt aus:

```csharp
[assembly: AssemblyVersion("1.0.0.0")]
```

Globale Attribute werden im Quellcode nach allen `using`-Direktiven der obersten Ebene und vor Typ-, Modul- oder Namespacedeklarationen angezeigt. Globale Attribute können in mehreren Quelldateien auftreten, jedoch müssen die Dateien in einem einzigen Kompilierungsdurchlauf kompiliert werden. Visual Studio fügt der Datei „AssemblyInfo.cs“ in .NET Framework-Projekten globale Attribute hinzu. Diese Attribute werden nicht zu .NET Core-Projekten hinzugefügt.

Assemblyattribute sind Werte, die Informationen zu einer Assembly bereitstellen. Sie werden in die folgenden Kategorien eingeteilt:

- Attribute für Assemblyidentitäten
- Informationsattribute
- Attribute für Assemblymanifeste.

## <a name="assembly-identity-attributes"></a>Attribute für Assemblyidentitäten

Drei Attribute bestimmen mit einem starken Namen (falls zutreffend) die Identität einer Assembly: „name“, „version“ und „culture“. Diese Attribute bilden den vollständigen Namen der Assembly und sind erforderlich, wenn im Code auf sie verwiesen wird. Mit Attributen können die Version und Kultur einer Assembly festgelegt werden. Allerdings wird der name-Wert bei Erstellung der Assembly vom Compiler, der Visual Studio-IDE im [Dialogfeld „Assemblyinformationen“](/visualstudio/ide/reference/assembly-information-dialog-box) oder dem Assemblylinker (Al.exe) festgelegt. Der Assemblyname basiert auf dem Assemblymanifest. Das Attribut <xref:System.Reflection.AssemblyFlagsAttribute> gibt an, ob mehrere Kopien der Assembly parallel bestehen können.

In der folgenden Tabelle werden die Identitätsattribute aufgeführt.

|Attribut|Zweck|
|---------------|-------------|
|<xref:System.Reflection.AssemblyVersionAttribute>|Gibt die Version einer Assembly an|
|<xref:System.Reflection.AssemblyCultureAttribute>|Gibt an, welche Kultur die Assembly unterstützt.|
|<xref:System.Reflection.AssemblyFlagsAttribute>|Gibt an, ob eine Assembly die parallele Ausführung auf demselben Computer, im selben Prozess oder in derselben Anwendungsdomäne unterstützt|

## <a name="informational-attributes"></a>Informationsattribute

Sie verwenden Informationsattribute, um zusätzliche Unternehmens- oder Produktinformationen für eine Assembly bereitzustellen. Die folgende Tabelle zeigt die Informationsattribute, die im Namespace <xref:System.Reflection?displayProperty=nameWithType> definiert werden.

|Attribut|Zweck|
|---------------|-------------|
|<xref:System.Reflection.AssemblyProductAttribute>|Gibt einen Produktnamen für ein Assemblymanifest an.|
|<xref:System.Reflection.AssemblyTrademarkAttribute>|Gibt eine Marke für ein Assemblymanifest an.|
|<xref:System.Reflection.AssemblyInformationalVersionAttribute>|Gibt Versionsinformationen für ein Assemblymanifest an.|
|<xref:System.Reflection.AssemblyCompanyAttribute>|Gibt einen Unternehmensnamen für ein Assemblymanifest an.|
|<xref:System.Reflection.AssemblyCopyrightAttribute>|Definiert ein benutzerdefiniertes Attribut, das ein Copyright für ein Assemblymanifest angibt|
|<xref:System.Reflection.AssemblyFileVersionAttribute>|Legt eine bestimmte Versionsnummer für die Win32-Dateiversionsressource fest.|
|<xref:System.CLSCompliantAttribute>|Gibt an, ob die Assembly mit der Common Language Specification (CLS) kompatibel ist|

## <a name="assembly-manifest-attributes"></a>Attribute für Assemblymanifeste.

Sie können Attribute für Assemblymanifeste verwenden, um Informationen im Assemblymanifest bereitzustellen. Dies schließt Attribute für Titel, Beschreibung, Standardalias und Konfiguration ein. Die folgende Tabelle zeigt die Attribute für Assemblymanifeste, die im Namespace <xref:System.Reflection?displayProperty=nameWithType> definiert werden.

|Attribut|Zweck|
|---------------|-------------|
|<xref:System.Reflection.AssemblyTitleAttribute>|Gibt einen Assemblytitel für ein Assemblymanifest an.|
|<xref:System.Reflection.AssemblyDescriptionAttribute>|Gibt eine Assemblybeschreibung für ein Assemblymanifest an.|
|<xref:System.Reflection.AssemblyConfigurationAttribute>|Gibt eine Assemblykonfiguration (z. B. „Einzelhandel“ oder „Debug“) für ein Assemblymanifest an.|
|<xref:System.Reflection.AssemblyDefaultAliasAttribute>|Definiert einen benutzerfreundlichen Standardalias für ein Assemblymanifest|
