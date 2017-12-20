---
title: Was ist neu in c# 7.1
description: "Eine Übersicht über neue Funktionen in c# 7.1."
keywords: C#-Sprachentwurf, 7.1, Visual Studio-2017,
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 02f1f8fc8f0a3221e00e2a3c43ce06423ca43672
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="whats-new-in-c-71"></a>Was ist neu in c# 7.1

C#-7.1 ist der erste Punkt Version der C#-Sprache. Eine erhöhte-versionsrhythmus für die Sprache werden markiert. Sie können die neuen Funktionen früher, im Idealfall verwenden, wenn jeder neuen Funktion bereit ist. C#-7.1 fügt die Möglichkeit, den Compiler entsprechend eine angegebene Version der Sprache zu konfigurieren. Mit der Sie die Entscheidung zum Aktualisieren von Tools von der Entscheidung für eine Aktualisierung von Sprachversionen zu trennen.

C#-7.1 fügt die [Version Sprachauswahl](#language-version-selection) Konfigurationselement, drei neue Sprachfunktionen zu nutzen und neue Compilerverhalten.

Die neuen Sprachfeatures in dieser Version sind:

* [`async``Main` Methode](#async-main)
  - Der `async`-Modifizierer kann am Einstiegspunkt einer Anwendung verwendet werden.
* [`default`Literale Ausdrücke](#default-literal-expressions)
  - Sie können Literale Standardausdrücken in Default-Wert-Ausdrücken verwenden, wenn der Zieltyp abgeleitet werden kann.
* [Abgeleitete Tupel Elementnamen](#inferred-tuple-element-names)
  - Tupel Initialisierung in vielen Fällen können die Namen der Tupelelemente abgeleitet werden.

Schließlich der Compiler verfügt über zwei Optionen `/refout` und `/refonly` das entsprechende Steuerelement [Generieren der Assembly verweisen](#reference-assembly-generation).

## <a name="language-version-selection"></a>Sprachauswahl-version

Der C#-Compiler unterstützt c# 7.1 beginnend mit Visual Studio 2017 Version 15.3 oder .NET Core SDK 2.0. Allerdings sind die 7.1 Funktionen standardmäßig deaktiviert. Um die 7.1-Funktionen zu aktivieren, müssen Sie die Spracheinstellung für die Version für das Projekt zu ändern.

Klicken Sie in Visual Studio mit der rechten Maustaste auf den Projektknoten im Projektmappen-Explorer, und wählen Sie **Eigenschaften**. Wählen Sie die **erstellen** Registerkarte, und wählen Sie die **erweitert** Schaltfläche. Wählen Sie in der Dropdownliste **c# neueste Nebenversion (aktuellste Version)**, oder eine bestimmte Version **c# 7.1** wie im folgenden Bild gezeigt. Die `latest` Wert bedeutet, dass Sie die aktuelle Nebenversion auf dem aktuellen Computer verwenden möchten. Die `C# 7.1` bedeutet, dass die gewünschten c# 7.1 verwenden, auch nachdem die neuere Nebenversionen freigegeben werden.

![Die Sprachversion festlegen](./media/csharp-7-1/advanced-build-settings.png)

Sie können alternativ bearbeiten Sie die Datei "Csproj" und hinzufügen oder ändern die folgenden Zeilen:

```xml
<PropertyGroup>
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

> [!NOTE]
> Wenn Sie Visual Studio-IDE verwenden, um die Csproj-Dateien aktualisiert werden, erstellt die IDE separate Knoten für jede Buildkonfiguration. In der Regel legen Sie dem Wert der gleiche in alle Buildkonfigurationen, jedoch müssen Sie explizit für jede Buildkonfiguration festgelegt, oder wählen Sie "Alle Konfigurationen" aus, wenn Sie diese Einstellung zu ändern. Im folgenden sehen Sie in der Csproj-Datei:

```xml
<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>

<PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|AnyCPU'">
  <LangVersion>latest</LangVersion>
</PropertyGroup>
```

Gültige Einstellungen für die `LangVersion` -Element sind:

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

Die speziellen Zeichenfolgen `default` und `latest` auf die neueste Haupt- und Nebenversionsnummern Sprachversionen auf dem Buildcomputer installiert wurde, bzw. beheben.

Diese Einstellung entkoppelt, installieren neue Versionen des SDK und Tools in der Entwicklungsumgebung von auswählen, um neue Sprachfeatures in einem Projekt einzubinden. Sie können das neueste SDK und Tools auf dem Buildcomputer installieren. Jedes Projekt kann konfiguriert werden, um eine bestimmte Version der Sprache für ihre Build verwenden.

## <a name="async-main"></a>Async-Hauptfenster

Ein *Async main* Methode ermöglicht Ihnen die Verwendung `await` in Ihrer `Main` Methode.
Bisher mussten Sie zum Schreiben:

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

Sie können jetzt Folgendes schreiben:

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

Wenn das Programm einen Exitcode zurückgegeben wird, können Sie deklarieren eine `Main` Methode, die zurückgibt eine <xref:System.Threading.Tasks.Task>:

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

Erfahren Sie mehr über die Details in der [Async main](../programming-guide/main-and-command-args/index.md) Thema des Handbuchs Programmierung.

## <a name="default-literal-expressions"></a>Literale Standardausdrücke

Standard-Literale Ausdrücke sind eine Erweiterung Default-Wert-Ausdrücken.
Diese Ausdrücke initialisiert werden, eine Variable auf den Standardwert. Sie würden, in dem zuvor schreiben:

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

Sie können jetzt den Typ auf der rechten Seite der Initialisierung weglassen:

```csharp
Func<string, bool> whereClause = default;
```

Sie können erfahren Sie mehr über diese Erweiterung in der C#-Programmierhandbuch Thema auf [Standard Wertausdrücke](../programming-guide/statements-expressions-operators/default-value-expressions.md).

Diese Erweiterung ändert sich auch einige der Regeln für die Analyse der [default-Schlüsselwort](../language-reference/keywords/default.md).

## <a name="inferred-tuple-element-names"></a>Abgeleitete Tupel Elementnamen

Diese Funktion ist eine kleine Erweiterung der Tupel-Funktion in c# 7.0 eingeführt. Oft bei der Initialisierung eines Tupels sind Variablen, die für die rechte Seite der Zuweisung verwendet identisch mit den Namen, die Sie für die Tupelelemente würde wie folgt:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

Die Variablen verwendet, um das Tupel in c# 7.1 initialisieren können die Namen der Tupelelemente abgeleitet werden:

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

Weitere Informationen finden Sie Informationen zu dieser Funktion in der [Tupel](../tuples.md) Thema.

## <a name="reference-assembly-generation"></a>Generieren der Assembly Verweis

Es gibt zwei neue Compileroptionen, die generieren *Verweis reine Assemblys*: [/refout](../language-reference/compiler-options/refout-compiler-option.md) und [/refonly](../language-reference/compiler-options/refonly-compiler-option.md).
In den verknüpften Themen werden diese Optionen und die Verweisassemblys ausführlicher erläutert.
