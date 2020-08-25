---
title: let-Bindungen
description: 'Erfahren Sie, wie Sie eine F #-"Let"-Bindung verwenden, die einen Bezeichner einem Wert oder einer Funktion zuordnet.'
ms.date: 05/16/2016
ms.openlocfilehash: 6f2396f480c5e6c631d0022f4732419ee5b07db6
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812223"
---
# <a name="let-bindings"></a>let-Bindungen

Eine *Bindung* ordnet einen Bezeichner einem Wert oder einer Funktion zu. Verwenden Sie das- `let` Schlüsselwort, um einen Namen an einen Wert oder eine Funktion zu binden.

## <a name="syntax"></a>Syntax

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a>Hinweise

Das `let` Schlüsselwort wird in Bindungs Ausdrücken verwendet, um Werte oder Funktions Werte für einen oder mehrere Namen zu definieren. In der einfachsten Form des `let` Ausdrucks wird ein Name wie folgt an einen einfachen Wert gebunden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

Wenn Sie den Ausdruck durch eine neue Zeile vom Bezeichner trennen, müssen Sie die einzelnen Zeilen des Ausdrucks einziehen, wie im folgenden Code.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

Anstelle eines Namens kann ein Muster, das Namen enthält, z. b. ein Tupel angegeben werden, wie im folgenden Code dargestellt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

Der *Text Ausdruck* ist der Ausdruck, in dem die Namen verwendet werden. Der Textkörper Ausdruck wird in einer eigenen Zeile angezeigt, um genau mit dem ersten Zeichen im- `let` Schlüsselwort zu versehen:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

Eine `let` Bindung kann auf Modulebene, in der Definition eines Klassen Typs oder in lokalen Bereichen (z. b. in einer Funktionsdefinition) vorkommen. Eine `let` Bindung auf der obersten Ebene eines Moduls oder eines Klassen Typs muss keinen Text Ausdruck aufweisen, aber auf anderen Bereichs Ebenen ist der Text Ausdruck erforderlich. Die gebundenen Namen können nach dem Zeitpunkt der Definition verwendet werden, aber nicht an einem beliebigen Punkt `let` , bevor die Bindung angezeigt wird. Dies wird im folgenden Code veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a>Funktions Bindungen

Funktions Bindungen folgen den Regeln für Wert Bindungen, außer dass Funktions Bindungen den Funktionsnamen und die Parameter enthalten, wie im folgenden Code gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

Im Allgemeinen sind Parameter Muster, z. b. ein tupelmuster:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

Ein `let` Bindungs Ausdruck ergibt den Wert des letzten Ausdrucks. Daher wird im folgenden Codebeispiel der Wert von `result` aus berechnet, der ergibt `100 * function3 (1, 2)` `300` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

Weitere Informationen finden Sie unter [Funktionen](index.md).

## <a name="type-annotations"></a>Typanmerkungen

Sie können Typen für Parameter angeben, indem Sie einen Doppelpunkt (:) gefolgt von einem Typnamen, der in Klammern eingeschlossen ist. Sie können auch den Typ des Rückgabewerts angeben, indem Sie den Doppelpunkt anfügen und nach dem letzten Parameter eingeben. Die vollständigen Typanmerkungen für `function1` , mit ganzen Zahlen als Parametertypen, lauten wie folgt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

Wenn keine expliziten Typparameter vorhanden sind, wird der Typrückschluss verwendet, um die Typen von Parametern von Funktionen zu bestimmen. Dies kann den automatischen generalisieren des Typs eines Parameters einschließen, der generisch ist.

Weitere Informationen finden Sie unter [Automatische Generalisierung](../generics/automatic-generalization.md) und [Typrückschluss](../type-inference.md).

## <a name="let-bindings-in-classes"></a>let-Bindungen in Klassen

Eine `let` Bindung kann in einem Klassentyp, jedoch nicht in einer Struktur oder einem Daten Satz Typen vorkommen. Damit eine Let-Bindung in einem Klassentyp verwendet werden kann, muss die Klasse über einen primären Konstruktor verfügen. Konstruktorparameter müssen nach dem Typnamen in der Klassendefinition angezeigt werden. Eine `let` Bindung in einem Klassentyp definiert private Felder und Member für diesen Klassentyp und `do` bildet in Verbindung mit Bindungen im Typ den Code für den primären Konstruktor für den Typ. Die folgenden Codebeispiele zeigen eine `MyClass` -Klasse mit privaten Feldern `field1` und `field2` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

Die Bereiche von `field1` und `field2` sind auf den Typ beschränkt, in dem Sie deklariert werden. Weitere Informationen finden Sie unter [ `let` Bindungen in Klassen](../members/let-bindings-in-classes.md) und [Klassen](../classes.md).

## <a name="type-parameters-in-let-bindings"></a>Typparameter in let-Bindungen

Eine `let` Bindung auf Modulebene, in einem Typ oder in einem Berechnungs Ausdruck kann explizite Typparameter aufweisen. Eine Let-Bindung in einem Ausdruck, z. b. innerhalb einer Funktionsdefinition, darf keine Typparameter aufweisen. Weitere Informationen finden Sie unter [Generics](../generics/index.md).

## <a name="attributes-on-let-bindings"></a>Attribute bei let-Bindungen

Attribute können auf Bindungen auf oberster Ebene `let` in einem Modul angewendet werden, wie im folgenden Code gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a>Bereich und Barrierefreiheit von let-Bindungen

Der Gültigkeitsbereich einer mit einer Let-Bindung deklarierten Entität ist auf den Teil des enthaltenden Bereichs beschränkt (z. b. eine Funktion, ein Modul, eine Datei oder eine Klasse), nachdem die Bindung angezeigt wurde. Daher kann man sagen, dass eine Let-Bindung einen Namen in einen Bereich einführt. In einem Modul ist ein Let-gebundener Wert oder eine Funktion für Clients eines Moduls zugänglich, solange auf das Modul zugegriffen werden kann, da die let-Bindungen in einem Modul in öffentliche Funktionen des Moduls kompiliert werden. Im Gegensatz dazu sind Bindungen in einer Klasse für die Klasse privat.

Funktionen in Modulen müssen normalerweise durch den Namen des Moduls qualifiziert werden, wenn Sie vom Client Code verwendet werden. Wenn ein Modul z. b `Module1` . über eine Funktion verfügt `function1` , geben die Benutzer an, dass auf `Module1.function1` die Funktion verwiesen werden soll.

Benutzer eines Moduls können eine Import Deklaration verwenden, um die Funktionen innerhalb dieses Moduls zur Verwendung verfügbar zu machen, ohne dass der Modulname qualifiziert ist. Im soeben erwähnten Beispiel können Benutzer des Moduls in diesem Fall das Modul öffnen, indem Sie die Import Deklaration öffnen `Module1` und anschließend direkt auf verweisen `function1` .

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

Einige Module verfügen über das-Attribut "Requirements [qualifiedaccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html)", was bedeutet, dass die Funktionen, die Sie verfügbar machen, mit dem Namen des Moduls qualifiziert werden müssen. Das F #-Listen Modul verfügt beispielsweise über dieses Attribut.

Weitere Informationen zu Modulen und zur Zugriffs Steuerung finden Sie unter [Module](../modules.md) und [Access Control](../access-control.md).

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)
- [`let` Bindungen in Klassen](../members/let-bindings-in-classes.md)
