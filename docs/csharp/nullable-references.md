---
title: Nullwerte zulassende Verweistypen
description: Dieser Artikel bietet eine Übersicht der Nullable-Verweistypen, die in C# 8.0 hinzugefügt wurden. Sie erfahren, wie das Feature bei neuen und vorhandenen Projekten vor Nullverweisausnahmen schützt.
ms.technology: csharp-null-safety
ms.date: 04/21/2020
ms.openlocfilehash: b4906987ee23f458c1da9754ed7b402621169f63
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099339"
---
# <a name="nullable-reference-types"></a>Nullwerte zulassende Verweistypen

Mit den in C# 8.0 eingeführten **Nullable-Verweistypen** und **Nicht-Nullable-Verweistypen** können Sie wichtige Anweisungen zu den Eigenschaften für Verweistypvariablen erstellen:

- **Ein Verweis darf nicht NULL sein**. Wenn Variablen nicht NULL sein dürfen, erzwingt der Compiler Regeln, die sicherstellen, dass das Dereferenzieren dieser Variablen sicher ist, ohne zuerst zu überprüfen, dass sie nicht NULL sind:
  - Die Variable muss mit einem Wert ungleich NULL initialisiert werden.
  - Der Variablen kann nie der Wert `null` zugewiesen werden.
- **Ein Verweis darf NULL sein**. Wenn Variablen NULL sein dürfen, erzwingt der Compiler verschiedene Regeln, um sicherzustellen, dass Sie richtig auf einen Nullverweis überprüft haben:
  - Die Variable kann nur dereferenziert werden, wenn der Compiler garantieren kann, dass der Wert nicht NULL ist.
  - Diese Variablen können mit dem Standardwert `null` initialisiert und in anderem Code dem Wert `null` zugewiesen werden.

Dieses neue Feature bietet große Vorteile hinsichtlich der Verarbeitung von Verweisvariablen in früheren Versionen von C#, bei denen die Entwurfsabsicht nicht über die Variablendeklaration bestimmt werden kann. Der Compiler bot keinen Schutz gegen Nullverweisausnahmen für Verweistypen:

- **Ein Verweis kann NULL sein**. Wenn eine Verweistypvariable mit `null` initialisiert oder später `null` zugewiesen wird, gibt der Compiler keine Warnungen aus. Der Compiler gibt Warnungen aus, wenn diese Variablen ohne NULL-Überprüfungen dereferenziert werden.
- **Es wird angenommen, dass ein Verweis nicht NULL ist**. Der Compiler gibt keine Warnungen aus, wenn Verweistypen dereferenziert werden. Der Compiler gibt Warnungen aus, wenn eine Variable auf einen Ausdruck festgelegt ist, der NULL sein kann.

Diese Warnungen werden zum Zeitpunkt der Kompilierung ausgegeben. Der Compiler fügt keine NULL-Überprüfungen oder andere Laufzeitkonstrukte in einem Nullable-Kontext hinzu. Zur Laufzeit sind ein Nullable-Verweis und ein Non-Nullable-Verweis gleichwertig.

Durch das Hinzufügen von Nullable-Verweistypen können Sie Ihre Absicht klarer deklarieren. Der `null`-Wert ist die richtige Wahl, um darzustellen, dass eine Variable auf keinen Wert verweist. Verwenden Sie dieses Feature nicht dazu, alle `null`-Werte aus Ihrem Code zu entfernen. Stattdessen sollten Sie Ihre Absicht gegenüber dem Compiler und anderen Entwicklern deklarieren, die Ihren Code lesen. Indem Sie Ihre Absicht deklarieren, werden Sie vom Compiler informiert, sobald Sie Code schreiben, der dieser Absicht widerspricht.

