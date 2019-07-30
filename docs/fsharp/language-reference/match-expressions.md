---
title: Ausdrücke vergleichen
description: Erfahren Sie, F# wie der Übereinstimmungs Ausdruck eine Verzweigungs Steuerung bereitstellt, die auf dem Vergleich eines Ausdrucks mit einer Reihe von Mustern basiert.
ms.date: 04/19/2018
ms.openlocfilehash: 222cb0604300039d86ed0c80293651631d212eb6
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627605"
---
# <a name="match-expressions"></a>Ausdrücke vergleichen

Der `match` Ausdruck stellt ein Verzweigungs Steuerelement bereit, das auf dem Vergleich eines Ausdrucks mit einer Reihe von Mustern basiert.

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

Die Muster Vergleichsausdrücke ermöglichen eine komplexe Verzweigung basierend auf dem Vergleich eines Test Ausdrucks mit einer Reihe von Mustern. Im Ausdruck wird der *Test Ausdruck* mit den einzelnen Mustern verglichen. Wenn eine Übereinstimmung gefunden wird, wird der entsprechende *Ergebnis Ausdruck* ausgewertet, und der resultierende Wert wird als Wert des Vergleichs Ausdrucks zurückgegeben. `match`

Die in der vorherigen Syntax gezeigte Muster Vergleichsfunktion ist ein Lambda Ausdruck, in dem der Musterabgleich sofort auf dem Argument ausgeführt wird. Die in der vorherigen Syntax gezeigte Muster Vergleichsfunktion entspricht der folgenden.

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

Weitere Informationen zu Lambda-Ausdrücken finden [Sie unter Lambda-Ausdrücke: Das `fun` Schlüssel](./functions/lambda-expressions-the-fun-keyword.md)Wort.

Der gesamte Satz von Mustern sollte alle möglichen Übereinstimmungen der Eingabevariablen abdecken. Häufig verwenden Sie das Platzhalter Muster (`_`) als letztes Muster, um alle zuvor nicht übereinstimmenden Eingabewerte abzugleichen.

Der folgende Code veranschaulicht einige der Methoden, mit denen der `match` Ausdruck verwendet wird. Einen Verweis und Beispiele für alle möglichen Muster, die verwendet werden können, finden Sie unter [Muster](pattern-matching.md)Abgleich.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a>Wächter bei Mustern

Sie können eine `when` -Klausel verwenden, um eine zusätzliche Bedingung anzugeben, die die Variable erfüllen muss, damit Sie einem Muster entspricht. Eine solche Klausel wird als *Wächter*bezeichnet. Der Ausdruck, der `when` auf das-Schlüsselwort folgt, wird nur ausgewertet, wenn eine Entsprechung für das diesem Guard zugeordnete Muster vorliegt.

Das folgende Beispiel veranschaulicht die Verwendung eines-Schutzes, um einen numerischen Bereich für ein Variablen Muster anzugeben. Beachten Sie, dass mehrere Bedingungen mithilfe von booleschen Operatoren kombiniert werden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

Beachten Sie, dass Sie eine `when` -Klausel verwenden müssen, wenn Sie einen Teil der Eingabe mit einem Wert vergleichen müssen, weil andere Werte als Literale nicht im Muster verwendet werden können. Dies wird im folgenden Code veranschaulicht:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

Beachten Sie Folgendes: Wenn ein Union-Muster durch einen Wächter abgedeckt wird, gilt der Wächter für **alle** Muster, nicht nur für den letzten. Beispielsweise gilt für den folgenden Code, dass der `when a > 12` Wächter sowohl `A a` für als `B a`auch für gilt:

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
