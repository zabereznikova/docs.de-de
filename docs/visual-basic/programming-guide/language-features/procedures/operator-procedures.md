---
title: Operatorprozeduren (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- overloaded operators [Visual Basic]
- operator overloading
- operator procedures
ms.assetid: 8c513d38-246b-4fb7-8b75-29e1364e555b
ms.openlocfilehash: 80c9a77494be95365899c6a25435fcfc5d2a7293
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175018"
---
# <a name="operator-procedures-visual-basic"></a>Operatorprozeduren (Visual Basic)
Eine Operatorprozedur besteht aus einer Reihe von Visual Basic-Anweisungen, die das Verhalten von Standardoperatoren definieren (z. B. `*`, `<>`, oder `And`) auf eine Klasse oder Struktur, die Sie definiert haben. Dies ist die Abkürzung *operatorüberladung*.  
  
## <a name="when-to-define-operator-procedures"></a>Beim Definieren von Operatorprozeduren  
 Wenn Sie eine Klasse oder Struktur definiert haben, können Sie die Variablen den Typ der Klasse oder Struktur deklarieren. Manchmal muss eine solche Variable in einem Vorgang im Rahmen eines Ausdrucks teilnehmen. Zu diesem Zweck müssen sie ein Operand eines Operators sein.  
  
 Visual Basic definiert nur die grundlegenden Datentypen von Operatoren. Sie können das Verhalten eines Operators, wenn bei mindestens einem definieren oder beider Operanden sind vom Typ der Klasse oder Struktur.  
  
 Weitere Informationen finden Sie unter [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="types-of-operator-procedure"></a>Typen von Operatorprozedur  
 Eine Operatorprozedur kann es sich um eine der folgenden Typen sein:  
  
-   Eine Definition eines unären Operators, in dem das Argument vom Typ der Klasse oder Struktur ist.  
  
-   Eine Definition eines binären Operators, in denen mindestens eines der Argumente des Typs der Klasse oder Struktur ist.  
  
-   Eine Definition eines Konvertierungsoperators, der den Typ der Klasse oder Struktur, in dem das Argument ist.  
  
-   Eine Definition eines Konvertierungsoperators, die den Typ der Klasse oder Struktur zurückgibt.  
  
 Konvertierungsoperatoren sind immer unär, und Sie immer `CType` wie der Operator, die Sie definieren.  
  
## <a name="declaration-syntax"></a>Deklarationssyntax  
 Die Syntax zum Deklarieren einer Operatorprozedur lautet wie folgt aus:  
  
 `Public Shared`   `[Widening | Narrowing]`   `Operator`  *Operatorsymbol* `(` *operand1*`[,`*operand2* `]) As` *Datatype*   
  
 `' Statements of the operator procedure.`  
  
 `End Operator`  
  
 Sie verwenden die `Widening` oder `Narrowing` Schlüsselwort nur auf einen Operator für die Konvertierung. Das Operatorsymbol ist immer [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) für einen Typkonvertierungsoperator.  
  
 Sie deklarieren die beiden Operanden einen binären Operator definieren, und Sie deklarieren, dass einer der Operanden einen unäroperator, einschließlich einen Typkonvertierungsoperator zu definieren. Alle Operanden müssen deklariert werden `ByVal`.  
  
 Sie deklarieren jeder Operand auf die gleiche Weise, die Sie deklarieren die Parameter für [Sub-Prozeduren](./sub-procedures.md).  
  
### <a name="data-type"></a>Datentyp  
 Da Sie für eine Klasse oder Struktur, die Sie definiert haben einen Operator definieren, muss mindestens einer der Operanden für den Datentyp, der diese Klasse oder Struktur sein. Für einen Typumwandlungsoperator verwenden muss entweder der Operand oder der Rückgabetyp des Datentyps der Klasse oder Struktur sein.  
  
 Weitere Informationen finden Sie unter [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
## <a name="calling-syntax"></a>Die Syntax aufrufen  
 Sie aufrufen eine Operatorprozedur implizit mit dem Symbol "Operator" in einem Ausdruck. Sie geben die Operanden auf die gleiche Weise, die für die vordefinierten Operatoren erforderlich ist.  
  
 Die Syntax für einen impliziten Aufruf einer Operatorprozedur lautet wie folgt aus:  
  
 `Dim testStruct As`  *Strukturname*  
  
 `Dim testNewStruct As`  *Strukturname*`= testStruct`*Operatorsymbol*   `10`  
  
### <a name="illustration-of-declaration-and-call"></a>Abbildung der Deklaration und Aufruf  
 Die folgende Struktur speichert einen 128-Bit-Ganzzahl-Wert als die höherwertigen und niederwertigen Bestandteile. Definiert die `+` Operator, um zwei `veryLong` Werte und generiert eine resultierende `veryLong` Wert.  
  
 [!code-vb[VbVbcnProcedures#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#23)]  
  
 Das folgende Beispiel zeigt einen typischen Aufruf von der `+` Operator definiert `veryLong`.  
  
 [!code-vb[VbVbcnProcedures#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#24)]  

## <a name="see-also"></a>Siehe auch

- [Verfahren](./index.md)
- [Sub-Prozeduren](./sub-procedures.md)
- [Function-Prozeduren](./function-procedures.md)
- [Eigenschaftenprozeduren](./property-procedures.md)
- [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)
- [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Vorgehensweise: Definieren eines Operators](./how-to-define-an-operator.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)
- [Vorgehensweise: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)
- [Vorgehensweise: Verwenden einer Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md)
