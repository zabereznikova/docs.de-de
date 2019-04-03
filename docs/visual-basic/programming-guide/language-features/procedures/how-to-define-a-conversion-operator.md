---
title: 'Vorgehensweise: Definieren eines Konvertierungsoperators (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 54203dfa-c24b-463f-9942-d5153e89e762
ms.openlocfilehash: cf7bfdd09c7f3429f9c730a7aec34b24af3f2e9f
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829225"
---
# <a name="how-to-define-a-conversion-operator-visual-basic"></a>Vorgehensweise: Definieren eines Konvertierungsoperators (Visual Basic)
Wenn Sie eine Klasse oder Struktur definiert haben, können Sie einen Operator für die Konvertierung zwischen dem Typ der Klasse oder Struktur und einen anderen Datentyp definieren (z. B. `Integer`, `Double`, oder `String`).  
  
 Definieren Sie die typkonvertierung als eine [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) Prozedur innerhalb der Klasse oder Struktur. Alle Konvertierungsprozeduren muss `Public Shared`, und geben jeweils [Widening](../../../../visual-basic/language-reference/modifiers/widening.md) oder [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md).  
  
 Definieren eines Operators in einer Klasse oder Struktur ist die Abkürzung *überladen* den Operator.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert Konvertierungsoperatoren zwischen einer Struktur mit dem Namen `digit` und `Byte`.  
  
 [!code-vb[VbVbcnProcedures#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#27)]  
  
 Sie können die Struktur testen `digit` durch den folgenden Code.  
  
 [!code-vb[VbVbcnProcedures#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#28)]  
  
## <a name="see-also"></a>Siehe auch

- [Operatorprozeduren](./operator-procedures.md)
- [Vorgehensweise: Definieren eines Operators](./how-to-define-an-operator.md)
- [Vorgehensweise: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)
- [Vorgehensweise: Verwenden Sie eine Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md)
- [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Vorgehensweise: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
