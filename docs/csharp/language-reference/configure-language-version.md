---
title: 'Leitfaden für C#: Auswählen der C#-Sprachversion'
description: Konfigurieren des Compilers zum Ausführen der Syntaxüberprüfung mithilfe einer spezifischen Compilerversion
ms.date: 02/28/2019
ms.openlocfilehash: 6d31a757171bd2eecdcc1fbd3da765dcb3fe45c0
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212026"
---
# <a name="select-the-c-language-version"></a>Auswählen der C#-Sprachversion

Der C#-Compiler bestimmt eine Standardsprachversion, basierend auf dem oder den Zielframeworks Ihres Projekts. Wenn Ihr Projekt auf eine Vorschauframework abzielt, das eine entsprechende Vorschausprachversion besitzt, wird die Vorschausprachversion als Sprachversion verwendet. Wenn Ihr Projekt nicht auf ein Vorschauframework abzielt, wird die höchste Nebenversion als Sprachversion verwendet.

Beispielsweise verwendet jedes Projekt, das während des Vorschauzeitraums für .NET Core 3.0 auf `netcoreapp3.0` oder `netstandard2.1` abzielt (beide in der Vorschauphase), die C# 8.0-Sprache (ebenfalls in der Vorschauphase). Projekte, die auf eine veröffentlichte Version abzielen, verwenden C# 7.3 (die neueste veröffentlichte Version). Dieses Verhalten bedeutet, dass jedes Projekt, das auf .NET Framework abzielt, die neueste Version verwendet (C# 7.3). 

Diese Funktion entkoppelt das Installieren neuer Versionen vom SDK und den Tools in Ihrer Entwicklungsumgebung von der Entscheidung, neue Sprachfeatures in einem Projekt zu verwenden. Sie können das neueste SDK und die neuesten Tools auf Ihrem Buildcomputer installieren. Jedes Projekt kann dazu konfiguriert werden, eine spezifische Version der Sprache für das Build zu verwenden. Das Standardverhalten bedeutet, dass alle Sprachfunktionen, die von neuen Typen oder neuem CLR-Verhalten abhängig sind, nur aktiviert sind, wenn das Projekt auf diese Frameworks abzielt.

Sie können das Standardverhalten überschreiben, indem Sie eine Sprachversion angeben. Es gibt verschiedene Möglichkeiten, die Sprachversion einzurichten:

