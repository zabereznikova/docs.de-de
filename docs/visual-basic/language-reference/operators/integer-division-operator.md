---
title: '\-Operator (Visual Basic)'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38718b109b4b3865238267039908ea1d51d06229
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-visual-basic"></a>\-Operator (Visual Basic)
Dividiert zwei Zahlen und gibt ein ganzzahliges Ergebnis zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a>Teile  
 `expression1`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
 `expression2`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Alle numerischen Typen, einschließlich der Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.  
  
## <a name="result"></a>Ergebnis  
 Das Ergebnis ist der Ganzzahlquotient von `expression1` geteilt durch `expression2`, die verworfen Nachkommateil und behält nur den ganzzahlige Teil. Dies bezeichnet man *Abschneiden*.  
  
 Datentyp des Ergebnisses ist ein numerischer Typ für die Datentypen der entsprechenden `expression1` und `expression2`. Finden Sie in den Tabellen "Ganzzahlarithmetik" in [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).  
  
 Die [/-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) gibt den vollständigen Quotienten zurück, der den Rest in den Teil mit Bruchzahlen enthält.  
  
## <a name="remarks"></a>Hinweise  
 Visual Basic Versuche vor dem Ausführen der Division einen beliebigen Gleitkomma numerischen Ausdruck konvertiert `Long`. Wenn `Option Strict` ist `On`, tritt ein Compilerfehler auf. Wenn `Option Strict` ist `Off`, wird ein <xref:System.OverflowException> ist möglich, wenn der Wert außerhalb des Bereichs der der [Long-Datentyp](../../../visual-basic/language-reference/data-types/long-data-type.md). Die Konvertierung in `Long` kann auch *Banker rounding*. Weitere Informationen finden Sie unter "Nachkommastellen" in [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md).  
  
 Wenn `expression1` oder `expression2` ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird dies als 0 (null) behandelt.  
  
## <a name="attempted-division-by-zero"></a>Versuchte Division durch 0 (null)  
 Wenn `expression2` ergibt 0 (null), die `\` löst der Operator einen <xref:System.DivideByZeroException> Ausnahme. Dies gilt für alle numerischen Datentypen der Operanden.  
  
> [!NOTE]
>  Die `\` Operator kann *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der betreffenden Klasse oder Struktur hat. Wenn im Code dieser Operator auf eine solche Klasse oder Struktur verwendet, achten Sie darauf, dass Sie dessen neu definierten Verhalten verstehen. Weitere Informationen finden Sie unter [Operatorprozeduren](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `\` Operator eine Ganzzahldivision ausgeführt. Das Ergebnis ist eine ganze Zahl, die den Ganzzahlquotient der beiden Operanden mit den übrigen verworfen darstellt.  
  
 [!code-vb[VbVbalrOperators#18](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/integer-division-operator_1.vb)]  
  
 Die Ausdrücke im vorhergehenden Beispiel geben die Werte von 2, 3, 33 und-22, bzw. zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [\\=-Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)  
 [/-Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)  
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)  
 [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)  
 [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
