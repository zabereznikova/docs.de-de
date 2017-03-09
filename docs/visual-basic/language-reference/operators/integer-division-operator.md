---
title: "\ Operator (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.\"
  - "\"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "division operator, integer"
  - "integer division operator"
  - "zero, division by zero"
  - "arithmetic operators, division"
  - "division, by zero"
  - "backslash (\) [Visual Basic]"
  - "\ operator [Visual Basic]"
  - "integer quotient"
  - "math operators"
  - "quotients, integer"
  - "truncation, integer division"
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# \ Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Dividiert zwei Zahlen und gibt eine ganze Zahl als Ergebnis zurück.  
  
## Syntax  
  
```  
  
expression1 \ expression2  
```  
  
## Teile  
 `expression1`  
 Erforderlich.  Ein beliebiger numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich.  Ein beliebiger numerischer Ausdruck.  
  
## Unterstützte Typen  
 Alle numerischen Typen, einschließlich Typen ohne Vorzeichen, Gleitkommatypen sowie `Decimal`.  
  
## Ergebnis  
 Das Ergebnis ist der ganzzahlige Quotient, der sich aus der Division von `expression1` durch `expression2` ergibt. Es wird nur der ganzzahlige Teil beibehalten und jeglicher Rest verworfen.  Dies wird als *Verkürzung* bezeichnet.  
  
 Der Ergebnisdatentyp ist ein numerischer Typ, der sich für die Datentypen von `expression1` und `expression2` eignet.  Siehe die "Ganzzahlarithmetik"\-Tabellen in [Data Types of Operator Results](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
 Der [\/ Operator](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) gibt den vollständigen Quotienten zurück, der den Rest im Bruchteil enthält.  
  
## Hinweise  
 Vor dem Ausführen der Division versucht Visual Basic, einen numerischen Gleitkommaausdruck in `Long` zu konvertieren.  Wenn `Option Strict` `On` ist, tritt ein Compilerfehler auf.  Ist `Option Strict` `Off`, kann eine <xref:System.OverflowException>\-Ausnahme ausgelöst werden, wenn der Wert außerhalb des Bereichs von [Long Data Type](../../../visual-basic/language-reference/data-types/long-data-type.md) liegt.  Die Konvertierung zu `Long` unterliegt auch der *unverzerrten Rundung \(Banker's Rounding\)*.  Weitere Informationen finden Sie im Abschnitt "Nachkommastellen" unter [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Wenn `expression1` oder `expression2` [Nothing](../../../visual-basic/language-reference/nothing.md) ergibt, wird der Ausdruck als 0 \(null\) behandelt.  
  
## Versuchte Division durch 0 \(null\)  
 Wenn `expression2` 0 \(null\) ergibt, löst der Operator `\` eine <xref:System.DivideByZeroException>\-Ausnahme aus.  Dies gilt für alle numerischen Datentypen der Operanden.  
  
> [!NOTE]
>  Der Operator `\` kann *überladen* werden. Das bedeutet, dass eine Klasse oder Struktur sein Verhalten neu definiert, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist.  Wenn Sie diesen Operator im Code auf eine solche Klasse oder Struktur anwenden, sollten Sie auf jeden Fall sein neu definiertes Verhalten verstehen.  Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## Beispiel  
 In diesem Beispiel wird mit dem Operator `\` eine Ganzzahldivision ausgeführt.  Das Ergebnis ist eine ganze Zahl, die den ganzzahligen Quotienten der beiden Operanden darstellt, wobei der Rest verworfen wird.  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/visualbasic/integer-division-operator_1.vb)]  
  
 Die Ausdrücke im vorangehenden Beispiel geben die Werte 2, 3, 33 bzw. \-22 zurück.  
  
## Siehe auch  
 [\\\= Operator](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)   
 [\/ Operator](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Arithmetic Operators](../../../visual-basic/language-reference/operators/arithmetic-operators.md)   
 [Operator Precedence in Visual Basic](../../../visual-basic/language-reference/operators/operator-precedence.md)   
 [Operators Listed by Functionality](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)   
 [Arithmetic Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)