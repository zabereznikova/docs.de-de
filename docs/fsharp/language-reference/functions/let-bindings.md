---
title: let-Bindungen (F#)
description: Informationen Sie zum Verwenden einer F#-"-Bindung, die einen Bezeichner mit einem Wert oder die Funktion ordnet let".
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 2abc4e05f9f2977501f01f745062e2e7cd611f68
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="let-bindings"></a>let-Bindungen

Ein *Bindung* ordnet einen Bezeichner mit einem Wert oder einer Funktion. Sie verwenden die `let` Schlüsselwort, einen Namen auf einen Wert oder eine Funktion zu binden.

## <a name="syntax"></a>Syntax

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a>Hinweise

Die `let` -Schlüsselwort wird verwendet, bei der Bindung Ausdrücke, um Werte oder Funktionswerte für einen oder mehrere Namen definieren. Die einfachste Form der `let` Ausdruck bindet einen Namen wie folgt auf einen einfachen Wert.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

Wenn Sie den Ausdruck aus einem Bezeichner mit einer neuen Zeile trennen, muss jede Zeile des Ausdrucks, wie im folgenden Code einrücken

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

Anstatt nur einen Namen ein Muster, das Namen enthält, kann angegeben werden, z. B. eines Tupels, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

Die *Text-Ausdruck* ist der Ausdruck in der die Namen verwendet werden. Text-Ausdruck wird in einer eigenen Zeile, Einzug genau mit dem ersten Zeichen in der `let` Schlüsselwort:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

Ein `let` -Bindung kann auf Modulebene, in der Definition eines Klassentyps oder in lokalen Gültigkeitsbereichen, z. B. in einer Funktionsdefinition. Ein `let` auf der obersten Ebene in einem Modul oder in einen Klassentyp Bindung muss nicht Body-Ausdruck verfügen, jedoch auf andere Bereichsebenen Textausdruck erforderlich ist. Die gebundenen Namen verwendet werden, nach dem Zeitpunkt der Definition, jedoch nicht zu einem beliebigen Zeitpunkt vor der `let` Bindung angezeigt wird, wie im folgenden Code veranschaulicht wird.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]
    
## <a name="function-bindings"></a>Funktionsbindungen

Funktionsbindungen Regeln den für Wert Bindungen, mit dem Unterschied, dass funktionsbindungen den Funktionsnamen und die Parameter enthalten, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

Parameter sind im allgemeinen Mustern, z. B. ein Tupelmuster:

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

Ein `let` binden Ausdruck ergibt den Wert des letzten Ausdrucks. Aus diesem Grund in die im folgenden Codebeispiel wird der Wert der `result` errechnet sich aus `100 * function3 (1, 2)`, ergibt die `300`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

Weitere Informationen finden Sie unter [Funktionen](index.md).

## <a name="type-annotations"></a>Typanmerkungen

Sie können Typen für Parameter angeben, durch einen Doppelpunkt (:) gefolgt vom Typnamen, alle Elemente in Klammern einschließen. Sie können auch den Typ des Rückgabewerts angeben, durch den Doppelpunkt und den Typ nach dem letzten Parameter anfügen. Die vollständige typanmerkungen für `function1`, mit ganzen Zahlen als Parametertypen, wäre wie folgt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

Wenn keine explizite Typparameter vorhanden sind, wird Typrückschluss verwendet, um die Typen der Parameter von Funktionen zu ermitteln. Dazu gehören das automatisch durch das Verallgemeinern von den Typ eines Parameters generisch sein.

Weitere Informationen finden Sie unter [automatische Verallgemeinerung](../generics/automatic-generalization.md) und [Typrückschluss](../type-inference.md).

## <a name="let-bindings-in-classes"></a>let-Bindungen in Klassen

Ein `let` -Bindung kann in einem Klassentyp sein, aber nicht in eine Struktur oder ein Datensatztyp. Um eine Let-Bindung in einem Klassentyp zu verwenden, muss die Klasse einen primären Konstruktor verfügen. Konstruktorparameter müssen nach dem Namen des Typs in der Klassendefinition angezeigt werden. Ein `let` Bindung in einen Klassentyp definiert private Felder und Member für diesen Klassentyp und zusammen mit `do` Bindungen in den Typ bildet den Code für den primären Konstruktor für den Typ. Die folgenden Codebeispiele zeigen eine Klasse `MyClass` private Felder `field1` und `field2`.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

Die Bereiche des `field1` und `field2` sind beschränkt auf den Typ, in dem sie deklariert werden. Weitere Informationen finden Sie unter [ `let` Bindungen in Klassen](../members/let-bindings-in-classes.md) und [Klassen](../classes.md).

## <a name="type-parameters-in-let-bindings"></a>Typparameter in let-Bindungen

Ein `let` Bindung auf Modulebene, in einen Typ oder einen Ausdruck für die Berechnung kann explizite Typparameter verfügen. Eine Let-Bindung in einem Ausdruck, z. B. innerhalb einer Funktionsdefinition dürfen keine Typparameter aufweisen. Weitere Informationen finden Sie unter [Generika](../generics/index.md).

## <a name="attributes-on-let-bindings"></a>Attribute auf let-Bindungen

Attribute können auf der obersten Ebene angewendet werden `let` Bindungen in einem Modul, wie im folgenden Code gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]
    
## <a name="scope-and-accessibility-of-let-bindings"></a>Bereich und der Zugriff von Let-Bindungen

Der Bereich einer Entität mit einem Let-Bindung deklariert ist beschränkt auf den Bereich des enthaltenden Bereich (z. B. eine Funktion, Modul, Datei oder Klasse), nachdem die Bindung angezeigt wird. Aus diesem Grund kann gesagt werden, dass eine Bindung ermöglichen einen Namen in den Gültigkeitsbereich einer führt. In einem Modul ist die einem Let-Grenzwert oder Funktion zugegriffen werden kann, um Clients eines Moduls, solange das Modul zugegriffen werden kann, ist, da der öffentliche Funktionen des Moduls der Let-Bindungen in einem Modul kompiliert werden. Im Gegensatz dazu sind Let-Bindungen in einer Klasse für die Klasse privat.

Funktionen in Modulen müssen in der Regel wird durch den Namen des Moduls bei Verwendung durch Clientcode gekennzeichnet werden. Angenommen, ein Modul `Module1` verfügt über eine Funktion `function1`, Benutzer angeben würden `Module1.function1` zum Verweisen auf die Funktion.

Benutzer eines Moduls können eine Importdeklaration verwenden, um die Funktionen in diesem Modul für die Verwendung verfügbar zu machen, ohne wird durch den Namen des Moduls gekennzeichnet. Im Beispiel aufgeführten Benutzer des Moduls können in diesem Fall öffnen Sie das Modul mithilfe der Import-Deklaration öffnen `Module1` und danach auf verweisen `function1` direkt.

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

Einige Module verfügen über Attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), was bedeutet, dass die Funktionen, die sie verfügbar machen, die mit dem Namen des Moduls gekennzeichnet sein müssen. Der F#-List-Modul hat z. B. dieses Attribut.

Weitere Informationen zu Modulen und Steuerung des Zugriffs, finden Sie unter [Module](../modules.md) und [Access Control](../access-control.md).

## <a name="see-also"></a>Siehe auch

[Funktionen](index.md)

[`let`-Bindungen in Klassen](../members/let-bindings-in-classes.md)