Ein **Nullable-Verweistyp** wird mithilfe der gleichen Syntax wie [Nullable-Werttypen](language-reference/builtin-types/nullable-value-types.md) aufgeführt: Ein `?` wird an den Variablentyp angefügt. Beispielsweise stellt die folgende Variablendeklaration eine Nullable-Zeichenfolgenvariable, `name`, dar:

```csharp
string? name;
```

Bei jeder Variable, bei der `?` nicht an den Typnamen angefügt ist, handelt es sich um einen **Non-Nullable-Verweistyp**. Dies umfasst alle Verweistypvariablen in vorhandenem Code, wenn Sie dieses Feature aktiviert haben.

Der Compiler verwendet die statische Analyse, um zu bestimmen, ob ein Nullable-Verweis nicht NULL ist. Der Compiler warnt Sie, falls Sie einen Nullable-Verweis dereferenzieren, wenn dieser möglicherweise NULL ist. Sie können dieses Verhalten überschreiben, indem Sie den [NULL-toleranten Operator](language-reference/operators/null-forgiving.md) (`!`) gefolgt von einem Variablennamen verwenden. Wenn Sie beispielsweise wissen, dass die Variable `name` nicht NULL ist, der Compiler aber eine Warnung ausgibt, können Sie folgenden Code schreiben, um die Compileranalyse zu überschreiben:

```csharp
name!.Length;
```

## <a name="nullability-of-types"></a>NULL-Zulässigkeit von Typen

Jeder beliebige Verweistyp kann über eine von vier *NULL-Zulässigkeiten* verfügen, die beschreibt, wann Warnungen ausgegeben werden:

- *Nonnullable* (Nicht-Nullable): Variablen dieses Typs kann NULL nicht zugewiesen werden. Variablen dieses Typs müssen vor der Dereferenzierung nicht auf NULL überprüft werden.
- *Nullable*: Variablen dieses Typs kann NULL zugewiesen werden. Wenn Variablen dieses Typs dereferenziert werden, ohne dass zuvor auf `null` überprüft wurde, wird eine Warnung ausgegeben.
- *Oblivious* (Nichtbeachtend): Oblivious ist der Zustand vor C# 8.0. Variablen dieses Typs können ohne Warnungen dereferenziert oder zugewiesen werden.
- *Unknown* (Unbekannt): Unknown ist im Allgemeinen für Typparameter gedacht, bei denen der Compiler von Einschränkungen nicht erfährt, dass es sich bei dem Typ um einen *Nullable-* oder einen *Non-Nullable-Typ* handeln muss.

Die NULL-Zulässigkeit eines Typs in einer Variablendeklaration wird durch den *Nullable-Kontext* gesteuert, in der die Variable deklariert wird.

## <a name="nullable-contexts"></a>Nullable-Kontexte

Nullable-Kontexte ermöglichen eine differenzierte Steuerung der Interpretation von Verweistypvariablen durch den Compiler. Der **Nullable-Anmerkungskontext** jeder beliebigen Quellzeile ist aktiviert oder deaktiviert. Der Compiler vor C# 8.0 hat Ihren gesamten Code in einem deaktivierten Nullable-Kontext kompiliert: Jeder Verweistyp kann NULL sein. Der **Kontext „nullable warnings“** (Nullable-Warnungen) kann ebenfalls aktiviert oder deaktiviert sein. Der Nullable-Warnungskontext gibt die vom Compiler generierten Warnungen mithilfe der Flussanalyse an.

Der Nullable-Anmerkungskontext und der Nullable-Warnungskontext können für ein Projekt festgelegt werden, indem Sie das `Nullable`-Element in Ihrer *CSPROJ*-Datei verwenden. Dieses Element konfiguriert, wie der Compiler die NULL-Zulässigkeit von Typen interpretiert und welche Warnungen generiert werden. Gültige Einstellungen sind folgende:

- `enable`: Der Nullable-Anmerkungskontext ist **enabled** (aktiviert). Der Nullable-Warnungskontext ist **enabled** (aktiviert).
  - Variablen eines Verweistyps wie `string` sind „non-nullable“ (nicht-nullable).  Alle NULL-Zulässigkeitswarnungen sind „enabled“ (aktiviert).
