---
title: Operatorüberladung
description: 'Erfahren Sie, wie Sie arithmetische Operatoren in einer Klasse oder einem Daten Satz Typ und auf globaler Ebene in F # überladen.'
ms.date: 08/15/2020
ms.openlocfilehash: fb86ceb95101fcc1f157ec9ba17a9d8145b11a91
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557580"
---
# <a name="operator-overloading"></a>Operatorüberladung

In diesem Thema wird beschrieben, wie arithmetische Operatoren in einer Klasse oder einem Datensatztyp sowie auf globaler Ebene überladen werden.

## <a name="syntax"></a>Syntax

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a>Bemerkungen

In der vorherigen Syntax ist das *Operator-Symbol* eine von `+` , `-` , `*` , `/` , `=` usw. Der *Parameter-List* gibt die Operanden in der Reihenfolge an, in der Sie in der üblichen Syntax für diesen Operator angezeigt werden. Der *Methoden Text* erstellt den resultierenden Wert.

Operatorüberladungen müssen statisch sein. Operator Überladungen für unäre Operatoren, wie z. b. `+` und `-` , müssen eine Tilde ( `~` ) im *Operator-Symbol* verwenden, um anzugeben, dass der Operator ein unärer Operator und kein binärer Operator ist, wie in der folgenden Deklaration gezeigt.

```fsharp
static member (~-) (v : Vector)
```

Im folgenden Code wird eine Vektorklasse veranschaulicht, die über nur zwei Operatoren verfügt, einer für unäres Minus und einer für Multiplikation mit einem Skalar. In dem Beispiel werden zwei Überladungen für skalare Multiplikation benötigt, da der Operator unabhängig von der Reihenfolge verwendet werden können muss, in der der Vektor und der Skalar angezeigt werden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a>Erstellen von neuen Operatoren

Sie können alle Standardoperatoren überladen, Sie können jedoch auch aus Sequenzen bestimmter Zeichen neue Operatoren erstellen. Zulässige Operator Zeichen sind `!` , `%` , `&` , `*` , `+` , `-` , `.` , `/` , `<` , `=` , `>` , `?` , `@` , `^` , `|` und `~` . Das Zeichen `~` hat eine besondere Bedeutung, da mit ihm ein Operator als unärer Operator festgelegt wird. Es kann nicht in einer Operatorzeichenfolge verwendet werden. Nicht alle Operatoren können unär gemacht werden.

Rangfolge und Assoziativität des Operators hängen von der verwendeten Zeichenfolge ab. Die Assoziativität kann entweder von links nach rechts oder von rechts nach links sein. Sie wird immer verwendet, wenn Operatoren der gleichen Rangfolge nacheinander ohne Klammern angezeigt werden.

Das Operatorzeichen `.` wirkt sich nicht auf die Rangfolge aus. Wenn Sie eine eigene Version von Multiplikation definieren möchten, die die gleiche Rangfolge und Assoziativität wie die übliche Multiplikation aufweist, können Sie daher z. B. den Operator `.*` erstellen.

Nur die Operatoren `?` und `?<-` können mit beginnen `?` .

Eine Tabelle, in der die Rangfolge aller Operatoren in F # angezeigt wird, finden Sie unter [Symbol-und Operator Verweis](./symbol-and-operator-reference/index.md).

## <a name="overloaded-operator-names"></a>Namen von überladenen Operatoren

Wenn der F#-Compiler einen Operatorausdruck kompiliert, wird eine Methode mit einem vom Compiler generierten Namen für den Operator erzeugt. Dies ist der Name, der in MSIL (Microsoft Intermediate Language) sowie in IntelliSense und bei Reflektion für die Methode angezeigt wird. Sie müssen diese Namen normalerweise nicht in F#-Code verwenden.

In der folgenden Tabelle werden die Standardoperatoren und die entsprechenden generierten Namen dargestellt.

|Operator|Generierter Name|
|--------|--------------|
|`[]`|`op_Nil`|
|`::`|`op_Cons`|
|`+`|`op_Addition`|
|`-`|`op_Subtraction`|
|`*`|`op_Multiply`|
|`/`|`op_Division`|
|`@`|`op_Append`|
|`^`|`op_Concatenate`|
|`%`|`op_Modulus`|
|`&&&`|`op_BitwiseAnd`|
|<code>&#124;&#124;&#124;</code>|`op_BitwiseOr`|
|`^^^`|`op_ExclusiveOr`|
|`<<<`|`op_LeftShift`|
|`~~~`|`op_LogicalNot`|
|`>>>`|`op_RightShift`|
|`~+`|`op_UnaryPlus`|
|`~-`|`op_UnaryNegation`|
|`=`|`op_Equality`|
|`<=`|`op_LessThanOrEqual`|
|`>=`|`op_GreaterThanOrEqual`|
|`<`|`op_LessThan`|
|`>`|`op_GreaterThan`|
|`?`|`op_Dynamic`|
|`?<-`|`op_DynamicAssignment`|
|<code>&#124;></code>|`op_PipeRight`|
|<code><&#124;</code>|`op_PipeLeft`|
|`!`|`op_Dereference`|
|`>>`|`op_ComposeRight`|
|`<<`|`op_ComposeLeft`|
|`<@ @>`|`op_Quotation`|
|`<@@ @@>`|`op_QuotationUntyped`|
|`+=`|`op_AdditionAssignment`|
|`-=`|`op_SubtractionAssignment`|
|`*=`|`op_MultiplyAssignment`|
|`/=`|`op_DivisionAssignment`|
|`..`|`op_Range`|
|`.. ..`|`op_RangeStep`|

