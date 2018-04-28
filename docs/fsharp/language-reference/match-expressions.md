---
title: Vergleichsausdrücke (f#)
description: Erfahren Sie, wie die Vergleichsausdruck [F#] Verzweigen gesteuert, die auf dem Vergleich eines Ausdrucks mit einem Satz von Mustern basiert.
author: cartermp
ms.author: phcart
ms.date: 04/19/2018
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: f6930f782384464f0d44b205ea77cbaf43898213
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="match-expressions"></a>Vergleichsausdrücke

Die `match` Ausdruck enthält, Verzweigen Steuerelement, das basierend auf den Vergleich eines Ausdrucks mit einem Satz von Mustern.

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

Das Muster übereinstimmenden-Ausdrücke ermöglichen komplexe Verzweigung basierend auf den Vergleich eines Test-Ausdrucks mit einem Satz von Mustern. In der `match` Ausdruck, der *Testausdruck* mit jedes Muster verglichen wird, wiederum, und wenn eine Übereinstimmung gefunden wird, wird das entsprechende *Ergebnisausdruck* wird ausgewertet, und der resultierende Wert als Wert des Ausdrucks Übereinstimmung zurückgegeben.

Funktion in der vorherigen Syntax für der Mustervergleich ist ein Lambda-Ausdruck, in welche, den Muster übereinstimmenden sofort für das Argument ausgeführt wird. Funktion in der vorherigen Syntax für der Mustervergleich ist äquivalent zu folgendem.

```fsharp
fun arg ->
    match arg with
    | pattern1 [ when condition ] -> result-expression1
    | pattern2 [ when condition ] -> result-expression2
    | ...
```

Weitere Informationen zu Lambda-Ausdrücken finden Sie unter [Lambda-Ausdrücke: das `fun` Schlüsselwort](functions/lambda-expressions-the-fun-keyword.md).

Der gesamte Satz von Mustern sollten alle möglichen Übereinstimmungen der Eingabevariablen abgedeckt. In vielen Fällen verwenden Sie das Platzhaltermuster (`_`) als das letzte Muster, die zuvor nicht übereinstimmenden Eingabewerten überein.

Das folgende Codebeispiel veranschaulicht einige der Methoden in der die `match` Ausdruck verwendet wird. Ein Verweis und Beispiele für alle Muster, die verwendet werden können, finden Sie unter [Mustervergleich](pattern-matching.md).

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4601.fs)]

## <a name="guards-on-patterns"></a>Wächter für Muster

Sie können eine `when` -Klausel, um eine weitere Bedingung angeben, die die Variable entsprechen muss, einem bestimmten Muster entsprechen. Diese Klausel wird als bezeichnet eine *schützen*. Der folgende Ausdruck den `when` Schlüsselwort wird nicht ausgewertet werden, es sei denn, eine Übereinstimmung, um das Muster, das dem Wächter zugeordnet festgestellt wurde.

Das folgende Beispiel veranschaulicht die Verwendung von Wächter einen numerischen Bereich für ein Variablenmuster an. Beachten Sie, dass mehrere Bedingungen mit booleschen Operatoren kombiniert werden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4602.fs)]

Beachten Sie, weil andere Werte als Literale in das Muster nicht verwendet werden können, müssen Sie verwenden eine `when` -Klausel, wenn Sie einen Teil der Eingabe mit einem Wert vergleichen. Dies wird im folgenden Code gezeigt:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4603.fs)]

Beachten Sie, dass wenn eine union-Muster von Wächter abgedeckt wird, für der Wächter gilt **alle** der Muster, nicht nur die letzte Aktivität. Angenommen, den folgenden Code, den Wächter `when a > 12` gelten für beide `A a` und `B a`:

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

[F#-Sprachreferenz](index.md)  
[Aktive Muster](active-patterns.md)  
[Mustervergleich](pattern-matching.md)  
