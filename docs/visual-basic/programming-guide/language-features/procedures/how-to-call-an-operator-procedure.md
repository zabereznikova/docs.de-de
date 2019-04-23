---
title: 'Vorgehensweise: Aufrufen einer Operatorprozedur (Visual Basic)'
ms.date: 07/20/2015
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
ms.openlocfilehash: d68781aa12ab7c1c717031ca252c5f3120649edc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335484"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Vorgehensweise: Aufrufen einer Operatorprozedur (Visual Basic)
Sie aufrufen mit dem Symbol "Operator" in einem Ausdruck eine Operatorprozedur. Im Falle eines Konvertierungsoperators rufen Sie die [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) zum Konvertieren eines Werts aus einem Datentyp in einen anderen.  
  
 Sie Operatorprozeduren nicht explizit aufrufen. Sie verwenden einfach den Operator an, oder die `CType` -Funktion in einer zuweisungsanweisung oder ein Ausdruck, der die gleiche Weise, die Sie normalerweise einen Operator verwenden. Visual Basic ermöglicht den Aufruf an die Operatorprozedur an.  
  
 Definieren eines Operators in einer Klasse oder Struktur ist die Abkürzung *überladen* den Operator.  
  
### <a name="to-call-an-operator-procedure"></a>Zum Aufrufen einer Operatorprozedur  
  
1. Verwenden Sie das Symbol "Operator" in einem Ausdruck, auf die normale Weise.  
  
2. Achten Sie darauf, dass die Datentypen der Operanden für den Operator an, und in der richtigen Reihenfolge sind.  
  
3. Der Operator unterstützt den Wert des Ausdrucks wie erwartet.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>Eine Konvertierungsoperatorprozedur aufrufen  
  
1. Verwendung `CType` innerhalb eines Ausdrucks.  
  
2. Achten Sie darauf, dass die Datentypen der Operanden für die Konvertierung an, und in der richtigen Reihenfolge sind.  
  
3. `CType` Ruft die Konvertierungsoperatorprozedur und gibt den konvertierten Wert zurück.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt zwei <xref:System.TimeSpan> Strukturen, diese zusammenfügt und speichert das Ergebnis in einer dritten <xref:System.TimeSpan> Struktur. Die <xref:System.TimeSpan> Struktur definiert Operatorprozeduren mehrere Standardoperatoren überladen.  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 Da <xref:System.TimeSpan> überlädt den Standard `+` -Operator, wird das vorherige Beispiel eine Operatorprozedur an, wenn den Wert des berechnet `combinedSpan`.  
  
 Ein Beispiel für eine Konvertierungsoperatorprozedur aufrufen, finden Sie unter [Vorgehensweise: Verwenden Sie eine Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Achten Sie darauf, dass die Klasse oder Struktur, die Sie verwenden den Operator definiert, die, den Sie verwenden möchten.  
  
## <a name="see-also"></a>Siehe auch

- [Operatorprozeduren](./operator-procedures.md)
- [Vorgehensweise: Definieren eines Operators](./how-to-define-an-operator.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)
- [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Vorgehensweise: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
