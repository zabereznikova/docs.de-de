---
title: Konfigurationsdateien für Code Analyse Regeln
description: Erfahren Sie mehr über die verschiedenen Konfigurationsdateien zum Konfigurieren von Code Analyse Regeln.
ms.date: 09/24/2020
ms.topic: conceptual
no-loc:
- EditorConfig
ms.openlocfilehash: cf9b8f4033e6774684b2b7e3b788ef3c157d95df
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96592105"
---
# <a name="configuration-files-for-code-analysis-rules"></a>Konfigurationsdateien für Code Analyse Regeln

Code Analyse Regeln verfügen über verschiedene [Konfigurationsoptionen](configuration-options.md). Diese Optionen werden als Schlüssel-Wert-Paare in einer der folgenden Analyse Konfigurationsdateien angegeben:

- [EditorConfig](#editorconfig) file: dateibasierte oder Ordner basierte Konfigurationsoptionen.
- [Globale analyzerconfig](#global-analyzerconfig) -Datei: Konfigurationsoptionen auf Projektebene.

## EditorConfig

[EditorConfig](/visualstudio/ide/create-portable-custom-editor-options) Dateien werden verwendet, um **Optionen bereitzustellen, die auf bestimmte Quelldateien oder Ordner angewendet** werden. Optionen werden Unterabschnitts Kopfzeilen abgelegt, um die entsprechenden Dateien und Ordner zu identifizieren. Fügen Sie einen Eintrag für jede Regel hinzu, die Sie konfigurieren möchten, und platzieren Sie ihn unter dem entsprechenden Datei Erweiterungs Abschnitt, z `[*.cs]` . b..

```ini
[*.cs]
<option_name> = <option_value>
```

Im obigen Beispiel `[*.cs]` ist ein editorconfig-Abschnitts Header, mit dem alle c#-Dateien mit `.cs` der Dateierweiterung innerhalb des aktuellen Ordners ausgewählt werden, einschließlich der Unterordner. Der nachfolgende Eintrag `<option_name> = <option_value>` ist eine Analyzer-Option, die auf alle c#-Dateien angewendet wird.

Sie können EditorConfig Datei Konventionen auf einen Ordner, ein Projekt oder ein gesamtes Repository anwenden, indem Sie die Datei im entsprechenden Verzeichnis platzieren. Diese Optionen werden bei der Ausführung der Analyse während der Buildzeit und beim Bearbeiten von Code in Visual Studio angewendet.

Wenn Sie über eine vorhandene *editorconfig* -Datei für Editor-Einstellungen verfügen, z. b. eine Einzugs Größe, oder wenn Sie nachfolgende Leerzeichen kürzen möchten, können Sie die Konfigurationsoptionen für die Code Analyse in derselben Datei platzieren.

> [!TIP]
> Visual Studio stellt eine *Editor config* -Element Vorlage bereit, die es einfach macht, eine dieser Dateien zu Ihrem Projekt hinzuzufügen. Weitere Informationen finden Sie unter [Hinzufügen einer EditorConfig Datei zu einem Projekt](/visualstudio/ide/create-portable-custom-editor-options#add-an-editorconfig-file-to-a-project).

### <a name="example"></a>Beispiel

Im folgenden finden Sie eine Beispiel EditorConfig Datei zum Konfigurieren von Optionen und des Regel schwere Grads:

```ini
# Remove the line below if you want to inherit .editorconfig settings from higher directories
root = true

# C# files
[*.cs]

#### Core EditorConfig Options ####

# Indentation and spacing
indent_size = 4
indent_style = space
tab_width = 4

#### .NET Coding Conventions ####

# this. and Me. preferences
dotnet_style_qualification_for_method = true:warning

#### Diagnostic configuration ####

# CA1000: Do not declare static members on generic types
dotnet_diagnostic.CA1000.severity = warning
```

## <a name="global-analyzerconfig"></a>Globale analyzerconfig

Beginnend mit dem .net 5,0 SDK (das in Visual Studio 2019, Version 16,8 und höheren Versionen unterstützt wird), können Sie auch Analyzer-Optionen mit globalen _analyzerconfig_ -Dateien konfigurieren. Diese Dateien werden verwendet, um Optionen bereitzustellen, **die für alle Quelldateien in einem Projekt gelten**, unabhängig von deren Dateinamen oder Dateipfaden.

Im Unterschied zu [EditorConfig](#editorconfig) Dateien können globale Konfigurationsdateien nicht verwendet werden, um Editor-Stileinstellungen für IDES zu konfigurieren, wie z. b. die Einzugs Größe oder das Kürzen von nachfolgenden Leerzeichen. Stattdessen sind Sie ausschließlich für die Angabe von Analyzer-Konfigurationsoptionen auf Projektebene vorgesehen.

### <a name="format"></a>Format

Im Unterschied EditorConfig zu Dateien, die über Abschnitts Header verfügen müssen, z `[*.cs]` . b., um die entsprechenden Dateien und Ordner zu identifizieren, haben globale analyzerconfig-Dateien keine Abschnitts Header. Stattdessen benötigen Sie einen Eintrag der obersten Ebene des Formulars `is_global = true` , um Sie von regulären Dateien zu unterscheiden EditorConfig . Dies gibt an, dass alle Optionen in der Datei auf das gesamte Projekt angewendet werden. Zum Beispiel:

```ini
is_global = true
<option_name> = <option_value>
```

### <a name="naming"></a>Benennung

Im Unterschied EditorConfig zu Dateien, die benannt werden müssen `.editorconfig` , benötigen globale Konfigurationsdateien keinen bestimmten Namen oder keine Erweiterung. Wenn Sie diese Dateien jedoch als benennen, `.globalconfig` werden Sie implizit auf alle c#-und Visual Basic Projekte innerhalb des aktuellen Ordners angewendet, einschließlich der Unterordner. Andernfalls müssen Sie das Element explizit der `GlobalAnalyzerConfigFiles` MSBuild-Projektdatei hinzufügen:

```xml
<ItemGroup>
  <GlobalAnalyzerConfigFiles Include="<path_to_global_analyzer_config>" />
</ItemGroup>
```

> [!NOTE]
> Der Eintrag der obersten Ebene `is_global = true` ist auch dann erforderlich, wenn die Datei den Namen hat `.globalconfig` .

### <a name="example"></a>Beispiel

Im folgenden finden Sie ein Beispiel für eine globale analyzerconfig-Datei zum Konfigurieren von Optionen und des Regel schwere Grads auf Projektebene:

```ini
# Top level entry required to mark this as a global AnalyzerConfig file
is_global = true

# NOTE: No section headers for configuration entries

#### .NET Coding Conventions ####

# this. and Me. preferences
dotnet_style_qualification_for_method = true:warning

#### Diagnostic configuration ####

# CA1000: Do not declare static members on generic types
dotnet_diagnostic.CA1000.severity = warning
```

## <a name="precedence"></a>Rangfolge

Sowohl EditorConfig Dateien als auch globale analyzerconfig-Dateien geben ein Schlüssel-Wert-Paar für jede Option an. Konflikte treten auf, wenn mehrere Einträge mit demselben Schlüssel, aber unterschiedlichen Werten vorhanden sind.

### <a name="general-options"></a>Allgemeine Optionen

Wenn Konflikte zwischen Optionen auftreten, werden die folgenden Rang Folge Regeln verwendet, um die Konflikte aufzulösen:

- In Konflikt stehende Einträge in derselben Konfigurationsdatei: der Eintrag, der später in der Datei angezeigt wird, gewinnt. Dies gilt für widersprüchliche Einträge in einer einzelnen EditorConfig Datei und auch innerhalb einer einzelnen globalen analyzerconfig-Datei.

- In Konflikt stehende Einträge in zwei EditorConfig Dateien: der Eintrag in der Datei, der EditorConfig tiefer im Dateisystem ist und daher über einen längeren Dateipfad verfügt, gewinnt.

- In Konflikt stehende Einträge in zwei globalen analyzerconfig-Dateien: eine Compilerwarnung wird gemeldet, und beide Einträge werden ignoriert.

- In Konflikt stehende Einträge in einer EditorConfig Datei und eine globale analyzerconfig-Datei: der Eintrag in der EditorConfig Datei gewinnt.

### <a name="severity-options"></a>Optionen für Schweregrad

Die vorherigen [allgemeinen Rang Folge Regeln](#general-options) gelten für alle Optionen, die in den Konfigurationsdateien angegeben sind. Für Optionen zum [Konfigurieren des schwere](configuration-options.md#severity-level) Grads gelten die folgenden zusätzlichen Rang Folge Regeln:

- Die in der Befehlszeile als Compileroptionen (oder) angegebenen Schweregrad Optionen über `/nowarn` `/warnaserror` schreiben immer die in und globalen analyzerconfig-Dateien angegebenen Optionen für den [Schweregrad](configuration-options.md#severity-level) EditorConfig .

- Schweregrad Optionen können auch mit einer [RuleSet](/visualstudio/code-quality/using-rule-sets-to-group-code-analysis-rules) -Datei angegeben werden. RuleSets-Dateien sind jedoch veraltet und werden von EditorConfig und globalen analyzerconfig-Dateien entfernt. Es wird empfohlen, [RuleSet-Dateien in eine entsprechende EditorConfig Datei zu konvertieren](/visualstudio/code-quality/use-roslyn-analyzers#convert-an-existing-ruleset-file-to-editorconfig-file). Die Rangfolge für in Konflikt stehende Schweregrade von einer RuleSet-Datei und EditorConfig oder von globalen analyzerconfig-Dateien ist nicht _definiert_.

- Informationen zu Rang folgen Regeln für Verwandte Schweregrad Optionen mit unterschiedlichen Schlüsseln, z. b. wenn verschiedene Schweregrade für eine einzelne Regel angegeben werden, und für die Kategorie, zu der die Regel fällt, finden Sie unter [Konfigurationsoptionen für die Code Analyse](configuration-options.md#precedence).

## <a name="see-also"></a>Siehe auch

- [EditorConfig vs Global analyzerconfig-Entwurfsproblem](https://github.com/dotnet/roslyn/issues/47707)
