---
title: let-Bindungen
description: Erfahren Sie, wie Sie mit einem F# "let" Bindung, die einen Bezeichner mit einem Wert oder einer Funktion verknüpft.
ms.date: 05/16/2016
ms.openlocfilehash: 45de82acf6f4423698cd8037266968e023f40dcb
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612672"
---
# <a name="let-bindings"></a>let-Bindungen

Ein *Bindung* ordnet einen Wert oder die Funktion einen Bezeichner. Sie verwenden die `let` Schlüsselwort, um einen Namen auf einen Wert oder die Funktion zu binden.

## <a name="syntax"></a>Syntax

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a>Hinweise

Die `let` -Schlüsselwort wird verwendet, in Bindungsausdrücken Werte oder Werte für einen oder mehrere Namen von Funktionen zu definieren. Die einfachste Form der `let` Ausdruck bindet einen Namen wie folgt auf einen einfachen Wert.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

Wenn Sie den Ausdruck aus einem Bezeichner mit einer neuen Zeile trennen, müssen Sie jede Zeile des Ausdrucks, wie im folgenden Code eingerückt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

Statt einfach einen Namen, ein Muster, das Namen angegeben werden, z. B. eines Tupels, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

Die *Body-Ausdruck* ist der Ausdruck, der in der die Namen verwendet werden. Der Body-Ausdruck wird in einer eigenen Zeile, Einzug genau mit dem ersten Zeichen in der `let` Schlüsselwort:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

Ein `let` -Bindung kann auf Modulebene, in der Definition eines Klassentyps oder in lokalen Bereichen, z. B. in einer Funktionsdefinition. Ein `let` Bindung auf der obersten Ebene in einem Modul oder in einen Klassentyp muss nicht Body-Ausdruck verfügen, aber auf andere Bereichsebenen, Text-Ausdruck ist erforderlich. Die gebundenen Namen verwendet werden, nach dem Zeitpunkt der Definition, aber nicht an einem beliebigen Punkt vor der `let` Bindung angezeigt wird, wie im folgenden Code dargestellt wird.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a>Funktionsbindungen

Funktionsbindungen folgen den Regeln für Wert Bindungen an, mit dem Unterschied, dass funktionsbindungen den Namen der Funktion und die Parameter enthalten, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

Parameter sind im allgemeinen Muster wie z.B. einem Tupelmuster:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

Ein `let` Bindungsausdruck ergibt den Wert des letzten Ausdrucks. Aus diesem Grund in der folgenden Codebeispiel wird der Wert des `result` wird berechnet aus `100 * function3 (1, 2)`, ergibt die `300`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

Weitere Informationen finden Sie unter [Funktionen](index.md).

## <a name="type-annotations"></a>Typanmerkungen

Sie können die Typen für Parameter angeben, durch einen Doppelpunkt (:) gefolgt von einem Typnamen alle Elemente in Klammern einschließen. Sie können auch den Typ des Rückgabewerts angeben, durch den Doppelpunkt und den Typ nach dem letzten Parameter anfügen. Die vollständige typanmerkungen für `function1`, mit ganzen Zahlen als Parametertypen, würde wie folgt lauten.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

Wenn keine expliziten Typ-Parameter vorhanden sind, wird den Typrückschluss verwendet, um zu bestimmen, die Typen der Parameter von Funktionen. Dies kann beinhalten, automatisch eine Generalisierung des Typs eines Parameters generisch sein.

Weitere Informationen finden Sie unter [automatische Verallgemeinerung](../generics/automatic-generalization.md) und [Typrückschluss](../type-inference.md).

## <a name="let-bindings-in-classes"></a>let-Bindungen in Klassen

Ein `let` -Bindung kann in einen Klassentyp jedoch nicht in einer Struktur oder einem Datensatztyp. Um eine Let-Bindung in einen Klassentyp zu verwenden, muss die Klasse über einen primären Konstruktor verfügen. Konstruktorparameter müssen nach dem Namen des Typs in der Klassendefinition angezeigt werden. Ein `let` Bindung in einen Klassentyp definiert wird, private Felder und Elemente für dieses Klassentyps und zusammen mit `do` Bindungen in den Typ, bildet den Code für den primären Konstruktor für den Typ. Die folgenden Codebeispiele zeigen eine Klasse `MyClass` private Felder `field1` und `field2`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

Die Bereiche der `field1` und `field2` sind beschränkt auf den Typ, in dem sie deklariert werden. Weitere Informationen finden Sie unter [ `let` Bindungen in Klassen](../members/let-bindings-in-classes.md) und [Klassen](../classes.md).

## <a name="type-parameters-in-let-bindings"></a>Typparameter in let-Bindungen

Ein `let` Bindung auf Modulebene, in einen Typ oder in einem Berechnungsausdruck kann explizite Typparameter haben. Eine Let-Bindung in einem Ausdruck, z. B. innerhalb einer Funktionsdefinition, dürfen keine Typparameter aufweisen. Weitere Informationen finden Sie unter [Generika](../generics/index.md).

## <a name="attributes-on-let-bindings"></a>Attribute in let-Bindungen

Attribute können auf der obersten Ebene angewendet werden `let` Bindungen in einem Modul, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a>Bereich und der Zugriff von Let-Bindungen

Der Bereich einer Entität, die mit einer Let-Bindung deklariert ist beschränkt, der Teil des enthaltenden Bereich (z. B. eine Funktion, Modul, Datei oder Klasse), wenn die Bindung angezeigt wird. Aus diesem Grund kann es gilt, dass eine Let-Bindung über einen Namen in einem Bereich einführt. In einem Modul kann die einer Let gebundenen Wert oder eine Funktion für die Clients eines Moduls zugegriffen werden, solange das Modul zugegriffen werden kann, ist, da die Let-Bindungen in einem Modul in öffentliche Funktionen des Moduls kompiliert werden. Im Gegensatz dazu sind die Let-Bindungen in einer Klasse auf die Klasse privat.

Funktionen in Modulen müssen in der Regel durch den Namen des Moduls, die bei der Verwendung von Clientcode qualifiziert werden. Angenommen, ein Modul `Module1` verfügt über eine Funktion `function1`, Benutzer geben `Module1.function1` , an die Funktion zu verweisen.

Eine Importdeklaration können Benutzer von einem Modul um die Funktionen innerhalb dieses Moduls verfügbar zu machen, ohne die, die durch den Namen des Moduls gekennzeichnet wird. Im eben erwähnten Beispiel Benutzer des Moduls können in diesem Fall öffnen Sie das Modul mithilfe der Import-Deklaration Open `Module1` und verweisen Sie anschließend auf `function1` direkt.

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

Einige Module verfügen über das Attribut [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), was bedeutet, dass die Funktionen, die sie verfügbar machen, die mit dem Namen des Moduls gekennzeichnet sein müssen. Z. B. die F# List-Modul hat dieses Attribut.

Weitere Informationen zu Modulen und Access Control, finden Sie unter [Module](../modules.md) und [Zugriffssteuerung](../access-control.md).

## <a name="see-also"></a>Siehe auch

- [Funktionen](index.md)
- [`let`-Bindungen in Klassen](../members/let-bindings-in-classes.md)