- `warnings`: Der Nullable-Anmerkungskontext ist **disabled** (deaktiviert). Der Nullable-Warnungskontext ist **enabled** (aktiviert).
  - Variablen eines Verweistyps sind „oblivious“ (nichtbeachtend). Alle NULL-Zulässigkeitswarnungen sind „enabled“ (aktiviert).
- `annotations`: Der Nullable-Anmerkungskontext ist **enabled** (aktiviert). Der Nullable-Warnungskontext ist **disabled** (deaktiviert).
  - Variablen eines Verweistyps wie „string“ sind „non-nullable“ (nicht-nullable). Alle NULL-Zulässigkeitswarnungen sind „disabled“ (deaktiviert).
- `disable`: Der Nullable-Anmerkungskontext ist **disabled** (deaktiviert). Der Nullable-Warnungskontext ist **disabled** (deaktiviert).
  - Variablen eines Verweistyps sind „oblivious“ (nichtbeachtend), wie in früheren Versionen von C#. Alle NULL-Zulässigkeitswarnungen sind „disabled“ (deaktiviert).

**Beispiel**:

```xml
<Nullable>enable</Nullable>
```

Sie können auch Anweisungen verwenden, um diese Kontexte überall in Ihrem Projekt festzulegen:

- `#nullable enable`: Legt den Nullable-Anmerkungskontext und den Nullable-Warnungskontext auf **enabled** (aktiviert) fest.
- `#nullable disable`: Legt den Nullable-Anmerkungskontext und den Nullable-Warnungskontext auf **disabled** (deaktiviert) fest.
- `#nullable restore`: Stellt die Projekteinstellungen für den Nullable-Anmerkungskontext und den Nullable-Warnungskontext wieder her.
- `#nullable disable warnings`: Legt den Nullable-Warnungskontext auf **disabled** (deaktiviert) fest.
- `#nullable enable warnings`: Legt den Nullable-Warnungskontext auf **enabled** (aktiviert) fest.
- `#nullable restore warnings`: Stellt die Projekteinstellungen für den Nullable-Warnungskontext wieder her.
- `#nullable disable annotations`: Legt den Nullable-Anmerkungskontext auf **disabled** (deaktiviert) fest.
- `#nullable enable annotations`: Legt den Nullable-Anmerkungskontext auf **enabled** (aktiviert) fest.
- `#nullable restore annotations`: Stellt die Projekteinstellungen für den Anmerkungswarnungskontext wieder her.

> [!IMPORTANT]
> Der globale Nullable-Kontext gilt nicht für generierte Codedateien. Der Nullable-Kontext ist unabhängig von der Strategie für alle als generiert gekennzeichneten Quelldateien *deaktiviert*. Das bedeutet, dass alle in generierten Dateien enthaltenen APIs nicht mit Anmerkungen versehen werden. Es gibt viel Möglichkeiten, eine Datei als generiert zu markieren:
>
> 1. Geben Sie in der EDITORCONFIG-Datei `generated_code = true` in einem Abschnitt an, der für diese Datei gilt.
> 1. Fügen Sie `<auto-generated>` oder `<auto-generated/>` ganz oben in der Datei in einem Kommentar ein. Dabei kann es sich um eine beliebige Zeile des Kommentars handeln, jedoch muss es sich beim Kommentarblock um das erste Element in der Datei handeln.
> 1. Beginnen Sie den Dateinamen mit *TemporaryGeneratedFile_* .
> 1. Enden Sie den Dateinamen mit *.designer.cs*, *.generated.cs*, *.g.cs* oder *.g.i.cs*.
>
> Generatoren können die Präprozessoranweisung [`#nullable`](language-reference/preprocessor-directives/preprocessor-nullable.md) verwenden.

