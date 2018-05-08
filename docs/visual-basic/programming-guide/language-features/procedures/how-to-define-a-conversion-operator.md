---
title: 'Gewusst wie: Definieren eines Konvertierungsoperators (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 24bbe41af67f757cae661a78d482a423ff0ffd85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>Gewusst wie: Definieren eines Konvertierungsoperators (Visual Basic)
Wenn Sie eine Klasse oder Struktur definiert haben, können Sie einen Operator für die Konvertierung zwischen dem Typ der Klasse oder Struktur und einen anderen Datentyp definieren (z. B. `Integer`, `Double`, oder `String`).  
  
 Definieren Sie die Konvertierung vom Typ als ein [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) Prozedur innerhalb der Klasse oder Struktur. Alle Konvertierungsprozeduren muss `Public Shared`, und geben jeweils [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) oder [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).  
  
 Definieren eines Operators in einer Klasse oder Struktur ist so genannte *überladen* den Operator.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert die Operatoren für die Konvertierung zwischen einer Struktur mit dem Namen `digit` und ein `Byte`.  
  
 [!code-vb[VbVbcnProcedures#27](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_1.vb)]  
  
 Sie können die Struktur testen `digit` durch den folgenden Code.  
  
 [!code-vb[VbVbcnProcedures#28](./codesnippet/VisualBasic/how-to-define-a-conversion-operator_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Operatorprozeduren](./operator-procedures.md)  
 [Gewusst wie: Definieren eines Operators](./how-to-define-an-operator.md)  
 [Gewusst wie: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)  
 [Gewusst wie: Verwenden einer Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md)  
 [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
