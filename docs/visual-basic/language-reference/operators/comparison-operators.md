---
title: Vergleichsoperatoren
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
ms.openlocfilehash: ea7604626ede66da818e4bc22fe4922bc752dc2c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74336085"
---
# <a name="comparison-operators-visual-basic"></a>Vergleichsoperatoren (Visual Basic)
Im folgenden sind die in Visual Basic definierten Vergleichs Operatoren angegeben.

 `<`-Operator

 `<=`-Operator

 `>`-Operator

 `>=`-Operator

 `=`-Operator

 `<>`-Operator

 [Is-Operator](../../../visual-basic/language-reference/operators/is-operator.md)

 [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)

 [Like-Operator](../../../visual-basic/language-reference/operators/like-operator.md)

 Diese Operatoren vergleichen zwei Ausdrücke, um zu bestimmen, ob Sie gleich sind, und falls nicht, wie Sie sich unterscheiden. `Is`, `IsNot`und `Like` werden auf separaten Hilfeseiten ausführlich erläutert. Die relationalen Vergleichs Operatoren werden auf dieser Seite ausführlich erläutert.

## <a name="syntax"></a>Syntax
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>-Komponenten
 `result`  
 Erforderlich Ein `Boolean` Wert, der das Ergebnis des Vergleichs darstellt.

 `expression1`, `expression2`  
 Erforderlich Beliebiger Ausdruck.

 `comparisonoperator`  
 Erforderlich Ein beliebiger relationaler Vergleichs Operator.

 `object1`, `object2`  
 Erforderlich Alle Verweis Objektnamen.

 `string`  
 Erforderlich Beliebiger `String` -Ausdruck.

 `pattern`  
 Erforderlich Alle `String` Ausdruck oder der Zeichenbereich.

## <a name="remarks"></a>Hinweise
 Die folgende Tabelle enthält eine Liste der relationalen Vergleichs Operatoren und die Bedingungen, die bestimmen, ob `result` `True` oder `False`ist.

|Operator|`True`, wenn|`False`, wenn|
|--------------|---------------|----------------|
|`<` (kleiner als)|`expression1` < `expression2`|`expression1` >= `expression2`|
|`<=` (kleiner als oder gleich)|`expression1` <= `expression2`|`expression1` > `expression2`|
|`>` (größer als)|`expression1` > `expression2`|`expression1` <= `expression2`|
|`>=` (größer als oder gleich)|`expression1` >= `expression2`|`expression1` < `expression2`|
|`=` (gleich)|`expression1` = `expression2`|`expression1` <> `expression2`|
|`<>` (ungleich)|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> Der [Operator =](../../../visual-basic/language-reference/operators/assignment-operator.md) wird auch als Zuweisungs Operator verwendet.

 Der `Is`-Operator, der `IsNot`-Operator und der `Like`-Operator verfügen über bestimmte Vergleichs Funktionalitäten, die sich von den Operatoren in der obigen Tabelle unterscheiden.

## <a name="comparing-numbers"></a>Vergleichen von Zahlen
 Wenn Sie einen Ausdruck vom Typ "`Single`" mit einem Typ vom Typ "`Double`" vergleichen, wird der `Single` Ausdruck in `Double`konvertiert. Dieses Verhalten steht im Gegensatz zu dem in Visual Basic 6 gefundenen Verhalten.

 Wenn Sie einen Ausdruck vom Typ `Decimal` mit einem Ausdruck vom Typ `Single` oder `Double`vergleichen, wird der `Decimal` Ausdruck in `Single` oder `Double`konvertiert. Bei `Decimal` ausdrücken könnte jeder Bruchteil, der kleiner als 1E-28 ist, verloren gehen. Ein solcher Verlust von Bruchteil-Werten kann bewirken, dass zwei Werte als gleich verglichen werden, wenn Sie nicht sind. Aus diesem Grund sollten Sie sorgfältig vorgehen, wenn Sie Gleichheit (`=`) zum Vergleichen von zwei Gleit Komma Variablen verwenden. Es ist sicherer, zu testen, ob der absolute Wert des Unterschieds zwischen den beiden Zahlen kleiner als eine geringfügige akzeptable Toleranz ist.

### <a name="floating-point-imprecision"></a>Ungenauigkeit von Gleit Komma Werten
 Beachten Sie beim Arbeiten mit Gleit Komma Zahlen, dass Sie nicht immer über eine genaue Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen bestimmter Vorgänge führen, wie z. b. Wert Vergleiche und der [Mod-Operator](../../../visual-basic/language-reference/operators/mod-operator.md). Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).

