---
title: 'Gewusst wie: Aufrufen einer Operatorprozedur (Visual Basic)'
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedure calls [Visual Basic], operator overloading
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- overloaded operators [Visual Basic], calling
- operator overloading
ms.assetid: 0dce42cc-f0b0-4c14-9f62-018b21f33497
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 21545f2488bfabd0abc9c6e316d21bbc4d5aeb91
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Gewusst wie: Aufrufen einer Operatorprozedur (Visual Basic)
Sie aufrufen mit dem Symbol "Operator" in einem Ausdruck eine Operatorprozedur. Im Fall eines Konvertierungsoperators rufen Sie die [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) um einen Wert von einem Datentyp in einen anderen zu konvertieren.  
  
 Operatorprozeduren werden nicht explizit aufrufen. Verwenden Sie nur den Operator, oder die `CType` -Funktion in einer zuweisungsanweisung oder einen Ausdruck ein, die gleiche Weise, die Sie in der Regel einen Operator verwenden. Visual Basic führt der Aufruf die Operatorprozedur an.  
  
 Definieren eines Operators in einer Klasse oder Struktur ist so genannte *überladen* den Operator.  
  
### <a name="to-call-an-operator-procedure"></a>Aufrufen eine Operatorprozedur  
  
1.  Verwenden Sie das Symbol "Operator" in einem Ausdruck auf die übliche Weise.  
  
2.  Achten Sie darauf, dass die Datentypen der Operanden für den Operator an, und in der richtigen Reihenfolge sind.  
  
3.  Der Operator trägt dazu bei, den Wert des Ausdrucks wie erwartet.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>Eine Konvertierungsoperatorprozedur aufrufen  
  
1.  Verwendung `CType` innerhalb eines Ausdrucks.  
  
2.  Achten Sie darauf, dass die Datentypen der Operanden für die Konvertierung an, und in der richtigen Reihenfolge sind.  
  
3.  `CType` Ruft die Konvertierungsoperatorprozedur auf und gibt den konvertierten Wert zurück.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei <xref:System.TimeSpan> Strukturen, diese zusammenfügt und speichert das Ergebnis in einer dritten <xref:System.TimeSpan> Struktur. Die <xref:System.TimeSpan> Struktur definiert Operatorprozeduren mehrere Standardoperatoren überladen.  
  
 [!code-vb[VbVbcnProcedures#29](./codesnippet/VisualBasic/how-to-call-an-operator-procedure_1.vb)]  
  
 Da <xref:System.TimeSpan> überlädt den Standard `+` -Operator, wird im vorherige Beispiel eine Operatorprozedur an, wenn den Wert des berechnet `combinedSpan`.  
  
 Ein Beispiel für eine Konvertierungsoperatorprozedur aufrufen, finden Sie unter [Vorgehensweise: Verwenden Sie eine Klasse, dass Operatoren definiert](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Achten Sie darauf, dass die Klasse oder Struktur, die Sie verwenden den Operator definiert, die, den Sie verwenden möchten.  
  
## <a name="see-also"></a>Siehe auch  
 [Operatorprozeduren](./operator-procedures.md)  
 [Gewusst wie: Definieren eines Operators](./how-to-define-an-operator.md)  
 [Gewusst wie: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)  
 [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