Standardmäßig sind die Nullable-Anmerkungs- und -Warnungskontexte, einschließlich neuer Projekte, **deaktiviert**. Dies bedeutet, dass Ihr vorhandener Code ohne Änderungen und ohne Warnungen kompiliert wird.

Diese Optionen bieten zwei unterschiedliche Strategien zum [Aktualisieren einer vorhandenen Codebasis](nullable-migration-strategies.md), um Nullable-Verweistypen zu verwenden.

## <a name="nullable-annotation-context"></a>Nullable-Anmerkungskontext

Der Compiler verwendet die folgenden Regeln in einem „disabled“-Nullable-Anmerkungskontext:

- Sie können keine Nullable-Verweise in einem „disabled“-Kontext deklarieren.
- Alle Verweisvariablen kann ein Wert von NULL zugewiesen werden.
- Wenn eine Variable eines Verweistyps dereferenziert wird, werden keine Warnungen generiert.
- Der NULL-tolerante Operator kann in einem „disabled“-Kontext nicht verwendet werden.

Das Verhalten ist wie bei früheren Versionen von C#.

Der Compiler verwendet die folgenden Regeln in einem „enabled“-Nullable-Anmerkungskontext:

- Jede Variable eines Verweistyps ist ein **Nicht-Nullable-Verweis**.
- Jeder Nicht-Nullable-Verweis kann sicher dereferenziert werden.
- Jeder Nullable-Verweistyp (aufgeführt durch `?` nach dem Typ in der Variablendeklaration) kann NULL sein. Durch die statische Analyse wird bestimmt, ob der Wert ungleich NULL ist, wenn er dereferenziert wird. Ist dies nicht der Fall, werden Sie vom Compiler gewarnt.
- Sie können den NULL-toleranten Operator verwenden, um zu deklarieren, dass ein Nullable-Verweis nicht NULL ist.

In einem „enabled“-Nullable-Anmerkungskontext deklariert das an einen Verweistyp angefügte Zeichen `?` einen **Nullable-Verweistyp**. Der **NULL-tolerante Operator** (`!`) kann an einen Ausdruck angefügt werden, um zu deklarieren, dass der Ausdruck nicht NULL ist.

## <a name="nullable-warning-context"></a>Nullable-Warnungskontext

Der Nullable-Warnungskontext unterscheidet sich vom Nullable-Anmerkungskontext. Warnungen können selbst dann aktiviert sein, wenn die neuen Anmerkungen deaktiviert sind. Der Compiler bestimmt mithilfe der statischen Flussanalyse den **NULL-Zustand** eines Verweises. Der NULL-Zustand ist entweder **not null** (nicht NULL) oder **maybe null** (vielleicht NULL), wenn der *Nullable-Warnungskontext* nicht **disabled** (deaktiviert) ist. Wenn Sie einen Verweis dereferenzieren, wenn der Compiler bestimmt hat, dass dessen Zustand **maybe null** (vielleicht NULL) lautet, löst der Compiler eine Warnung aus. Der Status eines Verweises ist **maybe null** (vielleicht NULL), sofern der Compiler nicht eine der folgenden beiden Bedingungen bestimmen kann:

1. Die Variable wurde definitiv einem Wert ungleich NULL zugewiesen.
1. Die Variable oder der Ausdruck wurde vor der Dereferenzierung auf NULL überprüft.

Der Compiler generiert Warnungen, wenn Sie in einem Nullable-Warnungskontext eine Variable oder einen Ausdruck dereferenzieren, die oder der **vielleicht NULL** ist. Darüber hinaus generiert der Compiler Warnungen, wenn einer Variable oder einem Ausdruck, die oder der **vielleicht NULL** ist, in einem aktivierten Nullable-Anmerkungskontext eine Non-Nullable-Verweistypvariable zugewiesen wird.

## <a name="attributes-describe-apis"></a>Beschreiben von APIs mit Attributen

