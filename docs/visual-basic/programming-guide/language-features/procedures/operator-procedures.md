---
title: Operatorprozeduren (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic code, procedures
- procedures, operator
- Visual Basic code, operators
- syntax, Operator procedures
- operators [Visual Basic], overloading
- overloaded operators
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a9e86c9c466ba236cc33153f2f341af35c622de6
ms.lasthandoff: 03/13/2017

---
# <a name="operator-procedures-visual-basic"></a>Operatorprozeduren (Visual Basic)
In einer Operatorprozedur ist eine Reihe von [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] -Anweisungen, die das Verhalten eines standard-Operators definieren (z. B. `*`, `<>`, oder `And`) für eine Klasse oder Struktur, die Sie definiert haben. Dies nennt man auch *überladen*.  
  
## <a name="when-to-define-operator-procedures"></a>Beim Definieren von Operatorprozeduren  
 Wenn Sie eine Klasse oder Struktur definiert haben, können Sie Variablen den Typ der Klasse oder Struktur deklarieren. Mitunter muss eine solche Variable zur Teilnahme an eines Vorgangs als Teil eines Ausdrucks. Zu diesem Zweck müssen sie ein Operand eines Operators sein.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]Operatoren definiert nur die grundlegenden Datentypen. Sie können das Verhalten eines Operators, wenn eine oder beide der Operanden sind vom Typ der Klasse oder Struktur.  
  
 Weitere Informationen finden Sie unter [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="types-of-operator-procedure"></a>Typen von Operatorprozeduren  
 Eine Operatorprozedur kann einer der folgenden Typen sein:  
  
-   Eine Definition, in dem das Argument vom Typ der Klasse oder Struktur ist, ein unärer Operator.  
  
-   Eine Definition eines binären Operators, wobei mindestens eines der Argumente des Typs von der Klasse oder Struktur ist.  
  
-   Eine Definition eines Konvertierungsoperators, wobei das Argument vom Typ der Klasse oder Struktur ist.  
  
-   Eine Definition eines Konvertierungsoperators, der den Typ der Klasse oder Struktur zurückgibt.  
  
 Konvertierungsoperatoren sind immer unär, und Sie immer `CType` wie der Operator definieren.  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  
 Die Syntax zum Deklarieren einer Operatorprozedur lautet wie folgt:  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`  *operatorsymbol*  `(` *operand1*  `[,`  *operand2* `]) As`  *datatype*  
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 Verwenden Sie die `Widening` oder `Narrowing` nur für einen Typkonvertierungsoperator-Schlüsselwort. Das Operatorsymbol ist immer [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) für einen Typkonvertierungsoperator.  
  
 Sie deklarieren die beiden Operanden einen binären Operator definieren, und Sie deklarieren, dass einer der Operanden einen unärer Operator, z. B. einen Typkonvertierungsoperator definieren. Alle Operanden müssen deklariert werden `ByVal`.  
  
 Sie deklarieren jeden Operanden auf die gleiche Weise, die Sie deklarieren die Parameter für [Sub-Prozeduren](./sub-procedures.md).  
  
### <a name="data-type"></a>Datentyp  
 Da Sie für eine Klasse oder Struktur definierten ein Operators definieren, muss mindestens einer der Operanden den Datentyp der Klasse oder Struktur sein. Für einen Typkonvertierungsoperator muss der Operand oder der Rückgabetyp des Datentyps der Klasse oder Struktur sein.  
  
 Weitere Informationen finden Sie unter [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="calling-syntax"></a>Aufrufen der Syntax  
 Sie aufrufen eine Operatorprozedur implizit durch das Operatorsymbol in einem Ausdruck verwenden. Sie geben die Operanden auf die selbe Weise wie für die vordefinierten Operatoren.  
  
 Die Syntax für einen impliziten Aufruf einer Operatorprozedur lautet wie folgt:  
  
 `Dim testStruct As`  *structurename*  
  
 `Dim testNewStruct As`  *Structurename*`= testStruct`*Operatorsymbol    *  `10`  
  
### <a name="illustration-of-declaration-and-call"></a>Darstellung von Deklaration und Aufruf  
 Die folgende Struktur speichert einen 128-Bit-Ganzzahl mit Vorzeichen-Wert als die konstituierenden höherwertigen und niedrigwertigen Teile. Definiert die `+` Operator, um zwei `veryLong` Werte und generiert einen `veryLong` Wert.  
  
 [!code-vb[VbVbcnProcedures&23;](./codesnippet/VisualBasic/operator-procedures_1.vb)]  
  
 Das folgende Beispiel zeigt einen normalen Aufruf der `+` Operator definiert `veryLong`.  
  
 [!code-vb[VbVbcnProcedures&#24;](./codesnippet/VisualBasic/operator-procedures_2.vb)]  
  
 Weitere Informationen und Beispiele finden Sie unter [Überladen von Operatoren in Visual Basic 2005](http://go.microsoft.com/fwlink/?LinkId=101703).  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)   
 [Sub-Prozeduren](./sub-procedures.md)   
 [Function-Prozeduren](./function-procedures.md)   
 [Property-Prozeduren](./property-procedures.md)   
 [Prozedurparameter und Argumente](./procedure-parameters-and-arguments.md)   
 [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Gewusst wie: Definieren eines Operators](./how-to-define-an-operator.md)   
 [Gewusst wie: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)   
 [Gewusst wie: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)   
 [Gewusst wie: Verwenden einer Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md)
