---
title: 'Vorgehensweise: Verwenden Sie eine Klasse, die Operatoren (Visual Basic) definiert.'
ms.date: 07/20/2015
helpviewer_keywords:
- operator procedures [Visual Basic], calling
- procedures [Visual Basic], operator
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
ms.openlocfilehash: bd512adf2f06ed0fbd3d36ed3175a0928bf1c57c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829407"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Vorgehensweise: Verwenden Sie eine Klasse, die Operatoren (Visual Basic) definiert.
Wenn Sie eine Klasse oder Struktur, die eine eigene Operatoren definiert verwenden, können Sie diese Operatoren in Visual Basic zugreifen.  
  
 Definieren eines Operators in einer Klasse oder Struktur ist die Abkürzung *überladen* den Operator.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel greift auf die SQL-Struktur <xref:System.Data.SqlTypes.SqlString>, das die Konvertierungsoperatoren definiert ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)) in beide Richtungen zwischen einer SQL-Zeichenfolge und eine Visual Basic-Zeichenfolge. Verwendung `CType(` *SQL Zeichenfolgenausdruck*, `String)` zum Konvertieren von einer SQL-Zeichenfolge in eine Visual Basic-Zeichenfolge, und `CType(` *Visual Basic-Ausdruck*, <xref:System.Data.SqlTypes.SqlString> `)` in die andere Richtung konvertiert.  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 Die <xref:System.Data.SqlTypes.SqlString> Struktur definiert einen Konvertierungsoperator ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)) von `String` zu <xref:System.Data.SqlTypes.SqlString> und eine andere von <xref:System.Data.SqlTypes.SqlString> zu `String`. Die Anweisung, zuweist `title` zu `jobTitle` verwendet den ersten Operator und die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Funktionsaufruf mithilfe des zweiten.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Achten Sie darauf, dass die Klasse oder Struktur, die Sie verwenden den Operator definiert, die, den Sie verwenden möchten. Gehen Sie nicht davon aus, für die Klasse oder Struktur jeder Operator zur Überladung definiert wurde. Eine Liste der Operatoren verfügbar sind, finden Sie unter [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Fügen Sie die entsprechenden `Imports` -Anweisung für die SQL-Zeichenfolge am Anfang der Quelldatei (in diesem Fall <xref:System.Data.SqlTypes>).  
  
 Das Projekt muss es sich um Verweise auf "System.Data" und "System.xml" enthalten.  
  
## <a name="see-also"></a>Siehe auch

- [Operatorprozeduren](./operator-procedures.md)
- [Vorgehensweise: Definieren eines Operators](./how-to-define-an-operator.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)
- [Vorgehensweise: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)
- [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Vorgehensweise: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