Sie fügen APIs Attribute hinzu, die für den Compiler weitere Informationen darüber bereitstellen, wann Argumente oder Rückgabewerte NULL sein können oder nicht. Weitere Informationen zu diesen Attributen finden Sie in unserem Artikel in der Programmiersprachenreferenz zu den [Nullable-Attributen](language-reference/attributes/nullable-analysis.md). Diese Attribute werden über aktuelle und kommende Releases zu .NET-Bibliotheken hinzugefügt. Die am häufigsten verwendeten APIs werden zuerst aktualisiert.

## <a name="known-pitfalls"></a>Bekannte Fehlerquellen

Arrays und Strukturen, die Verweistypen enthalten, sind bekannte Fehlerquellen in Features, die NULL-Werte für Verweistypen zulassen.

### <a name="structs"></a>Strukturen

Strukturen, die Verweistypen enthalten, die keine NULL-Werte zulassen, können Sie `default` zuweisen, ohne dass Warnungen ausgelöst werden. Betrachten Sie das folgenden Beispiel:

```csharp
using System;

#nullable enable

public struct Student
{
    public string FirstName;
    public string? MiddleName;
    public string LastName;
}

public static class Program
{
    public static void PrintStudent(Student student)
    {
        Console.WriteLine($"First name: {student.FirstName.ToUpper()}");
        Console.WriteLine($"Middle name: {student.MiddleName.ToUpper()}");
        Console.WriteLine($"Last name: {student.LastName.ToUpper()}");
    }

    public static void Main() => PrintStudent(default);
}
```

Im obigen Beispiel gibt es in `PrintStudent(default)` keine Warnung, obwohl die Verweistypen `FirstName` und `LastName`, die keine NULL-Werte zulassen, NULL zurückgeben.

Bei der Verwendung von generischen Strukturen tritt ein weiteres häufigeres Problem auf. Betrachten Sie das folgenden Beispiel:

```csharp
#nullable enable

public struct Foo<T>
{
    public T Bar { get; set; }
}

public static class Program
{
    public static void Main()
    {
        string s = default(Foo<string>).Bar;
    }
}
```

Im obigen Beispiel entspricht die Eigenschaft `Bar` zur Laufzeit `null`, und sie wird einer Zeichenfolge zugewiesen, die keine NULL-Werte zulässt, ohne dass eine Warnung ausgelöst wird.

### <a name="arrays"></a>Arrays

Arrays stellen ebenfalls eine bekannte Fehlerquelle in Verweistypen dar, die NULL-Werte zulassen. Sehen Sie sich das folgende Beispiel an, das keine Warnungen auslöst:

```csharp
using System;

#nullable enable

public static class Program
{
    public static void Main()
    {
        string[] values = new string[10];
        string s = values[0];
        Console.WriteLine(s.ToUpper());
    }
}
```

Im obigen Beispiel zeigt die Deklaration des Arrays, dass dieses Zeichenfolgen enthält, die keine NULL-Werte zulassen, während alle seine Elemente mit NULL-Werten initialisiert werden. Anschließend wird der Variablen `s` ein NULL-Wert (das erste Element des Arrays) zugewiesen. Schließlich wird die Variable `s` dereferenziert, was zu einer Laufzeitausnahme führt.

## <a name="see-also"></a>Siehe auch

- [Entwurf der Spezifikation für Nullable-Verweistypen](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md)
- [Tutorial: Besseres Ausdrücken Ihrer Entwurfsabsicht mit Verweistypen, die NULL-Werte zulassen und nicht zulassen](tutorials/nullable-reference-types.md)
- [Tutorial: Migrieren vorhandenen Codes mit Verweistypen, die NULL-Werte zulassen](tutorials/upgrade-to-nullable-references.md)
- [-nullable (C#-Compileroption)](language-reference/compiler-options/nullable-compiler-option.md)
