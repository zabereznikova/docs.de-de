---
title: Automatische Verallgemeinerung
description: Erfahren Sie, wie F# automatisch die Argumente und Funktionstypen verallgemeinert, damit sie mit mehreren Typen nach Möglichkeit funktionieren.
ms.date: 05/16/2016
ms.openlocfilehash: 15ecf8e6f07da19bb015fd028a7465ba8b837190
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53611710"
---
# <a name="automatic-generalization"></a>Automatische Verallgemeinerung

F#verwendet die Typrückschluss um die Arten von Funktionen und Ausdrücke zu bewerten. In diesem Thema wird beschrieben, wie F# automatisch die Argumente und Funktionstypen verallgemeinert, damit sie mit mehreren Arten funktionieren, wenn dies möglich ist.

## <a name="automatic-generalization"></a>Automatische Verallgemeinerung

Die F# -Compiler, wenn er den Typrückschluss auf eine Funktion ausführt bestimmt, ob für ein bestimmten Parameter generisch sein kann. Der Compiler untersucht jeden Parameter und bestimmt, ob die Funktion eine Abhängigkeit vom angegebenen Typ dieses Parameters hat. Wenn dies nicht der Fall ist, wird der Typ abgeleitet, generisch sein.

Im folgenden Codebeispiel wird veranschaulicht, eine Funktion, die der Compiler leitet ab, um generisch sein.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

Der Typ wird abgeleitet sein `'a -> 'a -> 'a`.

Der Typ gibt an, dass dies eine Funktion, die akzeptiert zwei Argumente des gleichen unbekannten Typs und gibt einen Wert desselben Typs zurück. Einer der Gründe, die die vorherige Funktion sein, können generisch ist, das größer-als-Operator (`>`) selbst generisch ist. Größer-als Operator die Signatur hat `'a -> 'a -> bool`. Nicht alle Operatoren sind generisch, und wenn der Code in einer Funktion einen Parametertyp zusammen mit einer nicht generischen Funktion oder Operator verwendet, kann dieser Parametertyp kann nicht generalisiert werden.

Da `max` ist generisch ist, sie können mit Typen verwendet werden wie z. B. `int`, `float`und so weiter, wie in den folgenden Beispielen gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

Allerdings müssen die beiden Argumente vom gleichen Typ sein. Die Signatur ist `'a -> 'a -> 'a`, nicht `'a -> 'b -> 'a`. Aus diesem Grund generiert der folgende Code einen Fehler, da die Datentypen nicht übereinstimmen.

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

Die `max` Funktion funktioniert auch mit jeder Typ, der größer unterstützt-als-Operator. Aus diesem Grund könnte auch auf eine Zeichenfolge, Verwendung wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a>Wertebeschränkung

Der Compiler führt die automatische Verallgemeinerung nur für vollständige Funktionsdefinitionen, die expliziten Argumente haben, und klicken Sie auf einfache unveränderlichen Werten.

Dies bedeutet, dass der Compiler einen Fehler ausgibt, wenn Sie versuchen, Code zu kompilieren, die nicht ausreichend sollen einen bestimmten Typ beschränkt ist, jedoch ist auch nicht generalisierbar. Die Fehlermeldung für dieses Problem bezieht sich auf die diese Einschränkung für die automatische Verallgemeinerung für Werte als die *wertebeschränkung*.

In der Regel tritt auf, der Wert Einschränkung Fehler, wenn Sie möchten ein Konstrukt generisch sein, aber der Compiler hat nicht genügend Informationen, um sie zu generalisieren oder unbeabsichtigt genügend Typinformationen in einer nicht generischen Konstrukts ohne Angabe. Die Lösung auf den Wert Einschränkung Fehler besteht darin, geben Sie explizitere Informationen, um das Problem Type Inference ausführlicher in einem der folgenden Methoden zu beschränken:

- Einen Typ nicht generischen ist durch das Hinzufügen einer expliziten Typ-Anmerkung auf einen Wert oder einen Parameter zu beschränken.

- Wenn das Problem ein Konstrukt verallgemeinerbaren definieren Sie eine generische Funktion, wie z. B. eine funktionskomposition verwendet oder nicht vollständig Curry Funktionsargumente angewendet, versuchen Sie, Schreiben Sie die Funktion wie eine normale Funktionsdefinition.

- Wenn das Problem ein Ausdruck ist, der ist zu komplex für den generalisiert werden, stellen es in eine Funktion, durch das Hinzufügen eines zusätzlichen, nicht verwendeten Parameters.

- Fügen Sie explizite generische Typparameter hinzu. Diese Option wird nur selten verwendet.

- Die folgenden Codebeispiele veranschaulichen jedes dieser Szenarien.

Fall 1: Zu komplex. ein Ausdruck ist. In diesem Beispiel wird die Liste `counter` dient `int option ref`, aber es ist nicht definiert, wie ein einfacher, unveränderliche Wert.

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

Fall 2: Verwenden ein verallgemeinerbaren-Konstrukt, um eine generische Funktion zu definieren. In diesem Beispiel ist das Konstrukt verallgemeinerbaren, da hierbei partielle Anwendung von Funktionsargumenten.

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

Fall 3: Hinzufügen eines zusätzlichen, nicht verwendeten Parameters. Da dieses Ausdrucks nicht vorhanden sind, die für die Generalisierung einfach genug ist, gibt der Compiler den Wert Einschränkung Fehler auf.

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

Fall 4: Hinzufügen von Typparametern.

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

Im letzten Fall wird der Wert einer Typfunktion, die verwendet werden kann, um die Werte verschiedener Typen, z. B. wie folgt erstellen:

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a>Siehe auch

- [Typableitung](../type-inference.md)
- [Generika](index.md)
- [Statisch aufgelöste Typparameter](statically-resolved-type-parameters.md)
- [Einschränkungen](constraints.md)