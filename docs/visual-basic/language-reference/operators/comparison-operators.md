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
ms.openlocfilehash: fcbb9052a79fa4b20b5a0f8fdc15de73d55a4281
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873442"
---
# <a name="comparison-operators-visual-basic"></a>Vergleichsoperatoren (Visual Basic)

Im folgenden sind die in Visual Basic definierten Vergleichs Operatoren angegeben.

 `<` KOM

 `<=` KOM

 `>` KOM

 `>=` KOM

 `=` KOM

 `<>` KOM

 [Is-Operator](is-operator.md)

 [IsNot-Operator](isnot-operator.md)

 [Like-Operator](like-operator.md)

 Diese Operatoren vergleichen zwei Ausdrücke, um zu bestimmen, ob Sie gleich sind, und falls nicht, wie Sie sich unterscheiden. `Is`, `IsNot` und `Like` werden auf separaten Hilfeseiten ausführlich erläutert. Die relationalen Vergleichs Operatoren werden auf dieser Seite ausführlich erläutert.

## <a name="syntax"></a>Syntax
  
```vb
result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>Bestandteile

 `result`  
 Erforderlich. Ein- `Boolean` Wert, der das Ergebnis des Vergleichs darstellt.

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

## <a name="remarks"></a>Bemerkungen

 Die folgende Tabelle enthält eine Liste der relationalen Vergleichs Operatoren und die Bedingungen, die bestimmen, ob `result` `True` oder ist `False` .

|Operator|`True`, wenn|`False`, wenn|
|--------------|---------------|----------------|
|`<` (Kleiner als)|`expression1` < `expression2`|`expression1` >= `expression2`|
|`<=` (Kleiner als oder gleich)|`expression1` <= `expression2`|`expression1` > `expression2`|
|`>` (Größer als)|`expression1` > `expression2`|`expression1` <= `expression2`|
|`>=` (Größer als oder gleich)|`expression1` >= `expression2`|`expression1` < `expression2`|
|`=` (Gleich)|`expression1` = `expression2`|`expression1` <> `expression2`|
|`<>` (Ungleich)|`expression1` <> `expression2`|`expression1` = `expression2`|

> [!NOTE]
> Der [Operator =](assignment-operator.md) wird auch als Zuweisungs Operator verwendet.

 Der `Is` -Operator, der `IsNot` -Operator und der- `Like` Operator verfügen über bestimmte Vergleichs Funktionalitäten, die sich von den Operatoren in der obigen Tabelle unterscheiden.

## <a name="comparing-numbers"></a>Vergleichen von Zahlen

 Wenn Sie einen Ausdruck vom Typ `Single` mit einem vom Typ vergleichen `Double` , `Single` wird der Ausdruck in konvertiert `Double` . Dieses Verhalten steht im Gegensatz zu dem in Visual Basic 6 gefundenen Verhalten.

 Wenn Sie einen Ausdruck vom Typ `Decimal` mit einem Ausdruck vom Typ `Single` oder vergleichen `Double` , `Decimal` wird der Ausdruck ebenso in oder konvertiert `Single` `Double` . Bei `Decimal` Ausdrücken können alle Bruchzahlen, die kleiner als 1E-28 sind, verloren gehen. Ein solcher Verlust von Bruchteil-Werten kann bewirken, dass zwei Werte als gleich verglichen werden, wenn Sie nicht sind. Aus diesem Grund sollten Sie bei der Verwendung von Gleichheit () darauf achten, `=` zwei Gleit Komma Variablen zu vergleichen. Es ist sicherer, zu testen, ob der absolute Wert des Unterschieds zwischen den beiden Zahlen kleiner als eine geringfügige akzeptable Toleranz ist.

### <a name="floating-point-imprecision"></a>Ungenauigkeit von Gleit Komma Werten

 Beachten Sie beim Arbeiten mit Gleit Komma Zahlen, dass Sie nicht immer über eine genaue Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen bestimmter Vorgänge führen, wie z. b. Wert Vergleiche und der [Mod-Operator](mod-operator.md). Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).

## <a name="comparing-strings"></a>Vergleichen von Zeichenfolgen

 Beim Vergleichen von Zeichen folgen werden die Zeichen folgen Ausdrücke basierend auf der alphabetischen Sortierreihenfolge ausgewertet, die von der-Einstellung abhängig ist `Option Compare` .

 `Option Compare Binary` basiert Zeichen folgen Vergleiche in einer Sortierreihenfolge, die von den internen binären Darstellungen der Zeichen abgeleitet ist. Die Sortierreihenfolge wird von der Codepage bestimmt. Das folgende Beispiel zeigt eine typische binäre Sortierreihenfolge.

 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

 `Option Compare Text` Basis Zeichenfolgenvergleiche bei einer Text Sortierreihenfolge ohne Beachtung der Groß-/Kleinschreibung, die durch das Gebiets Schema Wenn Sie `Option Compare Text` die Zeichen im vorherigen Beispiel festlegen und sortieren, gilt die folgende Text Sortierreihenfolge:

 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`

