---
title: "Comparison Operators (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.<>"
  - "vb.>="
  - "vb.<="
  - "vb.>"
  - "vb.<"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "greater than or equal to operator [Visual Basic]"
  - ">= operator [Visual Basic]"
  - "= operator [Visual Basic]"
  - "< operator [Visual Basic]"
  - "less than operator [Visual Basic]"
  - "relational operators, syntax"
  - "Like operator [Visual Basic]"
  - "<> operator [Visual Basic]"
  - "> operator [Visual Basic]"
  - "equal operator [Visual Basic]"
  - "less than or equal to operator [Visual Basic]"
  - "symbols, operators"
  - "greater than operator [Visual Basic]"
  - "comparing values [Visual Basic]"
  - "operators [Visual Basic], relational"
  - "string comparison [Visual Basic]"
  - "not equal to comparison operator [Visual Basic]"
  - "<= operator [Visual Basic]"
  - "operators [Visual Basic], comparison"
  - "Is operator [Visual Basic]"
  - "comparison operators, Visual Basicl"
ms.assetid: d6cb12a8-e52e-46a7-8aaf-f804d634a825
caps.latest.revision: 20
caps.handback.revision: 20
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Comparison Operators (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Die folgenden Operatoren sind die Vergleichsoperatoren von Visual Basic.  
  
 Operator `<`  
  
 Operator `<=`  
  
 Operator `>`  
  
 Operator `>=`  
  
 Operator `=`  
  
 Operator `<>`  
  
 [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md)  
  
 [IsNot Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)  
  
 [Like Operator](../../../visual-basic/language-reference/operators/like-operator.md)  
  
 Diese Operatoren vergleichen zwei Ausdrücke, um zu festzustellen, ob sie gleich sind, und wenn nicht, wie sie sich unterscheiden.  `Is`, `IsNot` und `Like` werden ausführlich auf separaten Hilfeseiten erläutert.  Die relationalen Vergleichsoperatoren werden ausführlich auf dieser Seite behandelt.  
  
## Syntax  
  
```  
  
      result = expression1 comparisonoperator expression2  
result = object1 [Is | IsNot] object2  
result = string Like pattern  
```  
  
## Teile  
 `result`  
 Erforderlich.  Ein `Boolean`\-Wert, der das Ergebnis des Vergleichs darstellt.  
  
 `expression`  
 Erforderlich.  Ein beliebiger Ausdruck.  
  
 `comparisonoperator`  
 Erforderlich.  Beliebiger relationaler Vergleichsoperator.  
  
 `object1`, `object2`  
 Erforderlich.  Beliebige Verweisobjektnamen.  
  
 `string`  
 Erforderlich.  Ein beliebiger `String`\-Ausdruck.  
  
 `pattern`  
 Erforderlich.  Beliebiger `String`\-Ausdruck oder Zeichenbereich.  
  
## Hinweise  
 Die folgende Tabelle enthält eine Liste der relationalen Vergleichsoperatoren und die Bedingungen, die festlegen, ob `result` den Wert `True` oder `False` aufweist.  
  
|Operator|`True`, wenn|`False`, wenn|  
|--------------|------------------|-------------------|  
|`<` \(Kleiner als\)|`expression1` \< `expression2`|`expression1` \>\= `expression2`|  
|`<=` \(Kleiner oder gleich\)|`expression1` \<\= `expression2`|`expression1` \> `expression2`|  
|`>` \(Größer als\)|`expression1` \> `expression2`|`expression1` \<\= `expression2`|  
|`>=` \(Größer oder gleich\)|`expression1` \>\= `expression2`|`expression1` \< `expression2`|  
|`=` \(Gleich\)|`expression1` \= `expression2`|`expression1` \<\> `expression2`|  
|`<>` \(Ungleich\)|`expression1` \<\> `expression2`|`expression1` \= `expression2`|  
  
> [!NOTE]
>  Der [\= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) wird auch als Zuweisungsoperator verwendet.  
  
 Die Operatoren `Is`, `IsNot` und `Like` haben eine spezielle Bedeutung und unterscheiden sich in der Funktionalität von den Operatoren der vorhergehenden Tabelle.  
  
## Vergleich von Zahlen  
 Wenn ein Ausdruck vom Typ `Single` mit einem Ausdruck vom Typ `Double` verglichen wird, wird der `Single`\-Ausdruck in `Double` konvertiert.  Dieses Verhalten ist gegensätzlich zu dem Verhalten in Visual Basic 6.  
  
 Wenn ein Ausdruck vom Typ `Decimal` mit einem Ausdruck vom Typ `Single` oder `Double` verglichen wird, wird der `Decimal`\-Ausdruck ebenso in `Single` bzw. `Double` konvertiert.  Bei `Decimal`\-Ausdrücken gehen Dezimalstellenwerte unter 1E\-28 unter Umständen verloren.  Dieser Verlust von Dezimalstellenwerten kann dazu führen, dass zwei Werte als gleich verglichen werden, obwohl sie nicht gleich sind.  Aus diesem Grund sollte der Gleichheitsoperator \(`=`\) beim Vergleichen von zwei Gleitkommavariablen mit größter Sorgfalt verwendet werden.  Es ist ratsam zu testen, ob der absolute Wert der Differenz zwischen den zwei Zahlen kleiner als eine kleine akzeptable Toleranz ist.  
  
### Ungenauigkeit von Gleitkommawerten  
 Wenn Sie mit Gleitkommazahlen arbeiten, sollten Sie beachten, dass sie im Arbeitsspeicher nicht immer präzise dargestellt werden.  Dies könnte bei bestimmten Operationen zu unerwarteten Ergebnissen führen, z. B. bei einem Wertevergleich und beim [Operator Mod](../../../visual-basic/language-reference/operators/mod-operator.md).  Weitere Informationen finden Sie unter [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## Vergleichen von Zeichenfolgen  
 Bei einem Vergleich von Zeichenfolgen werden die Zeichenfolgen auf der Grundlage ihrer alphabetischen Sortierreihenfolge ausgewertet. Diese richtet sich nach der `Option Compare`\-Einstellung.  
  
 Bei `Option Compare Binary` wird der Zeichenfolgenvergleich auf der Grundlage einer Sortierreihenfolge durchgeführt, die von den internen binären Darstellungen der Zeichen abgeleitet wird.  Die Sortierreihenfolge wird durch die Codepage festgelegt.  Das folgende Beispiel zeigt eine typische binäre Sortierreihenfolge.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 `Option Compare Text` führt einen Zeichenfolgenvergleich auf der Grundlage einer vom Gebietsschema der Anwendung vorgegebenen Textsortierreihenfolge durch. Die Groß\-\/Kleinschreibung wird dabei nicht berücksichtigt.  Wenn Sie `Option Compare Text` festlegen und die Zeichen im vorangehenden Beispiel sortieren, wird folgende Textsortierreihenfolge angewendet:  
  
 `(A=a) < (À= à) < (B=b) < (E=e) < (Ê= ê) < (Ø = ø) < (Z=z)`  
  
### Abhängigkeit vom Gebietsschema  
 Wenn Sie `Option Compare Text` festlegen, kann das Ergebnis eines Zeichenfolgenvergleichs vom Gebietsschema abhängen, in dem die Anwendung ausgeführt wird.  Zwei Zeichen könnten in einem Gebietsschema als gleich, in einem anderen jedoch als nicht gleich ermittelt werden.  Wenn Sie Zeichenfolgenvergleiche für wichtige Entscheidungen verwenden \(z. B. ob ein Anmeldeversuch akzeptiert werden soll\), sollten Sie hinsichtlich der Gegebenheiten der einzelnen Gebietsschemas vorsichtig sein.  Überlegen Sie, ob Sie `Option Compare Binary` festlegen oder die <xref:Microsoft.VisualBasic.Strings.StrComp%2A> aufrufen, die das Gebietsschema berücksichtigt.  
  
## Typenloses Programmieren mit relationalen Vergleichsoperatoren  
 Die Verwendung relationaler Vergleichsoperatoren in `Object`\-Ausdrücken ist unter `Option Strict On` nicht möglich.  Wenn `Option Strict` auf `Off` festgelegt wurde und `expression1` oder `expression2` ein `Object`\-Ausdruck ist, legen die Laufzeittypen fest, wie sie verglichen werden.  Aus der folgenden Tabelle können Sie ersehen, wie Ausdrücke abhängig vom zugrunde liegenden Laufzeittyp der Operanden verglichen werden bzw. wie das Ergebnis aussieht.  
  
|Bei folgenden Operanden|Verwendeter Vergleich|  
|-----------------------------|---------------------------|  
|Beide `String`|Sortiervergleich basierend auf den Eigenschaften der Zeichenfolgensortierung.|  
|Beide numerisch|Objekte werden in `Double` konvertiert, numerischer Vergleich.|  
|Einer numerisch und einer `String`|`String` wird in `Double` konvertiert und numerischer Vergleich wird ausgeführt.  Wenn `String` nicht in `Double` konvertiert werden kann, wird <xref:System.InvalidCastException> ausgelöst.|  
|Einer oder beide sind Verweistypen, jedoch nicht vom Typ `String`|Eine <xref:System.InvalidCastException> wird ausgelöst.|  
  
 In numerischen Vergleichen wird `Nothing` als 0 behandelt.  Zeichenfolgenvergleiche behandeln `Nothing` als `""` \(eine leere Zeichenfolge\).  
  
## Überladen  
 Die relationalen Vergleichsoperatoren \(`<`.  `<=`, `>`, `>=`, `=`, `<>`\) können *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein bzw. ihr Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn der Code einen dieser Operatoren auf eine solche Klasse oder Struktur anwendet, sollten Sie auf jeden Fall ihr neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
 Beachten Sie, dass der [\= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md) nur als ein relationaler Vergleichsoperator und nicht als Zuweisungsoperator überladen werden kann.  
  
## Beispiel  
 Das folgende Beispiel zeigt unterschiedliche Verwendungsmöglichkeiten von relationalen Vergleichsoperatoren für den Vergleich von Ausdrücken.  Relationale Vergleichsoperatoren geben ein `Boolean`\-Ergebnis zurück, das darstellt, ob der angegebene Ausdruck `True` ergibt.  Wenn der Operator `>` und der Operator `<` auf Zeichenfolgen angewendet werden, wird der Vergleich mit der normalen alphabetischen Sortierreihenfolge der Zeichenfolgen ausgeführt.  Diese Reihenfolge kann von den Gebietsschemaeinstellungen abhängig sein.  Die Einstellung von [Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md) legt fest, ob beim Sortieren die Groß\- und Kleinschreibung berücksichtigt wird.  
  
 [!code-vb[VbVbalrOperators#1](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/comparison-operators_1.vb)]  
  
 Im vorhergehenden Beispiel gibt der erste Vergleich `False` zurück; die übrigen Vergleiche geben dagegen `True` zurück.  
  
## Siehe auch  
 <xref:System.InvalidCastException>   
 [\= Operator](../../../visual-basic/language-reference/operators/assignment-operator.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)