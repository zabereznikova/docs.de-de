---
title: for-Anweisung in C#
ms.date: 06/13/2018
f1_keywords:
- for
- for_CSharpKeyword
helpviewer_keywords:
- for keyword [C#]
ms.assetid: 34041a40-2c87-467a-9ffb-a0417d8f67a8
ms.openlocfilehash: 5ebc478f8840173cacc0bc211061f3013379abd9
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422793"
---
# <a name="for-c-reference"></a>for (C#-Referenz)

Die Anweisung `for` führt eine Anweisung oder einen Anweisungsblock aus, während ein angegebener boolescher Ausdruck `true` ergibt.

Sie können die Schleife an jedem Punkt im `for`-Anweisungsblock mit der Anweisung [break](break.md) unterbrechen oder mit der Anweisung [continue](continue.md) direkt zum nächsten Durchlauf der Schleife springen. Sie können eine `for`-Schleife auch mit den Anweisungen [goto](goto.md), [return](return.md) oder [throw](throw.md) beenden.

## <a name="structure-of-the-for-statement"></a>Struktur der `for`-Anweisung

Jede `for`-Anweisung definiert die Abschnitte *initializer*, *condition* und *iterator*:

```csharp
for (initializer; condition; iterator)
    body
```

Alle drei Abschnitte sind optional. Der Schleifenkörper ist entweder eine Anweisung oder ein Anweisungsblock

Im folgenden Beispiel wird die `for`-Anweisung mit allen Abschnitten definiert dargestellt:

[!code-csharp-interactive[for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#5)]

### <a name="the-initializer-section"></a>Der Abschnitt *initializer*

Die Anweisungen im Abschnitt *initializer* werden nur einmal ausgeführt, bevor die Schleife beginnt. Der Abschnitt *initializer* ist eines der Folgenden:

- Die Deklaration und Initialisierung einer lokalen Schleifenvariable, auf die nicht von außerhalb der Schleife zugegriffen werden kann.

- Null (0) oder mehr durch Kommas getrennte Anweisungsausdrücke aus der folgenden Liste:

  - [Zuweisungsanweisung](../operators/assignment-operator.md)

  - Aufruf einer Methode

  - Präfix- oder Postfix-[Inkrementausdruck](../operators/arithmetic-operators.md#increment-operator-), z.B. `++i` oder `i++`

  - Präfix- oder Postfix-[Dekrementausdruck](../operators/arithmetic-operators.md#decrement-operator---), z.B. `--i` oder `i--`

  - Erstellung eines Objekts mithilfe des [new](../operators/new-operator.md)-Operators

  - [await](../operators/await.md)-Ausdruck

Der Abschnitt *initializer* im obigen Beispiel deklariert und initialisiert die lokale Schleifenvariable `i`:

```csharp
int i = 0
```

### <a name="the-condition-section"></a>Der Abschnitt *condition*

Der Abschnitt *condition* muss ein boolescher Ausdruck sein, wenn er vorhanden ist. Dieser Ausdruck wird vor jeder Schleifeniteration ausgewertet. Wenn der Abschnitt *condition* nicht vorhanden ist oder der boolesche Ausdruck `true` ergibt, wird die nächste Schleifeniteration ausgeführt. Andernfalls wird die Schleife beendet.

Im obigen Beispiel wird durch den Abschnitt *condition* bestimmt, ob die Schleife basierend auf dem Wert der lokalen Schleifenvariable beendet wird:

```csharp
i < 5
```

### <a name="the-iterator-section"></a>Der Abschnitt *iterator*

Der Abschnitt *iterator* definiert, was nach jeder Iteration des Schleifenkörpers geschieht. Der Abschnitt *iterator* enthält keine oder mehrere der folgenden durch Kommas getrennten Anweisungsausdrücke:

- [Zuweisungsanweisung](../operators/assignment-operator.md)

- Aufruf einer Methode

- Präfix- oder Postfix-[Inkrementausdruck](../operators/arithmetic-operators.md#increment-operator-), z.B. `++i` oder `i++`

- Präfix- oder Postfix-[Dekrementausdruck](../operators/arithmetic-operators.md#decrement-operator---), z.B. `--i` oder `i--`

- Erstellung eines Objekts mithilfe des [new](../operators/new-operator.md)-Operators

- [await](../operators/await.md)-Ausdruck

Im Beispiel wird die lokale Schleifenvariable durch den Abschnitt *iterator* inkrementiert:

```csharp
i++
```

## <a name="examples"></a>Beispiele

Das folgende Beispiel veranschaulicht mehrere weniger übliche Verwendungen der Abschnitte der `for`-Anweisung: das Zuweisen eines Werts für eine externe Schleifenvariable im Abschnitt *initializer*, das Aufrufen einer Methode in den Abschnitten *initializer* und *iterator* und das Ändern der Werte von zwei Variablen im Abschnitt *iterator*. Klicken Sie auf **Run** (Ausführen), um den Beispielcode auszuführen. Danach können Sie Änderungen am Code vornehmen und ihn erneut ausführen.

[!code-csharp-interactive[not typical for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#6)]

Im folgenden Beispiel wird die Endlosschleife `for` definiert:

[!code-csharp[infinite for loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#7)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Die for-Anweisung](~/_csharplang/spec/statements.md#the-for-statement) der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [foreach, in](foreach-in.md)
