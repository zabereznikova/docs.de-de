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
ms.openlocfilehash: 9014cac5e2f3933b27411dfe5681fc16f4cdde30
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013581"
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
  
 Diese Operatoren vergleichen zwei Ausdrücke, um zu bestimmen, ob sie gleich sind, und falls nicht, wie sie sich unterscheiden. `Is`, `IsNot`, und `Like` werden auf separaten Hilfeseiten ausführlich erläutert. Die relationalen Vergleichsoperatoren werden auf dieser Seite im Detail erläutert.  
  
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
 Erforderlich. Jede relationale Vergleichsoperator.  
  
 `object1`, `object2`  
 Erforderlich. Jeder Verweis zu verwendenden Objektnamen.  
  
 `string`  
 Erforderlich. Beliebiger `String` -Ausdruck.  
  
 `pattern`  
 Erforderlich. Alle `String` Ausdruck oder einen Bereich von Zeichen.  
  
## <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält eine Liste mit der relationalen Vergleichsoperatoren und die Bedingungen, die bestimmen, ob `result` ist `True` oder `False`.  
  
|Operator|`True`, wenn|`False`, wenn|  
|--------------|---------------|----------------|  
|`<` (Kleiner als)|`expression1` < `expression2`|`expression1` >= `expression2`|  
|`<=` (Kleiner als oder gleich)|`expression1` <= `expression2`|`expression1` > `expression2`|  
|`>` (Größer als)|`expression1` > `expression2`|`expression1` <= `expression2`|  
|`>=` (Größer als oder gleich)|`expression1` >= `expression2`|`expression1` < `expression2`|  
|`=` (Gleich)|`expression1` = `expression2`|`expression1` <> `expression2`|  
|`<>` (Ungleich)|`expression1` <> `expression2`|`expression1` = `expression2`|  
  
> [!NOTE]
>  Die [= (Operator)](../../../visual-basic/language-reference/operators/assignment-operator.md) wird auch als Zuweisungsoperator verwendet.  
  
 Die `Is` -Operator, der `IsNot` -Operator, und die `Like` Operator haben bestimmten Vergleich von Funktionen, die von den Operatoren in der obigen Tabelle unterscheiden.  
  
## <a name="comparing-numbers"></a>Vergleichen von Zahlen  
 Sie vergleichen, wenn einen Ausdruck vom Typ `Single` eines Typs `Double`, `Single` Ausdruck konvertiert wird `Double`. Dieses Verhalten ist Gegensatz zu dem Verhalten in Visual Basic 6.  
  
 Wenn Sie auf ähnliche Weise einen Ausdruck vom Typ vergleichen `Decimal` auf einen Ausdruck vom Typ `Single` oder `Double`, `Decimal` Ausdruck konvertiert wird `Single` oder `Double`. Für `Decimal` Ausdrücke anteilige Wert kleiner als 1E-28 möglicherweise verloren. Solche anteilige Wert möglicherweise zum Verlust zwei Werte als gleich verglichen werden soll, wenn sie nicht sind. Aus diesem Grund sollten Sie darauf achten, wenn Gleichheit mit (`=`), zwei Gleitkommavariablen verglichen werden soll. Es ist sicherer, testen, ob der Absolute Wert des Unterschieds zwischen den beiden Zahlen, die kleiner als eine kleine akzeptable Toleranz ist.  
  
