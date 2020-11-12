---
title: Zitieren von Code
description: 'Erfahren Sie mehr über f #-Code Zitate, eine Sprachfunktion, die es Ihnen ermöglicht, f #-Code Ausdrücke Programm gesteuert zu generieren und zu bearbeiten.'
ms.date: 08/13/2020
ms.openlocfilehash: dc37fdbd6cd29e5ee94e5c0186dfe2bfeb666f32
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "94557193"
---
# <a name="code-quotations"></a>Code Zitate

Dieser Artikel beschreibt *Code Zitate* , eine Sprachfunktion, die es Ihnen ermöglicht, F #-Code Ausdrücke Programm gesteuert zu generieren und zu bearbeiten. Diese Funktion ermöglicht es Ihnen, eine abstrakte Syntax Struktur zu generieren, die F #-Code darstellt. Die abstrakte Syntax Struktur kann dann nach den Anforderungen Ihrer Anwendung durchlaufen und verarbeitet werden. Beispielsweise können Sie die-Struktur verwenden, um F #-Code zu generieren oder Code in einer anderen Sprache zu generieren.

## <a name="quoted-expressions"></a>Ausdrücke in Anführungszeichen

Ein *Ausdruck* in Anführungszeichen ist ein F #-Ausdruck in Ihrem Code, der so begrenzt ist, dass er nicht als Teil des Programms kompiliert wird, sondern in ein Objekt kompiliert wird, das einen F #-Ausdruck darstellt. Sie können einen Ausdruck in Anführungszeichen auf eine von zwei Arten markieren: entweder mit Typinformationen oder ohne Typinformationen. Wenn Sie Typinformationen einschließen möchten, verwenden Sie die Symbole `<@` und `@>` , um den Ausdruck in Anführungszeichen zu begrenzen. Wenn Sie keine Typinformationen benötigen, verwenden Sie die Symbole `<@@` und `@@>` . Der folgende Code zeigt typisierte und nicht typisierte Anführungszeichen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

Das Durchlaufen eines großen Ausdrucks Baums ist schneller, wenn Sie keine Typinformationen einschließen. Der resultierende Typ eines Ausdrucks, der mit den typisierten Symbolen angegeben wird `Expr<'T>` , ist, wobei der Typparameter den Typ des Ausdrucks hat, der vom Typrückschluss-Algorithmus des F #-Compilers bestimmt wird. Wenn Sie Code Anführungszeichen ohne Typinformationen verwenden, handelt es sich bei dem Typ des Ausdrucks in Anführungszeichen um den nicht generischen Typ [expr](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html). Sie können die [RAW](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr-1.html#Raw) -Eigenschaft für die typisierte Klasse aufzurufen `Expr` , um das nicht typisierte Objekt zu erhalten `Expr` .

Es gibt eine Reihe von statischen Methoden, die es Ihnen ermöglichen, F #-Ausdrucks Objekte Programm gesteuert in der-Klasse zu generieren, ohne Ausdrücke in Anführungszeichen zu `Expr` verwenden.

Beachten Sie, dass ein Code Zitat einen Complete-Ausdruck enthalten muss. Für eine `let` Bindung benötigen Sie z. b. sowohl die Definition des gebundenen namens als auch einen zusätzlichen Ausdruck, der die Bindung verwendet. In der ausführlichen Syntax ist dies ein Ausdruck, der auf das- `in` Schlüsselwort folgt. Auf der obersten Ebene eines Moduls ist dies nur der nächste Ausdruck im Modul, aber in einem Anführungszeichen ist es explizit erforderlich.

Daher ist der folgende Ausdruck ungültig.

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

Die folgenden Ausdrücke sind jedoch gültig.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

Zum Auswerten von f #-Anführungszeichen müssen Sie den [f #-Anführungs](https://github.com/fsprojects/FSharp.Quotations.Evaluator)Zeichen Wert verwenden. Sie bietet Unterstützung für das Auswerten und Ausführen von F #-Ausdrucks Objekten.

F #-Zitate behalten auch Informationen zur Typeinschränkung bei. Betrachten Sie das folgende Beispiel:

```fsharp
open FSharp.Linq.RuntimeHelpers

let eval q = LeafExpressionConverter.EvaluateQuotation q

let inline negate x = -x
// val inline negate: x: ^a ->  ^a when  ^a : (static member ( ~- ) :  ^a ->  ^a)

<@ negate 1.0 @>  |> eval
```

Die von der Funktion generierte Einschränkung `inline` wird im Code-QUUM beibehalten. Das `negate` Formular der Funktion kann nun ausgewertet werden.

## <a name="expr-type"></a>Expr-Typ

Eine Instanz des `Expr` Typs stellt einen F #-Ausdruck dar. Sowohl die generischen als auch die nicht generischen `Expr` Typen sind in der Dokumentation der F #-Bibliothek dokumentiert. Weitere Informationen finden Sie unter [FSharp. notiernamespace](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations.html) und [Noti. Expr-Klasse](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html).

