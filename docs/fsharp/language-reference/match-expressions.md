---
title: Vergleichsausdrücke
description: Erfahren Sie, wie die F# Vergleichsausdruck stellt verzweigungssteuerung, die auf dem Vergleich eines Ausdrucks mit einem Satz von Mustern basiert.
ms.date: 04/19/2018
ms.openlocfilehash: 69ff8de1617e6b55d112d310bfcd8b2f967b6e8a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645199"
---
# <a name="match-expressions"></a>Vergleichsausdrücke

Die `match` Ausdruck liefert verzweigungssteuerung, die auf dem Vergleich eines Ausdrucks mit einem Satz von Mustern basiert.

## <a name="syntax"></a>Syntax

```fsharp
// Match expression.
match test-expression with
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...

// Pattern matching function.
function
| pattern1 [ when condition ] -> result-expression1
| pattern2 [ when condition ] -> result-expression2
| ...
```

## <a name="remarks"></a>Hinweise

Die mustervergleichsausdrücke ermöglichen Verzweigungen durch komplexe auf Basis des Vergleichs eines Test-Ausdrucks mit einem Satz von Mustern. In der `match` Ausdruck, der *Testausdruck* mit jedes Muster verglichen wird, nacheinander, und wenn eine Übereinstimmung gefunden wird, wird das entsprechende *Ergebnisausdruck* wird ausgewertet, und der resultierende Wert als der Wert des Ausdrucks Übereinstimmung zurückgegeben.

Mustervergleich in der vorherigen Syntax gezeigt Funktion ist ein Lambda-Ausdruck, in welches, den Muster übereinstimmende sofort für das Argument ausgeführt wird. Der Musterabgleich-Funktion in der vorherigen Syntax ist äquivalent zu folgendem.

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda-Ausdrücken: Die `fun` Schlüsselwort](functions/lambda-expressions-the-fun-keyword.md).

Die gesamte Gruppe von Mustern sollten alle möglichen Übereinstimmungen der Eingabevariablen abdecken. In vielen Fällen verwenden Sie das Platzhaltermuster (`_`) als das letzte Muster entsprechend alle zuvor nicht übereinstimmende Eingabewerte.

Der folgende Code zeigt einige der Methoden in der die `match` Ausdruck wird verwendet. Eine Referenz und Beispiele für alle Muster, die verwendet werden können, finden Sie unter [Musterabgleich](pattern-matching.md).

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a>Wächter für Muster

Sie können eine `when` -Klausel, um eine zusätzliche Bedingung anzugeben, die die Variable ein Muster erfüllen müssen. Diese Klausel wird als bezeichnet ein *schützen*. Der Ausdruck nach den `when` Schlüsselwort wird nicht ausgewertet, wenn eine Übereinstimmung für das Muster, die dem Wächter zugeordnet ist.

Das folgende Beispiel veranschaulicht die Verwendung von Wächter einen numerischen Bereich für ein Variablenmuster an. Beachten Sie, dass mehrere Bedingungen mit booleschen Operatoren kombiniert werden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

Beachten Sie, dass da andere Werte als Literale in das Muster verwendet werden können, müssen Sie verwenden eine `when` -Klausel, wenn einen Teil der Eingabe mit einem Wert zu vergleichen. Dies wird im folgenden Code gezeigt:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

Beachten Sie, dass bei einem union-Muster durch eine Guard abgedeckt ist, um der Wächter gilt **alle** der Muster, nicht nur die letzte Aktivität. Betrachten Sie den folgenden Code, den Wächter `when a > 12` gilt für `A a` und `B a`:

```fsharp
type Union =
    | A of int
    | B of int

let foo() =
    let test = A 42
    match test with
    | A a
    | B a when a > 41 -> a // the guard applies to both patterns
    | _ -> 1

foo() // returns 42
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Aktive Muster](active-patterns.md)
- [Mustervergleich](pattern-matching.md)
