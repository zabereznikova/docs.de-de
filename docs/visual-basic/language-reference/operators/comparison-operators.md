---
title: Vergleichsoperatoren (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.<>
- vb.>=
- vb.<=
- vb.>
- vb.<
helpviewer_keywords:
- greater than or equal to operator [Visual Basic]
- '>= operator [Visual Basic]'
- = operator [Visual Basic]
- < operator [Visual Basic]
- less than operator [Visual Basic]
- relational operators [Visual Basic], syntax
- Like operator [Visual Basic]
- <> operator [Visual Basic]
- '> operator [Visual Basic]'
- equal operator [Visual Basic]
- less than or equal to operator [Visual Basic]
- symbols, operators
- greater than operator [Visual Basic]
- comparing values [Visual Basic]
- operators [Visual Basic], relational
- string comparison [Visual Basic]
- not equal to comparison operator [Visual Basic]
- <= operator [Visual Basic]
- operators [Visual Basic], comparison
- Is operator [Visual Basic]
- comparison operators [Visual Basic], Visual Basic
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: 10558563b528ce0bae3f77f31a97a217018f455f
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666827"
---
# <a name="comparison-operators-visual-basic"></a>Vergleichsoperatoren (Visual Basic)
Im folgenden sind die in Visual Basic definierten Vergleichs Operatoren angegeben.

 `<`KOM

 `<=`KOM

 `>`KOM

 `>=`KOM

 `=`KOM

 `<>`KOM

 [Is-Operator](../../../visual-basic/language-reference/operators/is-operator.md)

 [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)

 [Like-Operator](../../../visual-basic/language-reference/operators/like-operator.md)

 Diese Operatoren vergleichen zwei Ausdrücke, um zu bestimmen, ob Sie gleich sind, und falls nicht, wie Sie sich unterscheiden. `Is`, `IsNot` und`Like` werden auf separaten Hilfeseiten ausführlich erläutert. Die relationalen Vergleichs Operatoren werden auf dieser Seite ausführlich erläutert.

## <a name="syntax"></a>Syntax
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>Teile
 `result`  
 Erforderlich. Ein `Boolean` -Wert, der das Ergebnis des Vergleichs darstellt.

 `expression1`, `expression2`  
 Erforderlich. Beliebiger Ausdruck.

 `comparisonoperator`  
 Erforderlich. Ein beliebiger relationaler Vergleichs Operator.

 `object1`, `object2`  
 Erforderlich. Alle Verweis Objektnamen.

 `string`  
 Erforderlich. Beliebiger `String` -Ausdruck.

 `pattern`  
 Erforderlich. Beliebiger `String` Ausdruck oder Zeichenbereich.

## <a name="remarks"></a>Hinweise
 Die folgende Tabelle enthält eine Liste der relationalen Vergleichs Operatoren und die Bedingungen, die `result` bestimmen `True` , `False`ob oder ist.

|Operator|`True`, wenn|`False`, wenn|
|--------------|---------------|----------------|
|`<`(Kleiner als)|`expression1` < `expression2`|`expression1` >= `expression2`|
|`<=`(Kleiner als oder gleich)|`expression1` <= `expression2`|`expression1` > `expression2`|
|`>`(Größer als)|`expression1` > `expression2`|`expression1` <= `expression2`|
|`>=`(Größer als oder gleich)|`expression1` >= `expression2`|`expression1` < `expression2`|
|`=`(Gleich)|`expression1` = `expression2`|`expression1` <> `expression2`|
|`<>`(Ungleich)|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
>  Der [Operator =](../../../visual-basic/language-reference/operators/assignment-operator.md) wird auch als Zuweisungs Operator verwendet.

 Der `Is` -Operator, `IsNot` der-Operator und `Like` der-Operator verfügen über bestimmte Vergleichs Funktionalitäten, die sich von den Operatoren in der obigen Tabelle unterscheiden.

## <a name="comparing-numbers"></a>Vergleichen von Zahlen
 Wenn Sie einen Ausdruck vom `Single` Typ mit einem vom Typ `Double`vergleichen, wird `Single` der Ausdruck in `Double`konvertiert. Dieses Verhalten steht im Gegensatz zu dem in Visual Basic 6 gefundenen Verhalten.

 Wenn Sie `Decimal` einen Ausdruck vom Typ mit einem Ausdruck vom Typ `Single` oder `Double`vergleichen, wird der `Decimal` Ausdruck ebenso in `Single` oder `Double`konvertiert. Bei `Decimal` Ausdrücken können alle Bruchzahlen, die kleiner als 1E-28 sind, verloren gehen. Ein solcher Verlust von Bruchteil-Werten kann bewirken, dass zwei Werte als gleich verglichen werden, wenn Sie nicht sind. Aus diesem Grund sollten Sie bei der Verwendung von Gleichheit (`=`) darauf achten, zwei Gleit Komma Variablen zu vergleichen. Es ist sicherer, zu testen, ob der absolute Wert des Unterschieds zwischen den beiden Zahlen kleiner als eine geringfügige akzeptable Toleranz ist.

### <a name="floating-point-imprecision"></a>Ungenauigkeit von Gleit Komma Werten
 Beachten Sie beim Arbeiten mit Gleit Komma Zahlen, dass Sie nicht immer über eine genaue Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen bestimmter Vorgänge führen, wie z. b. Wert Vergleiche und der [Mod-Operator](../../../visual-basic/language-reference/operators/mod-operator.md). Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).

