---
title: Neues in C# 7.1
description: Eine Übersicht der neuen Features in C# 7.1
ms.date: 08/16/2017
ms.openlocfilehash: 00baec45d7582d3ac12c7b0865241f5cd8159246
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="whats-new-in-c-71"></a>Neues in C# 7.1

C# 7.1 ist die erste Punktversion der C#-Sprache. Das bedeutet schnellere Releaserhythmen für die Sprache. Sie können die neuen Features früher benutzen, im Idealfall sobald ein neues Feature bereit ist. Mit C# 7.1 wird die Fähigkeit hinzugefügt, den Compiler so zu konfigurieren, dass er einer bestimmten Version der Sprache entspricht. Damit können Sie die Entscheidung, Tools upzugraden, von der Entscheidung unterscheiden, Upgrades für Sprachversionen durchzuführen.

Mit C# 7.1 wird ein Konfigurationselement zum [Auswählen der Sprachversion](#language-version-selection), drei neue Sprachfeatures und neues Compilerverhalten hinzugefügt.

Die neuen Sprachfeatures in diesem Release umfassen:

* Die [`async``Main`-Methode](#async-main)
  - Der Einstiegspunkt für eine Anwendung kann über den Modifizierer `async` verfügen.
* [`default`Literale Ausdrücke](#default-literal-expressions)
  - Sie können literale Standardausdrücke in Standardwertausdrücken verwenden, wenn der Zieltyp abgeleitet werden kann.
* [Abgeleitete Tupelelementnamen](#inferred-tuple-element-names)
  - Die Namen von Tupelelementen können in den meisten Fällen von der Initialisierung eines Tupels abgeleitet werden.

Außerdem verfügt der Compiler über die zwei Optionen `/refout` und `/refonly`, mit denen die [Generierung der Referenzassembly](#reference-assembly-generation) gesteuert wird.

## <a name="language-version-selection"></a>Auswählen der Sprachversion

Der C#-Compiler unterstützt C# 7.1 ab Visual Studio 2017 Version 15.3 bzw. .NET Core SDK 2.0. Allerdings sind die Features von C# 7.1 standardmäßig deaktiviert. Sie müssen die Einstellung der Sprachversion Ihres Projekts ändern, um diese Features zu aktivieren.

Klicken Sie in Visual Studio mit der rechten Maustaste auf den Projektknoten im Projektmappen-Explorer, und klicken Sie auf **Eigenschaften**. Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**. Wählen Sie, wie in der folgenden Abbildung gezeigt wird, in der Dropdownliste **C# latest minor version (latest)** (Neueste C#-Nebenversion (latest)) oder die bestimmte Version **C# 7.1** aus. Der Wert `latest` bedeutet, dass Sie die neueste Nebenversion auf dem aktuellen Computer verwenden. `C# 7.1` bedeutet, dass Sie C# 7.1 verwenden, auch nachdem neuere Nebenversionen veröffentlicht wurden.

![Festlegen der Sprachversion](./media/csharp-7-1/advanced-build-settings.png)

Alternativ können Sie die CSPROJ-Datei bearbeiten und die folgenden Zeilen hinzufügen oder bearbeiten.

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> Wenn Sie die Visual Studio-IDE verwenden, um Ihre CSPROJ-Dateien zu aktualisieren, werden separate Knoten für jede Buildkonfiguration von der IDE erstellt. In der Regel legen Sie den gleichen Wert in allen Buildkonfigurationen fest, dennoch müssen Sie ihn für jede Buildkonfiguration explizit festlegen oder beim Ändern dieser Einstellung „Alle Konfigurationen“ auswählen. Folgendes wird dann in Ihrer CSPROJ-Datei angezeigt:

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Folgende Einstellungen sind für das `LangVersion`-Element gültig:

* `ISO-1`
* `ISO-2`
* `3`
* `4`
* `5`
* `6`
* `7`
* `7.1`
* `default`
* `latest`

Die Auflösung der speziellen Zeichenfolgen `default` und `latest` sind die Haupt- und Nebensprachversionen, die jeweils auf dem Buildcomputer installiert sind.

Mit dieser Einstellung wird das Installieren neuer Versionen des SDK und der Tools in Ihrer Entwicklungsumgebung vom Auswählen neuer Sprachfeatures für ein Projekt entkoppelt. Sie können das neueste SDK und die neuesten Tools auf Ihrem Buildcomputer installieren. Jedes Projekt kann dazu konfiguriert werden, eine spezifische Version der Sprache für das Build zu verwenden.

## <a name="async-main"></a>Async Main

Mithilfe einer *async main*-Methode können Sie `await` in Ihrer `Main`-Methode verwenden.
Vorher hätten Sie das Folgende schreiben müssen:

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

Nun können Sie das Folgende schreiben:

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

Wenn Ihr Programm keinen Exitcode zurückgibt, können Sie eine `Main`-Methode deklarieren, die einen <xref:System.Threading.Tasks.Task> zurückgibt:

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

Ausführliche Informationen finden Sie unter [Async Main](../programming-guide/main-and-command-args/index.md) im Programmierhandbuch.

## <a name="default-literal-expressions"></a>Literale Standardausdrücke

Literale Standardausdrücke sind eine Erweiterung von Ausdrücken mit Standardwert.
Diese Ausdrücke initialisieren eine Variable auf dem Standardwert. Dort, wo Sie vorher das Folgende geschrieben haben:

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

Können Sie nun den Typ weglassen, der auf der rechten Seite der Initialisierung steht.

```csharp
Func<string, bool> whereClause = default;
```

Weitere Informationen zu dieser Erweiterung finden Sie unter [default value expressions (Standardwertausdrücke)](../programming-guide/statements-expressions-operators/default-value-expressions.md) im C#-Programmierhandbuch.

Diese Erweiterung ändert auch einige Regeln der Analyse für das [Schlüsselwort „default“](../language-reference/keywords/default.md).

## <a name="inferred-tuple-element-names"></a>Abgeleitete Tupelelementnamen

Dieses Feature ist eine kleine Erweiterung des Tupelfeatures, das in C# 7.0 eingeführt wurde. Wenn Sie einen Tupel initialisieren, sind die Variablen, die für die rechte Seite der Zuweisung verwendet werden, oft dieselben, wie die Namen, die Sie den Tupelelementen geben möchten.

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

Die Namen von Tupelelementen können von den Variablen abgeleitet werden, die zum Initialisieren der Tupel in C# 7.1 verwendet werden:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

Weitere Informationen über dieses Feature finden Sie im Artikel [Tupel](../tuples.md).

## <a name="reference-assembly-generation"></a>Generierung der Referenzassembly

Es gibt zwei neue Compileroptionen, die *Assemblys nur für Referenzen* generieren: [/refout](../language-reference/compiler-options/refout-compiler-option.md) und [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).
In den verlinkten Artikeln werden diese Optionen und Referenzassemblys ausführlich beschrieben.
