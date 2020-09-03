---
title: Verwaltung der C#-Sprachversion – Leitfaden für C#
description: Erfahren Sie mehr darüber, wie und aus welchen Gründen die C#-Sprachversion basierend auf Ihrem Projekt bestimmt wird. Erfahren Sie, wie Sie den Standardwert manuell überschreiben.
ms.custom: updateeachrelease
ms.date: 05/20/2020
ms.openlocfilehash: 24797c564890b034683d2989010bc694aabc423c
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811950"
---
# <a name="c-language-versioning"></a>Verwaltung der C#-Sprachversion

Der C#-Compiler bestimmt eine Standardsprachversion, die auf den Zielframeworks Ihres Projekts basiert. In Visual Studio gibt es keine Benutzeroberfläche zum Ändern dieses Werts, aber Sie können ihn ändern, indem Sie die *CSPROJ*-Datei bearbeiten. Mit der Auswahl des Standardwerts wird sichergestellt, dass Sie die neueste Sprachversion nutzen, die mit Ihrem Zielframework kompatibel ist. So profitieren Sie vom Zugriff auf die neuesten Sprachfeatures, die mit dem Zielframework Ihres Projekts kompatibel sind. Mit dem Standardwert wird außerdem sichergestellt, dass Sie keine Sprache verwenden, die Typen oder Runtimeverhalten erfordert, die nicht im Zielframework verfügbar sind. Wenn Sie eine Sprachversion auswählen, die neuer als die Standardeinstellung ist, können Kompilierzeit- und Runtimefehler auftreten, die schwer zu diagnostizieren sind.

Die in diesem Artikel aufgeführten Regeln gelten für den Compiler, der im Lieferumfang von Visual Studio 2019 oder dem .NET Core 3.0 SDK enthalten ist. Die C#-Compiler, die Teil der Visual Studio 2017-Installation oder von früheren .NET Core SDK-Versionen sind, sind standardmäßig auf C# 7.0 ausgerichtet.

C# 8.0 (und höher) wird nur in .NET Core 3.x und neueren Versionen unterstützt. Viele der neuesten Features erfordern Bibliotheks- und Runtimefeatures, die mit .NET Core 3.x eingeführt wurden:

- [Die Implementierung von Standardschnittstellen](../whats-new/csharp-8.md#default-interface-methods) erfordert neue Features in der .NET Core 3.0-CLR.
- Für [asynchrone Datenströme](../whats-new/csharp-8.md#asynchronous-streams) sind die neuen Typen <xref:System.IAsyncDisposable?displayProperty=nameWithType>, <xref:System.Collections.Generic.IAsyncEnumerable%601?displayProperty=nameWithType> und <xref:System.Collections.Generic.IAsyncEnumerator%601?displayProperty=nameWithType> erforderlich.
- Für [Indizes und Bereiche](../whats-new/csharp-8.md#indices-and-ranges) sind die neuen Typen <xref:System.Index?displayProperty=nameWithType> und <xref:System.Range?displayProperty=nameWithType> erforderlich.
- [Verweistypen, die NULL-Werte zulassen](../whats-new/csharp-8.md#nullable-reference-types), nutzen mehrere [Attribute](attributes/nullable-analysis.md), um bessere Warnungen bereitzustellen. Diese Attribute wurden in .NET Core 3.0 hinzugefügt. Andere Zielframeworks wurden nicht mit diesen Attributen versehen. Das bedeutet, dass Warnungen, die NULL-Werte zulassen, mögliche Probleme nicht exakt widerspiegeln.

## <a name="defaults"></a>der Arbeitszeittabelle

Der Compiler bestimmt basierend auf den folgenden Regeln eine Standardversion:

| Zielframework | Version | C#-Sprachversionsstandard |
|------------------|---------|-----------------------------|
| .NET Core        | 3.x     | C# 8.0                      |
| .NET Core        | 2.x     | C# 7.3                      |
| .NET-Standard    | 2.1     | C# 8.0                      |
| .NET-Standard    | 2.0     | C# 7.3                      |
| .NET-Standard    | 1.x     | C# 7.3                      |
| .NET Framework   | alle     | C# 7.3                      |

Wenn Ihr Projekt auf eine Vorschauframework abzielt, das eine entsprechende Vorschausprachversion besitzt, wird die Vorschausprachversion als Sprachversion verwendet. In dieser Vorschau können Sie die neuesten Features in beliebigen Umgebungen verwenden, ohne Auswirkungen auf Projekte für eine veröffentlichte .NET Core-Version zu haben.

> [!TIP]
> Wenn Sie wissen möchten, welche Sprachversion Sie derzeit verwenden, fügen Sie `#error version` (Groß-/Kleinschreibung beachten) in Ihren Code ein. Dadurch erzeugt der Compiler eine Diagnose (CS8304) mit einer Nachricht, die die verwendete Compilerversion und die aktuelle ausgewählte Sprachversion enthält.

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

Builds in allen Unterverzeichnissen des Verzeichnisses, das diese Datei enthält, verwenden die C#-Vorschauversion. Weitere Informationen finden Sie im Artikel zum [Anpassen Ihres Builds](/visualstudio/msbuild/customize-your-build).

## <a name="c-language-version-reference"></a>Referenz zur C#-Sprachversion

In der folgenden Tabelle sind alle aktuellen C#-Sprachversionen enthalten. Wenn Ihr Compiler älter ist, versteht er möglicherweise nicht alle Werte. Wenn Sie .NET Core 3.0 oder höher installieren, verfügen Sie über Zugriff auf alle aufgeführten Elemente.

[!INCLUDE [langversion-table](includes/langversion-table.md)]

> [!TIP]
> Öffnen Sie die [Developer-Eingabeaufforderung für Visual Studio](../../framework/tools/developer-command-prompt-for-vs.md), und führen Sie den folgenden Befehl aus, um die Liste der auf Ihrem Computer verfügbaren Sprachversionen anzuzeigen.
>
> ```CMD
> csc -langversion:?
> ```
>
> Wenn Sie die Kompilierungsoption [-langversion](compiler-options/langversion-compiler-option.md) wie folgt abfragen, wird etwa Folgendes ausgegeben:
>
> ```CMD
> Supported language versions:
> default
> 1
> 2
> 3
> 4
> 5
> 6
> 7.0
> 7.1
> 7.2
> 7.3
> 8.0 (default)
> latestmajor
> preview
> latest
> ```
