---
title: 'Gewusst wie: Verwenden einer Klasse, die Operatoren definiert'
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
ms.openlocfilehash: 9ec4b4c07910100dd02cc86e882b44aa7dbd2ced
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346037"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Gewusst wie: Verwenden einer Klasse, die Operatoren definiert (Visual Basic)
Wenn Sie eine Klasse oder Struktur verwenden, die eigene Operatoren definiert, können Sie von Visual Basic aus auf diese Operatoren zugreifen.  
  
 Die Definition eines Operators für eine Klasse oder Struktur wird auch als *überladen* des Operators bezeichnet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird auf die SQL-Struktur <xref:System.Data.SqlTypes.SqlString>zugegriffen, die die Konvertierungs Operatoren ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)) in beide Richtungen zwischen einer SQL-Zeichenfolge und einer Visual Basic Zeichenfolge definiert. Verwenden Sie `CType(`*SQL-Zeichen folgen Ausdruck*`String)`, um eine SQL-Zeichenfolge in eine Visual Basic Zeichenfolge zu konvertieren, und `CType(`*Visual Basic Zeichen folgen Ausdruck*<xref:System.Data.SqlTypes.SqlString>, um in die andere Richtung zu konvertieren.`)`  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 Die <xref:System.Data.SqlTypes.SqlString>-Struktur definiert einen Konvertierungs Operator ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)) von `String` bis <xref:System.Data.SqlTypes.SqlString> und einen anderen von <xref:System.Data.SqlTypes.SqlString> zu `String`. Die-Anweisung, die `title` zuweist, `jobTitle` den ersten Operator verwendet, und der <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Funktions aufrufter verwendet den zweiten.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Stellen Sie sicher, dass die verwendete Klasse oder Struktur den Operator definiert, den Sie verwenden möchten. Gehen Sie nicht davon aus, dass die Klasse oder Struktur jeden Operator definiert hat, der für das überladen verfügbar ist. Eine Liste der verfügbaren Operatoren finden Sie unter [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Fügen Sie die entsprechende `Imports`-Anweisung für die SQL-Zeichenfolge am Anfang der Quelldatei ein (in diesem Fall <xref:System.Data.SqlTypes>).  
  
 Das Projekt muss Verweise auf "System. Data" und "System. xml" aufweisen.  
  
## <a name="see-also"></a>Siehe auch

- [Operatorprozeduren](./operator-procedures.md)
- [Gewusst wie: Definieren eines Operators](./how-to-define-an-operator.md)
- [Gewusst wie: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)
- [Gewusst wie: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)
- [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)
- [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)
- [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
