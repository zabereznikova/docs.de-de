---
title: 'Gewusst wie: Verwenden einer Klasse, die Operatoren definiert (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- operator procedures, calling
- procedures, operator
- procedures, calling
- examples [Visual Basic], CType
- syntax, Operator procedures
- operators [Visual Basic], overloading
- return values, Operator procedures
- operator overloading
ms.assetid: 7ccce94a-6ca0-47d1-9f3f-13385d34f5d5
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b1db7c0b2a6fd8160baa48892b5f2214df24674e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Gewusst wie: Verwenden einer Klasse, die Operatoren definiert (Visual Basic)
Wenn Sie eine Klasse oder Struktur, die ihre eigenen Operatoren definiert verwenden, können Sie diese Operatoren aus zugreifen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].  
  
 Definieren eines Operators für eine Klasse oder Struktur ist die Abkürzung *überladen* des Operators.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel ruft die SQL-Struktur <xref:System.Data.SqlTypes.SqlString>, die die Konvertierungsoperatoren definiert ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)) in beide Richtungen zwischen einer SQL-Zeichenfolge und eine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Zeichenfolge.</xref:System.Data.SqlTypes.SqlString> Verwenden `CType(` *SQL-Zeichenfolgenausdruck*, `String)` konvertieren Sie eine SQL-Zeichenfolge, die eine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Zeichenfolge und `CType(` *Visual Basic-Zeichenfolgenausdruck*, <xref:System.Data.SqlTypes.SqlString> `)` für die Konvertierung in die andere Richtung.</xref:System.Data.SqlTypes.SqlString>  
  
 [!code-vb[VbVbcnProcedures&#30;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_1.vb)]  
  
 [!code-vb[VbVbcnProcedures&#31;](./codesnippet/VisualBasic/how-to-use-a-class-that-defines-operators_2.vb)]  
  
 Die <xref:System.Data.SqlTypes.SqlString>Struktur einen Konvertierungsoperator definiert ([CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)) von `String` , <xref:System.Data.SqlTypes.SqlString>und anderen von <xref:System.Data.SqlTypes.SqlString>, `String`.</xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString> </xref:System.Data.SqlTypes.SqlString> Die Anweisung, zuweist `title` auf `jobTitle` verwendet den ersten Operator, und die <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>-Funktionsaufruf verwendet das zweite.</xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Achten Sie darauf, dass die Klasse oder Struktur, die Sie verwenden den Operator definiert, den Sie verwenden möchten. Gehen Sie nicht davon aus, dass die Klasse oder Struktur jeder zum Überladen verfügbare Operator definiert wurde. Eine Liste der verfügbaren Operatoren finden Sie unter [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md).  
  
 Fügen Sie die entsprechenden `Imports` -Anweisung für die SQL-Zeichenfolge am Anfang der Quelldatei (in diesem Fall <xref:System.Data.SqlTypes>).</xref:System.Data.SqlTypes>  
  
 Das Projekt muss Verweise auf System.Data und System.XML enthalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Operatorprozeduren](./operator-procedures.md)   
 [Gewusst wie: Definieren eines Operators](./how-to-define-an-operator.md)   
 [Gewusst wie: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)   
 [Gewusst wie: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)   
 [Widening](../../../../visual-basic/language-reference/modifiers/widening.md)   
 [Einschränkende](../../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)   
 [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)   
 [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