## <a name="comparing-strings"></a>Vergleichen von Zeichenfolgen
 Beim Vergleichen von Zeichen folgen werden die Zeichen folgen Ausdrücke basierend auf der alphabetischen Sortierreihenfolge ausgewertet, `Option Compare` die von der-Einstellung abhängig ist.

 `Option Compare Binary`basiert Zeichen folgen Vergleiche in einer Sortierreihenfolge, die von den internen binären Darstellungen der Zeichen abgeleitet ist. Die Sortierreihenfolge wird von der Codepage bestimmt. Das folgende Beispiel zeigt eine typische binäre Sortierreihenfolge.

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 `Option Compare Text`Basis Zeichenfolgenvergleiche bei einer Text Sortierreihenfolge ohne Beachtung der Groß-/Kleinschreibung, die durch das Gebiets Schema Wenn Sie die `Option Compare Text` Zeichen im vorherigen Beispiel festlegen und sortieren, gilt die folgende Text Sortierreihenfolge:

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a>Gebiets Schema Abhängigkeit
 Wenn Sie festlegen `Option Compare Text`, kann das Ergebnis eines Zeichen folgen Vergleichs von dem Gebiets Schema abhängen, in dem die Anwendung ausgeführt wird. Zwei Zeichen können in einem Gebiets Schema gleich sein, aber nicht in einem anderen. Wenn Sie einen Zeichen folgen Vergleich verwenden, um wichtige Entscheidungen zu treffen, z. b., ob ein Anmeldeversuch angenommen werden soll, sollten Sie eine Warnung bezüglich Gebiets Schema Sensitivität haben. Sie <xref:Microsoft.VisualBasic.Strings.StrComp%2A>können entweder `Option Compare Binary` festlegen oder aufrufen, bei dem das Gebiets Schema berücksichtigt wird.

## <a name="typeless-programming-with-relational-comparison-operators"></a>Typlose Programmierung mit relationalen Vergleichs Operatoren
 Die Verwendung von relationalen Vergleichs Operatoren mit `Object` Ausdrücken ist unter `Option Strict On`nicht zulässig. Wenn `Option Strict` ist `Off`und entweder `expression1` oder einAusdruck`Object` ist, bestimmen die Lauf Zeit Typen, wie Sie verglichen werden. `expression2` Die folgende Tabelle zeigt, wie die Ausdrücke und das Ergebnis des Vergleichs verglichen werden, abhängig vom Lauf Zeittyp der Operanden.

|Wenn Operanden|Vergleich ist|
|---------------------|-------------------|
|Zwar`String`|Sortier Vergleich auf Grundlage von Zeichen folgen Sortier Merkmalen.|
|Beide numerisch|Objekte, die `Double`in konvertiert werden, numerische Vergleiche.|
|Eine numerische und eine`String`|Wird in einen-Wert `Double` konvertiert, und es wird ein numerischer Vergleich ausgeführt. `String` Wenn nicht in `Double`konvertiert werden kann, wird <xref:System.InvalidCastException> eine ausgelöst. `String`|
|Entweder oder beide sind Verweis Typen, die nicht sind.`String`|Es wird eine <xref:System.InvalidCastException> ausgelöst.|

 Numerische Vergleiche werden `Nothing` als 0 (null) behandelt. Zeichen folgen Vergleiche `Nothing` behandeln `""` als (eine leere Zeichenfolge).

## <a name="overloading"></a>Überladen
 Die relationalen Vergleichs Operatoren (`<`. `<=`, `>`, `>=`, `=`, )`<>`kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur ihr Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code einen dieser Operatoren in einer solchen Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

 Beachten Sie, dass der [=-Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) nur als relationaler Vergleichs Operator, nicht als Zuweisungs Operator, überladen werden kann.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt verschiedene Verwendungen relationaler Vergleichs Operatoren, die Sie zum Vergleichen von Ausdrücken verwenden. Relationale Vergleichs Operatoren `Boolean` geben ein Ergebnis zurück, das angibt, ob der angegebene `True`Ausdruck zu ausgewertet wird. Wenn Sie die `>` Operatoren `<` und auf Zeichen folgen anwenden, erfolgt der Vergleich mithilfe der normalen alphabetischen Sortierreihenfolge der Zeichen folgen. Diese Reihenfolge kann von ihrer Gebiets Schema Einstellung abhängen. Ob bei der Sortierung die Groß-/Kleinschreibung beachtet wird, hängt von der [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) -Einstellung ab.

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 Im vorherigen Beispiel gibt `False` der erste Vergleich zurück, und die restlichen Vergleiche geben zurück. `True`

## <a name="see-also"></a>Siehe auch

- <xref:System.InvalidCastException>
- [=-Operator](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Vergleichs Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
