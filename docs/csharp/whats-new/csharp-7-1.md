---
title: Neues in C# 7.1
description: Eine Übersicht der neuen Features in C# 7.1
ms.date: 04/09/2019
ms.openlocfilehash: 5d2d6f51b6422f5b4db5c6bd275b5ffce1f695f8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79398352"
---
# <a name="whats-new-in-c-71"></a>Neues in C# 7.1

C# 7.1 ist die erste Punktversion der C#-Sprache. Das bedeutet schnellere Releaserhythmen für die Sprache. Sie können die neuen Features früher benutzen, im Idealfall sobald ein neues Feature bereit ist. Mit C# 7.1 wird die Fähigkeit hinzugefügt, den Compiler so zu konfigurieren, dass er einer bestimmten Version der Sprache entspricht. Damit können Sie die Entscheidung, Tools upzugraden, von der Entscheidung unterscheiden, Upgrades für Sprachversionen durchzuführen.

Mit C# 7.1 wird ein Konfigurationselement zum [Auswählen der Sprachversion](../language-reference/configure-language-version.md), drei neue Sprachfeatures und neues Compilerverhalten hinzugefügt.

Die neuen Sprachfeatures in diesem Release umfassen:

- [`async` `Main`-Methode](#async-main)
  - Der Einstiegspunkt für eine Anwendung kann über den Modifizierer `async` verfügen.
- [`default`Literale Ausdrücke](#default-literal-expressions)
  - Sie können literale Standardausdrücke in Standardwertausdrücken verwenden, wenn der Zieltyp abgeleitet werden kann.
- [Abgeleitete Tupelelementnamen](#inferred-tuple-element-names)
  - Die Namen von Tupelelementen können in den meisten Fällen von der Initialisierung eines Tupels abgeleitet werden.
- [Musterabgleich für generische Typparameter](#pattern-matching-on-generic-type-parameters)
  - Sie können Musterabgleichsausdrücke für Variablen verwenden, deren Typ ein generischer Typparameter ist.

Außerdem verfügt der Compiler über die zwei Optionen `-refout` und `-refonly`, mit denen die [Generierung der Referenzassembly](#reference-assembly-generation) gesteuert wird.

Sie müssen [die Sprachversion des Compilers konfigurieren](../language-reference/configure-language-version.md) und die Version auswählen, um die neuesten Features in einer Punktversion zu verwenden.

Dieser Artikel enthält im Folgenden eine Übersicht über die einzelnen Funktionen. Sie werden die Hintergründe jeder einzelnen Funktion erfahren. Sie werden die Syntax erlernen. Sie können sich diese Funktionen in unserer Umgebung mit dem globalen `dotnet try`-Tool näher ansehen:

1. Installieren Sie das globale [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup)-Tool.
1. Klonen Sie das [dotnet/try-samples](https://github.com/dotnet/try-samples)-Repository.
1. Legen Sie das aktuelle Verzeichnis auf das Unterverzeichnis *csharp7* für das *try-samples*-Repository fest.
1. Führen Sie `dotnet try` aus.

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

Weitere Informationen finden Sie im Abschnitt [Standardliteral](../language-reference/operators/default.md#default-literal) des Artikels zum [default-Operator](../language-reference/operators/default.md).

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

## <a name="pattern-matching-on-generic-type-parameters"></a>Musterabgleich für generische Typparameter

Ab C# 7.1 kann der Musterausdruck für `is` und das `switch`-Typmuster den Typ eines generischen Typparameters haben. Dies kann sehr nützlich sein, wenn Sie Typen überprüfen, die entweder `struct`- oder `class`-Typen sein können, und Sie Boxing vermeiden möchten.

## <a name="reference-assembly-generation"></a>Generierung der Referenzassembly

Es gibt zwei neue Compileroptionen, die *Assemblys nur für Referenzen* generieren: [-refout](../language-reference/compiler-options/refout-compiler-option.md) und [-refonly](../language-reference/compiler-options/refonly-compiler-option.md).
In den verlinkten Artikeln werden diese Optionen und Referenzassemblys ausführlich beschrieben.
