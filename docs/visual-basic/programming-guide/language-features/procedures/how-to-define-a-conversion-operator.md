---
title: 'Gewusst wie: Definieren eines Konvertierungsoperators'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: 0ff95390206947e5a28f7a5b85547b496746a9cc
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344896"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>Gewusst wie: Definieren eines Konvertierungsoperators (Visual Basic)
Wenn Sie eine Klasse oder Struktur definiert haben, können Sie einen Typkonvertierungs Operator zwischen dem Typ der Klasse oder Struktur und einem anderen Datentyp (z. b. `Integer`, `Double`oder `String`) definieren.  
  
 Definieren Sie die Typkonvertierung als [CType-Funktions](../../../../visual-basic/language-reference/functions/ctype-function.md) Prozedur innerhalb der Klasse oder Struktur. Alle Konvertierungs Prozeduren müssen `Public Shared`werden, und jeder muss entweder eine [Erweiterung](../../../../visual-basic/language-reference/modifiers/widening.md) oder eine [Einschränkung](../../../../visual-basic/language-reference/modifiers/narrowing.md)angeben.  
  
 Die Definition eines Operators für eine Klasse oder Struktur wird auch als *überladen* des Operators bezeichnet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden Konvertierungs Operatoren zwischen einer Struktur namens `digit` und einer `Byte`definiert.  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 Sie können die Struktur `digit` mit dem folgenden Code testen.  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Siehe auch

- [Operatorprozeduren](./operator-procedures.md)
- [Gewusst wie: Definieren eines Operators](./how-to-define-an-operator.md)
- [Gewusst wie: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)
- [Gewusst wie: Verwenden einer Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md)
- [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