Beachten Sie, dass der- `not` Operator in F # nicht ausgibt, `op_Inequality` weil es sich nicht um einen symbolischen Operator handelt. Diese Funktion gibt Il aus, die einen booleschen Ausdruck negiert.

Andere, hier nicht aufgeführte Kombinationen von Operatorzeichen können als Operatoren verwendet werden, und ihre Namen werden durch das Verketten von Namen für die einzelnen Zeichen in der folgenden Tabelle gebildet. Beispiel: +!  wird `op_PlusBang`.

|Operatorzeichen|Name|
|------------------|----|
|`>`|`Greater`|
|`<`|`Less`|
|`+`|`Plus`|
|`-`|`Minus`|
|`*`|`Multiply`|
|`/`|`Divide`|
|`=`|`Equals`|
|`~`|`Twiddle`|
|`%`|`Percent`|
|`.`|`Dot`|
|`&`|`Amp`|
|<code>&#124;</code>|`Bar`|
|`@`|`At`|
|`^`|`Hat`|
|`!`|`Bang`|
|`?`|`Qmark`|
|`(`|`LParen`|
|`,`|`Comma`|
|`)`|`RParen`|
|`[`|`LBrack`|
|`]`|`RBrack`|

## <a name="prefix-and-infix-operators"></a>Präfix- und Infixoperatoren

Es wird erwartet, dass *Präfix* Operatoren vor einem Operanden oder Operanden platziert werden, ähnlich wie eine Funktion. Es wird erwartet, dass *Infix* -Operatoren zwischen den beiden Operanden platziert werden.

Nur bestimmte Operatoren können als Präfixoperatoren verwendet werden. Einige Operatoren sind immer Präfixoperatoren, andere können Infix- oder Präfixoperatoren sein und der Rest ist immer Infixoperatoren. Operatoren, die mit `!` beginnen, außer `!=` und der Operator `~` oder wiederholte Sequenzen von `~`, sind immer Präfixoperatoren. Die Operatoren `+`, `-`, `+.`, `-.`, `&`, `&&`, `%` und `%%` können Vorzeichenoperatoren oder Infixoperatoren sein. Sie unterscheiden die Präfix-Version dieser Operatoren von der Infix-Version, indem Sie `~` am Anfang eines Präfixoperators hinzufügen, wenn er definiert wird. Das Symbol `~` wird nicht verwendet, wenn Sie den Operator verwenden, sondern nur wenn definiert.

## <a name="example"></a>Beispiel

Im folgenden Code wird veranschaulicht, wie mit Operatorüberladung ein Bruchtyp implementiert wird. Ein Bruch wird durch einen Zähler und einen Nenner dargestellt. Mit der Funktion `hcf` wird der größte gemeinsame Teiler zum Kürzen von Brüchen bestimmt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

**Ausgabe:**

```console
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a>Operatoren auf globaler Ebene

Sie können Operatoren auch auf globaler Ebene definieren. Der folgende Code definiert einen Operator `+?` .

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

Die Ausgabe des vorangehenden Codes lautet `12`.

Sie können die normalen arithmetischen Operatoren auf diese Weise neu definieren, da gemäß den Bereichsregeln für F# neu definierte Operatoren Vorrang vor den integrierten Operatoren haben.

Das Schlüsselwort `inline` wird oft mit globalen Operatoren verwendet, bei denen es sich häufig um kleine Funktionen handelt, die nach Möglichkeit in den aufrufenden Code integriert werden sollten. Wenn Sie Operatorfunktionen als Inlinefunktionen festlegen, können diese auch mit statisch aufgelösten Typparametern verwendet werden, um statisch aufgelösten generischen Code zu erstellen. Weitere Informationen finden Sie unter [Inline Funktionen](./functions/inline-functions.md) und [statisch aufgelöste Typparameter](./generics/statically-resolved-type-parameters.md).

## <a name="see-also"></a>Weitere Informationen

- [Mitglieder](./members/index.md)
