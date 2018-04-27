---
title: 'Gewusst wie: Verwenden einer Klasse, die Operatoren definiert (Visual Basic)'
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
- procedures [Visual Basic], calling
- examples [Visual Basic], CType
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 7e0bcfaeca638dfabb841a9e935b872f76fdf957
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Gewusst wie: Verwenden einer Klasse, die Operatoren definiert (Visual Basic)
Wenn Sie eine Klasse oder Struktur, die ihre eigenen Operatoren definiert verwenden, können Sie diese Operatoren in Visual Basic zugreifen.  
  
 Definieren eines Operators in einer Klasse oder Struktur ist so genannte *überladen* den Operator.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel greift auf die SQL-Struktur <xref:System.Data.SqlTypes.SqlString>, die die Konvertierungsoperatoren definiert ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)) in beide Richtungen zwischen einer SQL-Zeichenfolge und eine Visual Basic-Zeichenfolge. Verwendung `CType(` *SQL-Zeichenfolgenausdruck*, `String)` zum Konvertieren einer SQL-Zeichenfolge in eine Visual Basic-Zeichenfolge und `CType(` *Visual Basic-Zeichenfolgenausdruck*, <xref:System.Data.SqlTypes.SqlString> `)` in die andere Richtung konvertiert.  
  
 [!code-vb[VbVbcnProcedures#30](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures#31](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 Die <xref:System.Data.SqlTypes.SqlString> Struktur definiert einen Konvertierungsoperator ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)) von `String` auf <xref:System.Data.SqlTypes.SqlString> und einem anderen <xref:System.Data.SqlTypes.SqlString> auf `String`. Die Anweisung, zuweist `title` auf `jobTitle` binärencoder wird der erste Operator und die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Funktionsaufruf mithilfe des zweiten.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Achten Sie darauf, dass die Klasse oder Struktur, die Sie verwenden den Operator definiert, die, den Sie verwenden möchten. Führen Sie Sie nicht davon gehen Sie aus, dass die Klasse oder Struktur jeder Operator überladen zur definiert wurde. Eine Liste der verfügbaren Operatoren, finden Sie unter [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Fügen Sie die entsprechenden `Imports` -Anweisung für die SQL-Zeichenfolge am Anfang der Quelldatei (in diesem Fall <xref:System.Data.SqlTypes>).  
  
 Das Projekt benötigen Verweise auf "System.Data" und "System.xml".  
  
## <a name="see-also"></a>Siehe auch  
 [Operatorprozeduren](./operator-procedures.md)  
 [Gewusst wie: Definieren eines Operators](./how-to-define-an-operator.md)  
 [Gewusst wie: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)  
 [Gewusst wie: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)  
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)  
 [Narrowing](../../../../visual-basic/language-reference/modifiers/narrowing.md)  
 [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)  
 [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
