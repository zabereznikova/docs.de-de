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
- comparison operators [Visual Basic], Visual Basicl
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
ms.openlocfilehash: 4e37f55b4c873c3dbea22a8edf0e5e2b58824720
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604925"
---
# <a name="comparison-operators-visual-basic"></a>Vergleichsoperatoren (Visual Basic)
Es folgen die Vergleichsoperatoren in Visual Basic definiert.  
  
 `<` Operator  
  
 `<=` Operator  
  
 `>` Operator  
  
 `>=` Operator  
  
 `=` Operator  
  
 `<>` Operator  
  
 [Is-Operator](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [Like-Operator](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 Diese Operatoren vergleichen zwei Ausdrücke, um zu bestimmen, ob sie gleich sind, und falls nicht, wie sie unterscheiden. `Is`, `IsNot`, und `Like` werden auf separaten Hilfeseiten im Detail besprochen. Die relationalen Vergleichsoperatoren werden auf dieser Seite im Detail erläutert.  
  
## <a name="syntax"></a>Syntax  
  
```  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Ein `Boolean` Wert, der das Ergebnis des Vergleichs darstellt.  
  
 `expression`  
 Erforderlich. Beliebiger Ausdruck.  
  
 `comparisonoperator`  
 Erforderlich. Alle relationalen Vergleichsoperator.  
  
 `object1`, `object2`  
 Erforderlich. Jeder Verweis zu verwendenden Objektnamen.  
  
 `string`  
 Erforderlich. Beliebiger `String`-Ausdruck.  
  
 `pattern`  
 Erforderlich. Alle `String` Ausdruck oder einen Bereich von Zeichen.  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält eine Liste von Vergleichsoperatoren für den relationalen und die Bedingungen, die bestimmen, ob `result` ist `True` oder `False`.  
  
|Operator|`True` if|`False` if|  
|--------------|---------------|----------------|  
|`<` (Kleiner als)|`expression1` < `expression2`|`expression1` >= `expression2`|  
|`<=` (Kleiner als oder gleich)|`expression1` <= `expression2`|`expression1` > `expression2`|  
|`>` (Größer als)|`expression1` > `expression2`|`expression1` <= `expression2`|  
|`>=` (Größer als oder gleich)|`expression1` >= `expression2`|`expression1` < `expression2`|  
|`=` (Gleich)|`expression1` = `expression2`|`expression1` <> `expression2`|  
|`<>` (Ungleich)|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  Die [=-Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) wird auch als Zuweisungsoperator verwendet.  
  
 Die `Is` -Operator, der `IsNot` -Operator, und die `Like` Operator haben spezifische Vergleich-Funktionen, die von den Operatoren in der obigen Tabelle unterscheiden.  
  
## <a name="comparing-numbers"></a>Vergleichen von Zahlen  
 Wenn Sie einen Ausdruck vom Typ vergleichen `Single` auf einen Typ `Double`, die `Single` Ausdruck konvertiert `Double`. Dieses Verhalten ist Gegensatz zum Verhalten in Visual Basic 6.  
  
 Auf ähnliche Weise, wenn Sie einen Ausdruck vom Typ vergleichen `Decimal` auf einen Ausdruck vom Typ `Single` oder `Double`, `Decimal` Ausdruck konvertiert `Single` oder `Double`. Für `Decimal` Ausdrücke, alle Dezimalstellenwert kleiner als 1E-28 möglicherweise verloren. Datenverluste Dezimalstellenwert kann bewirken, dass zwei Werte als gleich verglichen werden soll, wenn sie nicht sind. Aus diesem Grund sollten Sie darauf achten bei Verwendung von Gleichheit (`=`), zwei Gleitkommavariablen verglichen werden soll. Es ist sicherer, testen, ob der Absolute Wert des Unterschieds zwischen zwei Zahlen, die kleiner als eine kleine akzeptable Toleranz ist.  
  
### <a name="floating-point-imprecision"></a>Gleitkomma Ungenauigkeit  
 Beim Arbeiten mit Gleitkommazahlen, sollten Sie bedenken, dass sie nicht immer eine genaue Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen führen, über bestimmte Vorgänge, z. B. Wertvergleich und [Mod Operator](../../../visual-basic/language-reference/operators/mod-operator.md). Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="comparing-strings"></a>Vergleichen von Zeichenfolgen  
 Wenn Sie Zeichenfolgen vergleichen, die Zeichenfolgenausdrücke werden ausgewertet basierend auf deren Reihenfolge alphabetisch sortiert, abhängig von der `Option Compare` Einstellung.  
  
 `Option Compare Binary` Führt einen Zeichenfolgenvergleich auf einer Sortierreihenfolge, die von den internen binären Darstellungen der Zeichen abgeleitet. Die Sortierreihenfolge wird durch die Codepage bestimmt. Das folgende Beispiel zeigt eine typische binäre Sortierreihenfolge an.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 `Option Compare Text` Führt einen Zeichenfolgenvergleich durch Ihre Anwendung Gebietsschema bestimmt Groß-/Kleinschreibung, Text Sortierreihenfolge. Bei Festlegung `Option Compare Text` und die Zeichen im vorangehenden Beispiel sortieren, gilt die folgende Reihenfolge:  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a>Abhängigkeit vom Gebietsschema  
 Bei Festlegung `Option Compare Text`, kann das Ergebnis eines Zeichenfolgenvergleichs abhängen, auf dem Gebietsschema, in dem die Anwendung ausgeführt wird. Zwei Zeichen möglicherweise als gleichwertig in einem Gebietsschema aber nicht in einer anderen vergleichen. Wenn Sie einen Zeichenfolgenvergleich verwenden werden, um einige wichtige Entscheidungen, z. B. ob ein Anmeldeversuch, akzeptieren sollten Sie die Warnung, um Gebietsschema Empfindlichkeit sein. Legen Sie entweder `Option Compare Binary` oder aufrufende der <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, die berücksichtigt des Gebietsschemas.  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a>Programmierung ohne Datentypen mit relationalen Vergleichsoperatoren  
 Die Verwendung von relationalen Vergleichsoperatoren mit `Object` Ausdrücke darf nicht unter `Option Strict On`. Wenn `Option Strict` ist `Off`, und entweder `expression1` oder `expression2` ist ein `Object` Ausdruck, der Typen zur Laufzeit zu bestimmen, wie sie verglichen werden. Die folgende Tabelle zeigt, wie die Ausdrücke verglichen werden und das Ergebnis des Vergleichs, abhängig von der Common Language Runtime-Typ der Operanden.  
  
|Wenn die Operanden sind|Vergleich|  
|---------------------|-------------------|  
|Beide `String`|Vergleich basierend auf Eigenschaften zum Sortieren von Zeichenfolgen zu sortieren.|  
|Beide numerisch|Objekte in konvertiert `Double`, numerischen Vergleich.|  
|Eine numerische und eine `String`|Die `String` konvertiert eine `Double` und numerischen Vergleich wird ausgeführt. Wenn die `String` kann nicht konvertiert werden, um `Double`, wird eine <xref:System.InvalidCastException> ausgelöst wird.|  
|Eine oder beide sind Referenztypen außer `String`|Es wird eine <xref:System.InvalidCastException> ausgelöst.|  
  
 Behandeln von numerische vergleichen `Nothing` als 0. Behandeln von Zeichenfolgenvergleichen `Nothing` als `""` (eine leere Zeichenfolge).  
  
## <a name="overloading"></a>Überladen  
 Die relationalen Vergleichsoperatoren (`<`. `<=``>`, `>=`, `=`, `<>`) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur ihr Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Wenn Ihr Code einen dieser Operatoren auf solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
 Beachten Sie, dass die [=-Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) nur als relationalen Vergleichsoperator und nicht als Zuweisungsoperator überladen werden kann.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt verschiedene Verwendungsmöglichkeiten der relationalen Vergleichsoperatoren, die Sie zum Vergleichen von Ausdrücken verwenden. Relationale Vergleichsoperatoren Zurückgeben einer `Boolean` Ergebnis, das darstellt, und zwar unabhängig davon, ob der angegebene Ausdruck ergibt `True`. Beim Anwenden der `>` und `<` Operatoren in Zeichenfolgen, der Vergleich erfolgt mithilfe der normalen alphabetischen Sortierreihenfolge der Zeichenfolgen. Diese Reihenfolge kann Ihr Gebietsschema abhängig gemacht werden. Gibt an, ob die Sortierung Groß-/Kleinschreibung beachtet wird, hängt die [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) Einstellung.  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 Im vorherigen Beispiel gibt der erste Vergleich `False` und die verbleibenden Vergleiche zurückgeben `True`.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.InvalidCastException>  
 [=-Operator](../../../visual-basic/language-reference/operators/assignment-operator.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Vergleichsoperatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