## <a name="splicing-operators"></a>Splicing-Operatoren

Durch das Splicing können Sie literalcode-Anführungszeichen mit Ausdrücken kombinieren, die Sie Programm gesteuert erstellt haben, oder aus einem anderen Code Anführungszeichen. `%`Mit dem-Operator und dem- `%%` Operator können Sie ein F #-Ausdrucks Objekt zu einem Code Zitat hinzufügen. Sie verwenden den- `%` Operator, um ein typisiertes Ausdrucks Objekt in ein typisiertes Anführungszeichen einzufügen. Sie verwenden den- `%%` Operator, um ein nicht typisiertes Expression-Objekt in ein nicht typisiertes Anführungszeichen einzufügen. Beide Operatoren sind unäre Präfix Operatoren. Wenn daher `expr` ein nicht typisierter Ausdruck vom Typ ist `Expr` , ist der folgende Code gültig.

```fsharp
<@@ 1 + %%expr @@>
```

Wenn `expr` ein typisiertes Anführungszeichen vom Typ ist `Expr<int>` , ist der folgende Code gültig.

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Das folgende Beispiel veranschaulicht die Verwendung von Code Anführungszeichen, um F #-Code in einem Expression-Objekt zu platzieren und dann den f #-Code auszugeben, der den Ausdruck darstellt. Eine Funktion `println` ist definiert, die eine rekursive Funktion enthält `print` , die ein F #-Ausdrucks Objekt (vom Typ `Expr` ) in einem benutzerfreundlichen Format anzeigt. Es gibt mehrere aktive Muster in den Modulen " [FSharp. Noti. Patterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-patternsmodule.html) " und " [FSharp. Noti. DerivedPatterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html) ", die zum Analysieren von Ausdrucks Objekten verwendet werden können. In diesem Beispiel sind nicht alle möglichen Muster enthalten, die in einem F #-Ausdruck vorkommen können. Alle nicht erkannten Muster lösen eine Entsprechung für das Platzhalter Muster ( `_` ) aus und werden mithilfe der-Methode gerendert `ToString` , die auf dem- `Expr` Typ das aktive Muster kennt, das Sie dem Match-Ausdruck hinzufügen können.

### <a name="code"></a>Code

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a>Output

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Sie können auch die drei aktiven Muster im [ExprShape-Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html) verwenden, um Ausdrucks Baumstrukturen mit weniger aktiven Mustern zu durchlaufen. Diese aktiven Muster können nützlich sein, wenn Sie eine Struktur durchlaufen möchten, Sie jedoch nicht alle Informationen in den meisten Knoten benötigen. Wenn Sie diese Muster verwenden, entspricht jeder F #-Ausdruck einem der folgenden drei Muster: `ShapeVar` Wenn der Ausdruck eine Variable ist, `ShapeLambda` der Ausdruck ein Lambda-Ausdruck ist oder `ShapeCombination` Wenn der Ausdruck etwas anderes ist. Wenn Sie eine Ausdrucks Baumstruktur durchlaufen, indem Sie die aktiven Muster wie im vorherigen Codebeispiel verwenden, müssen Sie viele weitere Muster verwenden, um alle möglichen F #-Ausdrucks Typen zu verarbeiten, und Ihr Code ist komplexer. Weitere Informationen finden Sie unter [ExprShape. shapevar&#124;aktives Muster shapelambda&#124;shapekombination](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html#(%20|ShapeVar|ShapeLambda|ShapeCombination|%20)).

Das folgende Codebeispiel kann als Grundlage für komplexere Traversale verwendet werden. In diesem Code wird eine Ausdrucks Baumstruktur für einen Ausdruck erstellt, der einen Funktions aufzurufen,, umfasst `add` . Mit dem aktiven [specificcall](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html#(%20|SpecificCall|_|%20)) -Muster wird ein beliebiger Aufrufe von `add` in der Ausdrucks Baumstruktur erkannt. Dieses aktive Muster weist die Argumente des Aufrufes dem- `exprList` Wert zu. In diesem Fall gibt es nur zwei, sodass diese abgerufen werden und die Funktion rekursiv für die Argumente aufgerufen wird. Die Ergebnisse werden in ein Code Zitat eingefügt, das einen-aufrufbefehl `mul` mithilfe des Splice-Operators ( `%%` ) darstellt. Die `println` Funktion aus dem vorherigen Beispiel wird verwendet, um die Ergebnisse anzuzeigen.

Der Code in den anderen aktiven Muster Verzweigungen generiert einfach dieselbe Ausdrucks Baumstruktur, sodass die einzige Änderung im resultierenden Ausdruck die Änderung von in ist `add` `mul` .

### <a name="code"></a>Code

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a>Output

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
