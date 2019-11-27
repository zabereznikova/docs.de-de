---
title: 'Gewusst wie: Aufrufen einer Operatorprozedur'
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
ms.openlocfilehash: a685be7cc3b346b271413e2c29faae5a839313f4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74340241"
---
# <a name="how-to-call-an-operator-procedure-visual-basic"></a>Gewusst wie: Aufrufen einer Operatorprozedur (Visual Basic)
Sie wenden eine Operator Prozedur mit dem Operator Symbol in einem Ausdruck an. Im Fall eines Konvertierungs Operators wird die [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md) aufgerufen, um einen Wert von einem Datentyp in einen anderen zu konvertieren.  
  
 Operator Prozeduren werden nicht explizit aufgerufen. Sie verwenden einfach den-Operator oder die `CType`-Funktion in einer Zuweisungsanweisung oder einem Ausdruck auf die gleiche Weise, wie Sie normalerweise einen Operator verwenden. Visual Basic führt den aufzurufenden Operator Prozedur Vorgang aus.  
  
 Die Definition eines Operators für eine Klasse oder Struktur wird auch als *überladen* des Operators bezeichnet.  
  
### <a name="to-call-an-operator-procedure"></a>So wenden Sie eine Operator Prozedur an  
  
1. Verwenden Sie das Operator Symbol in einem Ausdruck auf die übliche Weise.  
  
2. Stellen Sie sicher, dass die Datentypen der Operanden für den Operator und in der richtigen Reihenfolge geeignet sind.  
  
3. Der Operator trägt wie erwartet zum Wert des Ausdrucks bei.  
  
### <a name="to-call-a-conversion-operator-procedure"></a>So können Sie eine Konvertierungs Operator Prozedur aufzurufen  
  
1. Verwenden Sie `CType` innerhalb eines Ausdrucks.  
  
2. Stellen Sie sicher, dass die Datentypen der Operanden für die Konvertierung und in der richtigen Reihenfolge geeignet sind.  
  
3. `CType` Ruft die Konvertierungs Operator Prozedur auf und gibt den konvertierten Wert zurück.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden zwei <xref:System.TimeSpan> Strukturen erstellt, addiert, und das Ergebnis wird in einer dritten <xref:System.TimeSpan> Struktur gespeichert. Die <xref:System.TimeSpan> Struktur definiert Operator Prozeduren, um mehrere Standard Operatoren zu überladen.  
  
 [!code-vb[VbVbcnProcedures#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#29)]  
  
 Da <xref:System.TimeSpan> den Standard `+` Operator überlädt, wird im vorherigen Beispiel eine Operator Prozedur aufgerufen, wenn der Wert von `combinedSpan`berechnet wird.  
  
 Ein Beispiel für den Aufruf einer Konversations Operator Prozedur finden Sie unter Gewusst [wie: Verwenden einer Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md).  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Stellen Sie sicher, dass die verwendete Klasse oder Struktur den Operator definiert, den Sie verwenden möchten.  
  
## <a name="see-also"></a>Siehe auch

- [Operatorprozeduren](./operator-procedures.md)
- [Gewusst wie: Definieren eines Operators](./how-to-define-an-operator.md)
- [Gewusst wie: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)
- [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
