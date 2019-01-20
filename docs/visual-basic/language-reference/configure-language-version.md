---
title: Wählen Sie die Version der Visual Basic-Sprache
description: Der Compiler auf, um die Validierung Syntax mit einer bestimmten Compilerversion zu konfigurieren.
ms.date: 05/24/2018
ms.openlocfilehash: 3b6d8055dbf64f2a5c38f46b6d66794fc48a1cea
ms.sourcegitcommit: b56d59ad42140d277f2acbd003b74d655fdbc9f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2019
ms.locfileid: "54415103"
---
# <a name="select-the-visual-basic-language-version"></a>Wählen Sie die Version der Visual Basic-Sprache

Visual Basic-Compiler standardmäßig die neueste Version der Sprache, die freigegeben wurde. Sie können jedes Projekt mit einem neuen Punktrelease der Sprache kompilieren. Mit einer neueren Version der Sprache können Sie die neuesten Sprachfeatures in Ihrem Projekt verwenden. In anderen Szenarios müssen Sie möglicherweise überprüfen, dass ein Projekt ordnungsgemäß kompiliert wird, wenn Sie eine ältere Version der Sprache verwenden.

Diese Funktion entkoppelt das Installieren neuer Versionen vom SDK und den Tools in Ihrer Entwicklungsumgebung von der Entscheidung, neue Sprachfeatures in einem Projekt zu verwenden. Sie können das neueste SDK und die neuesten Tools auf Ihrem Buildcomputer installieren. Jedes Projekt kann dazu konfiguriert werden, eine spezifische Version der Sprache für das Build zu verwenden.

Es gibt drei Möglichkeiten, um die Sprachversion festgelegt:

- Manuelles Bearbeiten Ihre [ **vbproj** Datei](#edit-the-vbproj-file)
- Legen Sie die Sprachversion [für mehrere Projekte in einem Unterverzeichnis](#configure-multiple-projects)
- Konfigurieren der [ `-langversion` -Compileroption](#set-the-langversion-compiler-option)

## <a name="edit-the-vbproj-file"></a>Bearbeiten Sie die Vbproj-Datei

Sie können die Sprachversion festlegen, in Ihre **vbproj** Datei. Fügen Sie das folgende Element hinzu:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Der Wert `latest` verwendet die neueste Nebenversion der Visual Basic-Sprache. Gültige Werte sind:

|Wert|Bedeutung|
|------------|-------------|
|default|Der Compiler akzeptiert jede gültige Sprachsyntax der letzten Hauptversion, die unterstützen werden kann.|
|9|Der Compiler akzeptiert nur Syntax, die in Visual Basic 9.0 oder früher enthalten ist.|
|10|Der Compiler akzeptiert nur Syntax, die in Visual Basic 10.0 oder früher enthalten ist.|
|11|Der Compiler akzeptiert nur Syntax, die in Visual Basic-11.0 oder früher enthalten ist.|
|12|Der Compiler akzeptiert nur Syntax, die in Visual Basic-12.0 oder früher enthalten ist.|
|14|Der Compiler akzeptiert nur Syntax, die in Visual Basic-14.0 oder früher enthalten ist.|
|15|Der Compiler akzeptiert nur Syntax, die in Visual Basic-15.0 oder früher enthalten ist.|
|15.3|Der Compiler akzeptiert nur Syntax, die in Visual Basic 15.3 oder früher enthalten ist.|
|15.5|Der Compiler akzeptiert nur Syntax, die in Visual Basic 15.5 oder früher enthalten ist.|
|latest|Der Compiler akzeptiert alle gültige Sprachsyntax, die es unterstützen kann.|

Die Auflösung der speziellen Zeichenfolgen `default` und `latest` sind die Haupt- und Nebensprachversionen, die jeweils auf dem Buildcomputer installiert sind.

## <a name="configure-multiple-projects"></a>Konfigurieren mehrerer Projekte

Sie können eine **Directory.build.props**-Datei erstellen, die das Element `<LangVersion>` enthält, um mehrere Verzeichnisse zu konfigurieren. In der Regel führen Sie dies im Projektmappenverzeichnis durch. Fügen Sie Folgendes in eine **Directory.build.props**-Datei in Ihrem Projektmappenverzeichnis ein:

```xml
<Project>
 <PropertyGroup>
   <LangVersion>15.5</LangVersion>
 </PropertyGroup>
</Project>
```

Builds in jedes Unterverzeichnis des Verzeichnisses, enthält diese Datei werden jetzt Visual Basic-Version 15.5-Syntax verwenden. Weitere Informationen finden Sie im Artikel zum [Anpassen Ihres Builds](/visualstudio/msbuild/customize-your-build).

## <a name="set-the-langversion-compiler-option"></a>Festlegen der Compileroption „langversion“

Sie können die Befehlszeilenoption `-langversion` verwenden. Weitere Informationen finden Sie im Artikel zur Compileroption [-langversion](../reference/command-line-compiler/langversion.md). Sie können eine Liste der gültigen Werte anzeigen, indem Sie die Eingabe `vbc -langversion:?` .