## <a name="comparing-strings"></a>Vergleichen von Zeichenfolgen
 Beim Vergleichen von Zeichen folgen werden die Zeichen folgen Ausdrücke basierend auf der alphabetischen Sortierreihenfolge ausgewertet, die von der `Option Compare` Einstellung abhängig ist.

 `Option Compare Binary` Basis Zeichenfolgenvergleiche in einer Sortierreihenfolge, die von den internen binären Darstellungen der Zeichen abgeleitet ist. Die Sortierreihenfolge wird von der Codepage bestimmt. Das folgende Beispiel zeigt eine typische binäre Sortierreihenfolge.

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 `Option Compare Text` Basiszeichen folgen Vergleiche bei einer durch die Groß-/Kleinschreibung Unterscheidung nach Groß-/Kleinschreibung, die durch das Gebiets Schema Wenn Sie `Option Compare Text` festlegen und die Zeichen im vorherigen Beispiel Sortieren, gilt die folgende Text Sortierreihenfolge:

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a>Gebiets Schema Abhängigkeit
 Wenn Sie `Option Compare Text`festlegen, kann das Ergebnis eines Zeichen folgen Vergleichs von dem Gebiets Schema abhängen, in dem die Anwendung ausgeführt wird. Zwei Zeichen können in einem Gebiets Schema gleich sein, aber nicht in einem anderen. Wenn Sie einen Zeichen folgen Vergleich verwenden, um wichtige Entscheidungen zu treffen, z. b., ob ein Anmeldeversuch angenommen werden soll, sollten Sie eine Warnung bezüglich Gebiets Schema Sensitivität haben. Sie können entweder `Option Compare Binary` festlegen oder den <xref:Microsoft.VisualBasic.Strings.StrComp%2A>aufrufen, der das Gebiets Schema berücksichtigt.

## <a name="typeless-programming-with-relational-comparison-operators"></a>Typlose Programmierung mit relationalen Vergleichs Operatoren
 Die Verwendung von relationalen Vergleichs Operatoren mit `Object` Ausdrücken ist unter `Option Strict On`nicht zulässig. Wenn `Option Strict` `Off`ist und entweder `expression1` oder `expression2` ein `Object` Ausdruck ist, bestimmen die Lauf Zeit Typen, wie Sie verglichen werden. Die folgende Tabelle zeigt, wie die Ausdrücke und das Ergebnis des Vergleichs verglichen werden, abhängig vom Lauf Zeittyp der Operanden.

|Wenn Operanden|Vergleich ist|
|---------------------|-------------------|
|Beide `String`|Sortier Vergleich auf Grundlage von Zeichen folgen Sortier Merkmalen.|
|Beide numerisch|Objekte, die in `Double`konvertiert werden, numerischer Vergleich.|
|Eine numerische und eine `String`|Der `String` wird in eine `Double` konvertiert, und es wird ein numerischer Vergleich ausgeführt. Wenn die `String` nicht in `Double`konvertiert werden kann, wird eine <xref:System.InvalidCastException> ausgelöst.|
|Entweder oder beide sind Verweis Typen, die nicht `String`|Es wird eine <xref:System.InvalidCastException> ausgelöst.|

 Numerische Vergleiche behandeln `Nothing` als 0 (null). Zeichen folgen Vergleiche behandeln `Nothing` als `""` (eine leere Zeichenfolge).

## <a name="overloading"></a>Überladen
 Die relationalen Vergleichs Operatoren (`<`. `<=`, `>`, `>=`, `=`, `<>`) können *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur ihr Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code einen dieser Operatoren in einer solchen Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).

 Beachten Sie, dass der [=-Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) nur als relationaler Vergleichs Operator, nicht als Zuweisungs Operator, überladen werden kann.

## <a name="example"></a>Beispiel
 Das folgende Beispiel zeigt verschiedene Verwendungen relationaler Vergleichs Operatoren, die Sie zum Vergleichen von Ausdrücken verwenden. Relationale Vergleichs Operatoren geben ein `Boolean` Ergebnis zurück, das angibt, ob der angegebene Ausdruck als `True`ausgewertet wird. Wenn Sie die `>`-und `<` Operatoren auf Zeichen folgen anwenden, erfolgt der Vergleich mithilfe der normalen alphabetischen Sortierreihenfolge der Zeichen folgen. Diese Reihenfolge kann von ihrer Gebiets Schema Einstellung abhängen. Ob bei der Sortierung die Groß-/Kleinschreibung beachtet wird, hängt von der [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) -Einstellung ab.

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 Im vorherigen Beispiel gibt der erste Vergleich `False` zurück, und die restlichen Vergleiche geben `True`zurück.

## <a name="see-also"></a>Siehe auch

- <xref:System.InvalidCastException>
- [=-Operator](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Vergleichs Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
