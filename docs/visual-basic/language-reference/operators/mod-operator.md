---
title: "Operator Mod(Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Mod"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Rest (Operator Mod)"
  - "Divisionsoperator, Mod-Operator"
  - "Modulus-Operator, Visual Basic"
  - "Mod-Operator [Visual Basic]"
  - "Operatoren [Visual Basic], Division"
  - "Arithmetische Operatoren, Mod"
  - "Mathematische Operatoren"
ms.assetid: 6ff7e40e-cec8-4c77-bff6-8ddd2791c25b
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Operator Mod(Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Teilt zwei Zahlen und gibt nur den Rest zurück.  
  
## Syntax  
  
```  
  
number1 Mod number2  
```  
  
## Teile  
 `number1`  
 Erforderlich.  Ein beliebiger numerischer Ausdruck.  
  
 `number2`  
 Erforderlich.  Ein beliebiger numerischer Ausdruck.  
  
## Unterstützte Typen  
 Alle numerischen Typen.  Dies schließt die Typen ohne Vorzeichen, Gleitkommatypen und `Decimal` ein.  
  
## Ergebnis  
 Das Ergebnis ist der Rest, nachdem `number1` durch `number2` geteilt wurde.  Zum Beispiel ergibt der Ausdruck `14 Mod 4` das Ergebnis 2.  
  
## Hinweise  
 Wenn `number1` oder `number2` ein Gleitkommawert ist, wird der Gleitkommarest der Division zurückgegeben.  Als Datentyp des Ergebnisses wird der kleinste Datentyp gewählt, der alle möglichen Ergebniswerte der Division mit den Datentypen von `number1` und `number2` speichern kann.  
  
 Wenn `number1` oder `number2` zu [Nothing](../../../visual-basic/language-reference/nothing.md) ausgewertet wird, wird der Ausdruck als 0 \(null\) behandelt.  
  
 Zugehörige Operatoren beinhalten Folgendes:  
  
-   Der [\\ Operator](../../../visual-basic/language-reference/operators/integer-division-operator.md) gibt den ganzzahligen Quotienten einer Division zurück.  Zum Beispiel ergibt der Ausdruck `14 \ 4` das Ergebnis 3.  
  
-   Der [\/ Operator](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) gibt den vollen Quotienten, einschließlich des Restes, als Gleitkommazahl zurück.  Zum Beispiel ergibt der Ausdruck `14 / 4` das Ergebnis 3,5.  
  
## Versuchte Division durch 0 \(null\)  
 Wenn `number2` 0 \(null\) ergibt, hängt das Verhalten des Operators `Mod` vom Datentyp der Operanden ab.  Bei einer Ganzzahldivision wird <xref:System.DivideByZeroException> ausgelöst.  Bei einer Gleitkommadivision wird <xref:System.Double.NaN> zurückgegeben.  
  
## Entsprechende Formel  
 Der Ausdruck `a Mod b` ist zu beiden der folgenden Formeln äquivalent:  
  
 `a - (b * (a \ b))`  
  
 `a - (b * Fix(a / b))`  
  
## Ungenauigkeit von Gleitkommawerten  
 Wenn Sie mit Gleitkommazahlen arbeiten, müssen Sie daran denken, dass die Zahlen im Speicher nicht immer präzise dargestellt werden.  Dies kann bei bestimmten Operationen zu unerwarteten Ergebnissen führen, z. B. beim Wertvergleich und beim Operator `Mod`.  Weitere Informationen finden Sie unter [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).  
  
## Überladen  
 Der Operator `Mod` kann *überladen* werden, d. h. dass eine Klasse oder Struktur sein Verhalten neu definieren kann.  Wenn Ihr Code den Operator `Mod` auf eine Instanz einer Klasse oder Struktur anwendet, die sein Verhalten neu definiert, müssen Sie das neu definierte Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 In diesem Beispiel werden mit dem Operator `Mod` zwei Zahlen dividiert und nur der Rest zurückgegeben.  Wenn es sich bei einer Zahl um eine Gleitkommazahl handelt, ist das Ergebnis eine Gleitkommazahl, die den Rest darstellt.  
  
 [!code-vb[VbVbalrOperators#31](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/mod-operator_1.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird die potenzielle Ungenauigkeit von Gleitkommaoperanden veranschaulicht.  In der ersten Anweisung sind die Operanden vom Typ `Double`, und 0,2 ist ein sich unendlich wiederholender Binärbruch, der im Speicher durch den Wert 0,20000000000000001 dargestellt wird.  In der zweiten Anweisung erzwingt das Literaltypzeichen `D`, dass beide Operanden den `Decimal`\-Datentyp haben. 0,2 wird präzise dargestellt.  
  
 [!code-vb[VbVbalrOperators#32](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/mod-operator_2.vb)]  
  
## Siehe auch  
 <xref:Microsoft.VisualBasic.Conversion.Int%2A>   
 <xref:Microsoft.VisualBasic.Conversion.Fix%2A>   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)   
 [\\ Operator](../../../visual-basic/language-reference/operators/integer-division-operator.md)