### <a name="floating-point-imprecision"></a>Gleitkomma Ungenauigkeit  
 Beim Arbeiten mit Gleitkommazahlen, Bedenken Sie, dass sie nicht immer eine genaue Darstellung im Arbeitsspeicher verfügen. Dies kann zu unerwarteten Ergebnissen führen, von der bestimmte Vorgänge, z. B. den Wertvergleich und [Mod-Operator](../../../visual-basic/language-reference/operators/mod-operator.md). Weitere Informationen finden Sie unter [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## <a name="comparing-strings"></a>Vergleichen von Zeichenfolgen  
 Wenn Sie Zeichenfolgen vergleichen, die Zeichenfolgenausdrücke werden ausgewertet basierend auf ihrer alphabetische Sortierreihenfolge, auf die die `Option Compare` festlegen.  
  
 `Option Compare Binary` Führt einen Zeichenfolgenvergleich auf einer Sortierreihenfolge, die von der internen binären Darstellungen der Zeichen abgeleitet. Die Sortierreihenfolge wird durch die Codepage bestimmt. Das folgende Beispiel zeigt eine typische binäre Sortierreihenfolge an.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 `Option Compare Text` Führt einen Zeichenfolgenvergleich auf einer Groß-/Kleinschreibung, Text Sortierreihenfolge, die vom Gebietsschema der Anwendung bestimmt. Wenn Sie festlegen, `Option Compare Text` und die Zeichen im vorherigen Beispiel sortieren, gilt die folgende Reihenfolge:  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### <a name="locale-dependence"></a>Abhängigkeit vom Gebietsschema  
 Wenn Sie festlegen, `Option Compare Text`, kann das Ergebnis eines Zeichenfolgenvergleichs abhängen, auf dem Gebietsschema, in dem die Anwendung ausgeführt wird. Zwei Zeichen möglicherweise als gleichwertig, die in einem Gebietsschema aber nicht in einer anderen vergleichen. Wenn Sie einen Zeichenfolgenvergleich verwenden, z. B. an, ob eine anzunehmen, sich anzumelden, wichtige Entscheidungen treffen sollten Sie die Warnung, die Gebietsschema-Vertraulichkeit sein. Sollten Sie entweder die Einstellung `Option Compare Binary` oder die aufrufenden die <xref:Microsoft.VisualBasic.Strings.StrComp%2A>, der das Gebietsschema berücksichtigt akzeptiert.  
  
## <a name="typeless-programming-with-relational-comparison-operators"></a>Programmierung ohne Datentypen mit relationalen Vergleichsoperatoren  
 Die Verwendung von relationalen Vergleichsoperatoren mit `Object` Ausdrücke ist nicht zulässig, unter `Option Strict On`. Wenn `Option Strict` ist `Off`, und entweder `expression1` oder `expression2` ist ein `Object` Ausdruck, der Runtime-Typen zu ermitteln, wie sie verglichen werden. Die folgende Tabelle zeigt, wie die Ausdrücke verglichen werden und das Ergebnis des Vergleichs, je nach den Laufzeittyp der Operanden.  
  
|Wenn die Operanden sind|Vergleich|  
|---------------------|-------------------|  
|Beide `String`|Vergleich basierend auf Eigenschaften zum Sortieren von Zeichenfolgen zu sortieren.|  
|Numerische|Objekte in konvertiert `Double`, numerischen Vergleich.|  
|Eine numerische und eine `String`|Die `String` konvertiert wird, um eine `Double` und numerischen Vergleich wird ausgeführt. Wenn die `String` kann nicht konvertiert werden, um `Double`, <xref:System.InvalidCastException> ausgelöst.|  
|Eine oder beide sind Verweistypen außer `String`|Es wird eine <xref:System.InvalidCastException> ausgelöst.|  
  
 Behandeln von numerische vergleichen `Nothing` als 0. Vergleich von Zeichenfolgen behandelt `Nothing` als `""` (eine leere Zeichenfolge).  
  
## <a name="overloading"></a>Überladen  
 Die relationalen Vergleichsoperatoren (`<`. `<=``>`, `>=`, `=`, `<>`) kann *überladen*, was bedeutet, dass eine Klasse oder Struktur deren Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code einen dieser Operatoren für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
 Beachten Sie, dass die [= (Operator)](../../../visual-basic/language-reference/operators/assignment-operator.md) nur als relationale Vergleichsoperator und als Zuweisungsoperator nicht überladen werden kann.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt verschiedene Einsatzbereiche der relationalen Vergleichsoperatoren, die Sie zum Vergleich von Ausdrücken verwenden. Zurückgeben der relationale Vergleichsoperator eine `Boolean` Ergebnis, das angibt, ob der angegebene Ausdruck ergibt `True`. Beim Anwenden der `>` und `<` Operatoren in Zeichenfolgen, der Vergleich erfolgt mithilfe der normalen Reihenfolge der alphabetischen Sortierung der Zeichenfolgen. Diese Reihenfolge kann abhängig von der gebietsschemaeinstellung sein. Abhängig davon, ob die Sortierung Groß-/Kleinschreibung beachtet wird die [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) festlegen.  
  
 [!code-vb[VbVbalrOperators#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#1)]  
  
 Im vorherigen Beispiel gibt der erste Vergleich `False` und die verbleibenden Vergleiche zurückgeben `True`.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.InvalidCastException>
- [=-Operator](../../../visual-basic/language-reference/operators/assignment-operator.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Problembehandlung bei Datentypen](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Vergleichsoperatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
