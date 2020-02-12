---
title: Verwaltung der C#-Sprachversion – Leitfaden für C#
description: Hier erfahren Sie, wie die C#-Sprachversion basierend auf Ihrem Projekt bestimmt wird, und Sie lernen die verschiedenen Werte kennen, die Sie manuell an die Sprachversion anpassen können.
ms.date: 07/10/2019
ms.openlocfilehash: 3c1035d983660ea0a945e4d4b7b72c69736c90cb
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980131"
---
# <a name="c-language-versioning"></a>Verwaltung der C#-Sprachversion

Der C#-Compiler bestimmt eine Standardsprachversion, die auf den Zielframeworks Ihres Projekts basiert. Der Grund dafür ist, dass die Sprache C# Features enthalten kann, die von Typen oder Laufzeitkomponenten abhängig sind, die nicht in allen .NET-Implementierungen verfügbar sind. Damit wird sichergestellt, dass Sie die Sprachversion mit der höchsten Kompatibilität erhalten, ganz gleich, für welches Ziel Sie Ihr Projekt erstellen.

Die in diesem Artikel aufgeführten Regeln gelten für den Compiler, der im Lieferumfang von Visual Studio 2019 oder dem .NET Core 3.0 SDK enthalten ist. Die C#-Compiler, die Teil der Visual Studio 2017-Installation oder von früheren .NET Core SDK-Versionen sind, sind standardmäßig auf C# 7.0 ausgerichtet. 

## <a name="defaults"></a>der Arbeitszeittabelle

Der Compiler bestimmt basierend auf den folgenden Regeln eine Standardversion:

|Zielframework|Version|C#-Sprachversionsstandard|
|----------------|-------|---------------------------|
|.NET Core|3.x|C# 8.0|
|.NET Core|2.x|C# 7.3|
|.NET-Standard|2.1|C# 8.0|
|.NET-Standard|2.0|C# 7.3|
|.NET-Standard|1.x|C# 7.3|
|.NET Framework|alle|C# 7.3|

## <a name="default-for-previews"></a>Standard für Vorschauversionen

Wenn Ihr Projekt auf eine Vorschauframework abzielt, das eine entsprechende Vorschausprachversion besitzt, wird die Vorschausprachversion als Sprachversion verwendet. Damit wird sichergestellt, dass Sie die neuesten Features verwenden können, die garantiert mit dieser Vorschauversion in jeder Umgebung funktionieren ohne Auswirkungen auf Ihre Projekte, die auf eine freigegebene .NET Core-Version abzielen.

## <a name="override-a-default"></a>Überschreiben eines Standardwerts

Wenn Sie Ihre C#-Version explizit angeben müssen, haben Sie verschiedene Möglichkeiten:

- Manuelles Bearbeiten der [Projektdatei](#edit-the-project-file)
- Festlegen der Sprachversion [für mehrere Projekte in einem Unterverzeichnis](#configure-multiple-projects)
- Konfigurieren der [Compileroption `-langversion`](compiler-options/langversion-compiler-option.md)

### <a name="edit-the-project-file"></a>Bearbeiten der Projektdatei

Sie können die Sprachversion in der Projektdatei festlegen. Wenn Sie beispielsweise expliziten Zugriff auf Previewfunktionen wünschen, fügen Sie ein Element wie folgt hinzu:

```xml
<PropertyGroup>
   <LangVersion>preview</LangVersion>
</PropertyGroup>
```

Der Wert `preview` verwendet die neueste verfügbare Vorschauversion der Sprache C#, die Ihr Compiler unterstützt.

### <a name="configure-multiple-projects"></a>Konfigurieren mehrerer Projekte

Sie können eine **Directory.Build.props**-Datei erstellen, die das Element `<LangVersion>` enthält, um mehrere Projekte zu konfigurieren. In der Regel führen Sie dies im Projektmappenverzeichnis durch. Fügen Sie Folgendes in eine **Directory.Build.props**-Datei in Ihrem Projektmappenverzeichnis ein:

```xml
<Project>
 <PropertyGroup>
   <LangVersion>preview</LangVersion>
 </PropertyGroup>
</Project>
```

Nun verwenden alle Unterverzeichnisse des Verzeichnisses, das diese Datei enthält, die C#-Vorschauversion. Weitere Informationen finden Sie im Artikel zum [Anpassen Ihres Builds](/visualstudio/msbuild/customize-your-build).

## <a name="c-language-version-reference"></a>Referenz zur C#-Sprachversion

In der folgenden Tabelle sind alle aktuellen C#-Sprachversionen enthalten. Wenn Ihr Compiler älter ist, versteht er möglicherweise nicht alle Werte. Sie haben Zugriff auf alle aufgeführten Elemente, wenn Sie .NET Core 3.0 installieren.

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