- Verwenden einer [Visual Studio-Schnellaktion](#visual-studio-quick-action)
- Festlegen der Sprachversion in der [Visual Studio-Benutzeroberfläche](#set-the-language-version-in-visual-studio)
- Manuelles Bearbeiten der [**CSPROJ**-Datei](#edit-the-csproj-file)
- Festlegen der Sprachversion [für mehrere Projekte in einem Unterverzeichnis](#configure-multiple-projects)
- Konfigurieren der [Compileroption `-langversion`](#set-the-langversion-compiler-option)

## <a name="visual-studio-quick-action"></a>Visual Studio-Schnellaktion

Visual Studio unterstützt Sie beim Auswählen der erforderlichen Sprachversion. Wenn Sie ein Sprachfeature verwenden, das in der derzeit konfigurierten Version nicht verfügbar ist, zeigt Visual Studio eine mögliche Lösung zum Aktualisieren der Sprachversion für das Projekt an.

## <a name="set-the-language-version-in-visual-studio"></a>Festlegen der Sprachversion in Visual Studio

Sie können die Version in Visual Studio festlegen. Klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf den Projektknoten, und wählen Sie **Eigenschaften** aus. Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**. Wählen Sie in der Dropdownliste die Version aus. Die folgende Abbildung zeigt die „aktuellste“ Einstellung:

![Screenshot der erweiterten Buildeinstellungen, in denen Sie die Sprachversion festlegen können](./media/configure-language-version/advanced-build-settings.png)

> [!NOTE]
> Wenn Sie die Visual Studio-IDE verwenden, um Ihre CSPROJ-Dateien zu aktualisieren, werden separate Knoten für jede Buildkonfiguration von der IDE erstellt. In der Regel legen Sie den gleichen Wert in allen Buildkonfigurationen fest, dennoch müssen Sie ihn für jede Buildkonfiguration explizit festlegen oder beim Ändern dieser Einstellung „Alle Konfigurationen“ auswählen. Folgendes wird dann in Ihrer CSPROJ-Datei angezeigt:
>
>```xml
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
>  <LangVersion>latest</LangVersion>
></PropertyGroup>
>
> <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
>  <LangVersion>latest</LangVersion>
> </PropertyGroup>
> ```
>

## <a name="edit-the-csproj-file"></a>Bearbeiten der CSPROJ-Datei

Sie können die Sprachversion in der **CSPROJ**-Datei festlegen. Fügen Sie ein Element wie das Folgende ein:

```xml
<PropertyGroup>
   <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Der Wert `latest` verwendet die neueste Nebenversion der C#-Sprache. Gültige Werte sind:

|Wert|Bedeutung|
|------------|-------------|
|preview|Der Compiler akzeptiert jede gültige Sprachsyntax der letzten Vorschauversion.|
|latest|Der Compiler akzeptiert die Syntax der neuesten veröffentlichte Version des Compilers (einschließlich Nebenversionen).|
|latestMajor|Der Compiler akzeptiert die Syntax der neuesten veröffentlichte Hauptversion des Compilers.|
|8.0|Der Compiler akzeptiert nur Syntax, die in C# 8.0 oder niedriger enthalten ist.|
|7.3|Der Compiler akzeptiert nur Syntax, die in C# 7.3 oder früher enthalten ist.|
|7.2|Der Compiler akzeptiert nur Syntax, die in C# 7.2 oder früher enthalten ist.|
|7.1|Der Compiler akzeptiert nur Syntax, die in C# 7.1 oder früher enthalten ist.|
|7|Der Compiler akzeptiert nur Syntax, die in C# 7.0 oder früher enthalten ist.|
|6|Der Compiler akzeptiert nur Syntax, die in C# 6.0 oder früher enthalten ist.|
|5|Der Compiler akzeptiert nur Syntax, die in C# 5.0 oder früher enthalten ist.|
|4|Der Compiler akzeptiert nur Syntax, die in C# 4.0 oder früher enthalten ist.|
|3|Der Compiler akzeptiert nur Syntax, die in C# 3.0 oder früher enthalten ist.|
|ISO-2|Der Compiler akzeptiert nur Syntax, die in ISO/IEC 23270:2006 C# (2.0) enthalten ist. |
|ISO-1|Der Compiler akzeptiert nur Syntax, die in ISO/IEC 23270:2003 C# (1.0/1.2) enthalten ist. |

## <a name="configure-multiple-projects"></a>Konfigurieren mehrerer Projekte

Sie können eine **Directory.build.props**-Datei erstellen, die das Element `<LangVersion>` enthält, um mehrere Verzeichnisse zu konfigurieren. In der Regel führen Sie dies im Projektmappenverzeichnis durch. Fügen Sie Folgendes in eine **Directory.build.props**-Datei in Ihrem Projektmappenverzeichnis ein:

```xml
<Project>
 <PropertyGroup>
   <LangVersion>7.3</LangVersion>
 </PropertyGroup>
</Project>
```

Nun verwenden alle Unterverzeichnisse des Verzeichnisses, das diese Datei enthält, die Syntax der Version 7.3 von C#. Weitere Informationen finden Sie im Artikel zum [Anpassen Ihres Builds](/visualstudio/msbuild/customize-your-build).

## <a name="set-the-langversion-compiler-option"></a>Festlegen der Compileroption „langversion“

Sie können die Befehlszeilenoption `-langversion` verwenden. Weitere Informationen finden Sie im Artikel zur Compileroption [-langversion](../language-reference/compiler-options/langversion-compiler-option.md). Sie können eine Liste der gültigen Werte anzeigen, indem Sie `csc -langversion:?` eingeben.