### <a name="locale-dependence"></a>Gebiets Schema Abhängigkeit

 Wenn Sie festlegen `Option Compare Text` , kann das Ergebnis eines Zeichen folgen Vergleichs von dem Gebiets Schema abhängen, in dem die Anwendung ausgeführt wird. Zwei Zeichen können in einem Gebiets Schema gleich sein, aber nicht in einem anderen. Wenn Sie einen Zeichen folgen Vergleich verwenden, um wichtige Entscheidungen zu treffen, z. b., ob ein Anmeldeversuch angenommen werden soll, sollten Sie eine Warnung bezüglich Gebiets Schema Sensitivität haben. Sie können entweder festlegen `Option Compare Binary` oder aufrufen <xref:Microsoft.VisualBasic.Strings.StrComp%2A> , bei dem das Gebiets Schema berücksichtigt wird.

## <a name="typeless-programming-with-relational-comparison-operators"></a>Typlose Programmierung mit relationalen Vergleichs Operatoren

 Die Verwendung von relationalen Vergleichs Operatoren mit `Object` Ausdrücken ist unter nicht zulässig `Option Strict On` . Wenn `Option Strict` ist `Off` und entweder `expression1` oder `expression2` ein Ausdruck ist `Object` , bestimmen die Lauf Zeit Typen, wie Sie verglichen werden. Die folgende Tabelle zeigt, wie die Ausdrücke und das Ergebnis des Vergleichs verglichen werden, abhängig vom Lauf Zeittyp der Operanden.

|Wenn Operanden|Vergleich ist|
|---------------------|-------------------|
|Zwar `String`|Sortier Vergleich auf Grundlage von Zeichen folgen Sortier Merkmalen.|
|Beide numerisch|Objekte, die in konvertiert `Double` werden, numerische Vergleiche.|
|Eine numerische und eine `String`|`String`Wird in einen-Wert konvertiert, `Double` und es wird ein numerischer Vergleich ausgeführt. Wenn `String` nicht in konvertiert werden kann `Double` , wird eine ausgelöst <xref:System.InvalidCastException> .|
|Entweder oder beide sind Verweis Typen, die nicht sind. `String`|Es wird eine <xref:System.InvalidCastException> ausgelöst.|

 Numerische Vergleiche werden als 0 (null) behandelt `Nothing` . Zeichen folgen Vergleiche behandeln `Nothing` als `""` (eine leere Zeichenfolge).

## <a name="overloading"></a>Überladen

 Die relationalen Vergleichs Operatoren ( `<` . `<=`, `>` , `>=` , `=` , `<>` ) kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur ihr Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code einen dieser Operatoren in einer solchen Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md).

 Beachten Sie, dass der [=-Operator](assignment-operator.md) nur als relationaler Vergleichs Operator, nicht als Zuweisungs Operator, überladen werden kann.

## <a name="example"></a>Beispiel

 Das folgende Beispiel zeigt verschiedene Verwendungen relationaler Vergleichs Operatoren, die Sie zum Vergleichen von Ausdrücken verwenden. Relationale Vergleichs Operatoren geben ein `Boolean` Ergebnis zurück, das angibt, ob der angegebene Ausdruck zu ausgewertet wird `True` . Wenn Sie die `>` Operatoren und auf Zeichen folgen anwenden `<` , erfolgt der Vergleich mithilfe der normalen alphabetischen Sortierreihenfolge der Zeichen folgen. Diese Reihenfolge kann von ihrer Gebiets Schema Einstellung abhängen. Ob bei der Sortierung die Groß-/Kleinschreibung beachtet wird, hängt von der [Option Compare](../statements/option-compare-statement.md) -Einstellung ab.

 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]

 Im vorherigen Beispiel gibt der erste Vergleich zurück, `False` und die restlichen Vergleiche geben zurück `True` .

## <a name="see-also"></a>Weitere Informationen

- <xref:System.InvalidCastException>
- [=-Operator](assignment-operator.md)
- [Operatorrangfolge in Visual Basic](operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](operators-listed-by-functionality.md)
- [Problembehandlung bei Datentypen](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Comparison Operators in Visual Basic](../../programming-guide/language-features/operators-and-expressions/comparison-operators.md)
