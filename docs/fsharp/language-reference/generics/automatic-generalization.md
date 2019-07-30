---
title: Automatische Verallgemeinerung
description: Erfahren Sie, wie F# automatisch die Argumente und Funktionstypen verallgemeinert, damit sie mit mehreren Typen nach Möglichkeit funktionieren.
ms.date: 05/16/2016
ms.openlocfilehash: 501749a190d9770cbcd9848e3d528cba32fe6762
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630628"
---
# <a name="automatic-generalization"></a>Automatische Verallgemeinerung

F#verwendet den Typrückschluss, um die Typen von Funktionen und Ausdrücken auszuwerten. In diesem Thema wird beschrieben, wie F# automatisch die Argumente und Funktionstypen verallgemeinert, damit sie mit mehreren Arten funktionieren, wenn dies möglich ist.

## <a name="automatic-generalization"></a>Automatische Verallgemeinerung

Wenn F# der Compiler einen Typrückschluss für eine Funktion ausführt, bestimmt er, ob ein bestimmter Parameter generisch sein kann. Der Compiler überprüft jeden Parameter und bestimmt, ob die Funktion eine Abhängigkeit vom jeweiligen Typ dieses Parameters aufweist. Wenn dies nicht der Fall ist, wird der Typ als generisch abgeleitet.

Im folgenden Codebeispiel wird eine Funktion veranschaulicht, die der Compiler als generisch herleitet.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet101.fs)]

Der Typ wird als abgeleitet `'a -> 'a -> 'a`.

Der-Typ gibt an, dass es sich hierbei um eine Funktion handelt, die zwei Argumente desselben unbekannten Typs annimmt und einen Wert desselben Typs zurückgibt. Einer der Gründe dafür, dass die vorherige Funktion generisch sein kann, ist, dass der größer`>`-als-Operator () selbst generisch ist. Der größer-als-Operator hat die `'a -> 'a -> bool`Signatur. Nicht alle Operatoren sind generisch, und wenn der Code in einer Funktion einen Parametertyp mit einer nicht generischen Funktion oder einem nicht generischen Operator verwendet, kann dieser Parametertyp nicht generalisiert werden.

Da `max` generisch ist, kann es mit Typen `int`wie, `float`usw. verwendet werden, wie in den folgenden Beispielen gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet102.fs)]

Allerdings müssen die beiden Argumente denselben Typ aufweisen. Die Signatur ist `'a -> 'a -> 'a`, nicht `'a -> 'b -> 'a`. Daher erzeugt der folgende Code einen Fehler, da die Typen nicht identisch sind.

```fsharp
// Error: type mismatch.
let biggestIntFloat = max 2.0 3
```

Die `max` -Funktion funktioniert auch mit jedem Typ, der den größer-als-Operator unterstützt. Daher können Sie Sie auch für eine Zeichenfolge verwenden, wie im folgenden Code gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet104.fs)]

## <a name="value-restriction"></a>Wert Einschränkung

Der Compiler führt die automatische Generalisierung nur für vollständige Funktionsdefinitionen mit expliziten Argumenten und für einfache unveränderliche Werte durch.

Dies bedeutet, dass der Compiler einen Fehler ausgibt, wenn Sie versuchen, Code zu kompilieren, der nicht ausreichend auf einen bestimmten Typ beschränkt ist, aber auch nicht verallgemeinerbar ist. Die Fehlermeldung für dieses Problem bezieht sich auf diese Einschränkung bei der automatischen Generalisierung von Werten als *Wert Einschränkung*.

In der Regel tritt der Wert Einschränkungs Fehler auf, wenn ein Konstrukt generisch sein soll, der Compiler jedoch nicht über ausreichende Informationen verfügt, um ihn zu generalisieren, oder wenn Sie versehentlich ausreichende Typinformationen in einem nicht generischen Konstrukt weglassen. Die Lösung für den Wert Einschränkungs Fehler besteht darin, ausführlichere Informationen bereitzustellen, um das Typrückschluss Problem mit einer der folgenden Methoden vollständig einzuschränken:

- Beschränken Sie einen Typ auf einen nicht generischen Typ, indem Sie einem Wert oder Parameter eine explizite Typanmerkung hinzufügen.

- Wenn das Problem ein nicht generisch erbares Konstrukt zum Definieren einer generischen Funktion verwendet, wie z. b. eine Funktions Komposition oder nicht vollständig angewendete currried-Funktionsargumente, versuchen Sie, die Funktion als normale Funktionsdefinition umzuschreiben.

- Wenn das Problem ein Ausdruck ist, der zu komplex ist, um verallgemeinert zu werden, nehmen Sie ihn durch Hinzufügen eines zusätzlichen, nicht verwendeten Parameters in eine Funktion auf.

- Fügen Sie explizite generische Typparameter hinzu. Diese Option wird nur selten verwendet.

- Die folgenden Codebeispiele veranschaulichen die einzelnen Szenarien.

Fall 1: Der Ausdruck ist zu komplex. In diesem Beispiel ist die Liste `counter` vorgesehen `int option ref`, aber Sie ist nicht als einfacher unveränderlicher Wert definiert.

```fsharp
let counter = ref None
// Adding a type annotation fixes the problem:
let counter : int option ref = ref None
```

Fall 2: Verwenden eines nicht verallgemeinerbaren Konstrukts zum Definieren einer generischen Funktion. In diesem Beispiel ist das Konstrukt nicht verallgemeinerbar, da es eine partielle Anwendung von Funktions Argumenten umfasst.

```fsharp
let maxhash = max << hash
// The following is acceptable because the argument for maxhash is explicit:
let maxhash obj = (max << hash) obj
```

Fall 3: Hinzufügen eines zusätzlichen, nicht verwendeten Parameters. Da dieser Ausdruck für die Generalisierung nicht einfach genug ist, gibt der Compiler den Wert Einschränkungs Fehler aus.

```fsharp
let emptyList10 = Array.create 10 []
// Adding an extra (unused) parameter makes it a function, which is generalizable.
let emptyList10 () = Array.create 10 []
```

Fall 4: Typparameter werden hinzugefügt.

```fsharp
let arrayOf10Lists = Array.create 10 []
// Adding a type parameter and type annotation lets you write a generic value.
let arrayOf10Lists<'T> = Array.create 10 ([]:'T list)
```

Im letzten Fall wird der Wert zu einer Typfunktion, die verwendet werden kann, um Werte von vielen verschiedenen Typen zu erstellen, z. b. wie folgt:

```fsharp
let intLists = arrayOf10Lists<int>
let floatLists = arrayOf10Lists<float>
```

## <a name="see-also"></a>Siehe auch

- [Typableitung](../type-inference.md)
- [Generika](index.md)
- [Statisch aufgelöste Typparameter](statically-resolved-type-parameters.md)
- [Einschränkungen](constraints.md)
