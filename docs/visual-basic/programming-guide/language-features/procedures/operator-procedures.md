---
title: "Operator Procedures (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, procedures"
  - "procedures, operator"
  - "Visual Basic code, operators"
  - "syntax, Operator procedures"
  - "operators [Visual Basic], overloading"
  - "overloaded operators"
  - "operator overloading"
  - "operator procedures"
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Operator Procedures (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Eine Operatorprozedur ist eine Reihe von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Anweisungen, die das Verhalten eines Standardoperators \(z. B. `*`, `<>` oder `And`\) in einer Klasse oder Struktur definieren, die Sie definiert haben.  Dies wird auch als *Überladen des Operators* bezeichnet.  
  
## Zeitpunkt für die Definition von Operatorprozeduren  
 Wenn Sie eine Klasse oder Struktur definiert haben, können Sie Variablen deklarieren, die dem Typ dieser Klasse oder Struktur angehören.  Gelegentlich muss eine solche Variable innerhalb eines Ausdrucks in einer Operation verwendet werden.  Dazu muss diese Variable ein Operand eines Operators sein.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] definiert nur die grundlegenden Datentypen von Operatoren.  Sie können das Verhalten eines Operators definieren, wenn mindestens einer der Operanden dem Typ der Klasse oder Struktur entspricht.  
  
 Weitere Informationen finden Sie unter [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## Typen von Operatorprozeduren  
 Eine Operatorprozedur kann einem der folgenden Typen angehören:  
  
-   Eine Definition eines unären Operators, wobei das Argument den gleichen Typ wie die Klasse oder Struktur aufweist.  
  
-   Eine Definition eines binären Operators, wobei mindestens eines der Argumente den gleichen Typ wie die Klasse oder Struktur aufweist.  
  
-   Eine Definition eines Konvertierungsoperators, wobei das Argument den gleichen Typ wie die Klasse oder Struktur aufweist.  
  
-   Eine Definition eines Konvertierungsoperators, der den Typ der Klasse oder Struktur zurückgibt.  
  
 Konvertierungsoperatoren sind immer unär, und als Operator wird stets `CType` definiert.  
  
## Deklarationssyntax  
 Die Syntax zur Deklaration einer Operatorprozedur lautet wie folgt:  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`   ``  *Operatorsymbol*  `(` *Operand1*  `[,`  *Operand2* `]) As`  *Datentyp*  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 Das `Widening`\-Schlüsselwort oder das `Narrowing`\-Schlüsselwort wird nur für einen Typkonvertierungsoperator verwendet.  Das Operatorsymbol für einen Typkonvertierungsoperator ist stets [CType\-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md).  
  
 Zur Definition eines binären Operators deklarieren Sie zwei Operanden, und zur Definition eines unären Operators sowie eines Typkonvertierungsoperators deklarieren Sie einen Operanden.  Für alle Operanden ist eine `ByVal`\-Deklaration erforderlich.  
  
 Jeder Operand wird auf die gleiche Weise deklariert wie Parameter für [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md).  
  
### Datentyp  
 Da Sie einen Operator für eine von Ihnen definierte Klasse oder Struktur definieren, muss mindestens einer der Operanden den gleichen Datentyp wie diese Klasse oder Struktur aufweisen.  Bei einem Typkonvertierungsoperator müssen der Datentyp des Operanden oder der Rückgabetyp dem Datentyp der Klasse oder Struktur entsprechen.  
  
 Weitere Informationen finden Sie unter [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## Aufrufsyntax  
 Zum impliziten Aufrufen einer Operatorprozedur verwenden Sie das Operatorsymbol in einem Ausdruck.  Sie geben die Operanden auf die gleiche Weise an wie vordefinierte Operatoren.  
  
 Die Syntax für einen impliziten Aufruf einer Operatorprozedur lautet wie folgt:  
  
 `Dim testStruct As`  *Strukturname*  
  
 `Dim testNewStruct As`  *Strukturname*  `= testStruct`  *Operatorsymbol*  `10`  
  
### Darstellung von Deklaration und Aufruf  
 Die folgende Struktur speichert einen ganzzahligen 128\-Bit\-Wert mit Vorzeichen als die konstituierenden höherwertigen und niedrigwertigen Teile.  Sie definiert den Operator `+`, mit dem zwei `veryLong` \-Werte hinzugefügt und ein resultierender `veryLong` \-Wert generiert werden.  
  
 [!code-vb[VbVbcnProcedures#23](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 Das folgende Beispiel zeigt einen typischen Aufruf des als `veryLong` definierten Operators `+`.  
  
 [!code-vb[VbVbcnProcedures#24](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 Weitere Informationen und Beispiele finden Sie unter [Operator Overloading in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).  
  
## Siehe auch  
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Sub Procedures](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md)   
 [Function\-Prozeduren](../../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md)   
 [Eigenschaftenprozeduren](../../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [How to: Define an Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)   
 [How to: Call an Operator Procedure](../../../../visual-basic/programming-guide/language-features/procedures/how-to-call-an-operator-procedure.md)   
 [How to: Use a Class that Defines Operators](../../../../visual-basic/programming-guide/language-features/procedures/how-to-use-a-class-that-defines-operators.md)