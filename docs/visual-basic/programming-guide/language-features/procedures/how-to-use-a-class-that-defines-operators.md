---
title: 'Vorgehensweise: Verwenden einer Klasse, die Operatoren definiert'
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
ms.openlocfilehash: 083916a420bf4ad182536363ea46448f6b4c1da5
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071351"
---
# <a name="how-to-use-a-class-that-defines-operators-visual-basic"></a>Gewusst wie: Verwenden einer Klasse, die Operatoren definiert (Visual Basic)

Wenn Sie eine Klasse oder Struktur verwenden, die eigene Operatoren definiert, können Sie von Visual Basic aus auf diese Operatoren zugreifen.  
  
 Die Definition eines Operators für eine Klasse oder Struktur wird auch als *überladen* des Operators bezeichnet.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird auf die SQL-Struktur zugegriffen <xref:System.Data.SqlTypes.SqlString> , die die Konvertierungs Operatoren ([CType-Funktion](../../../language-reference/functions/ctype-function.md)) in beide Richtungen zwischen einer SQL-Zeichenfolge und einer Visual Basic Zeichenfolge definiert. Verwenden Sie `CType(` den *SQL-Zeichen folgen Ausdruck*, `String)` um eine SQL-Zeichenfolge in eine Visual Basic Zeichenfolge zu konvertieren, und `CType(` *Visual Basic Zeichen folgen Ausdruck*, <xref:System.Data.SqlTypes.SqlString> `)` um in die andere Richtung zu konvertieren  
  
 [!code-vb[VbVbcnProcedures#30](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#30)]  
  
 [!code-vb[VbVbcnProcedures#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#31)]  
  
 Die <xref:System.Data.SqlTypes.SqlString> -Struktur definiert einen Konvertierungs Operator ([CType-Funktion](../../../language-reference/functions/ctype-function.md)) von `String` bis <xref:System.Data.SqlTypes.SqlString> und einen anderen von <xref:System.Data.SqlTypes.SqlString> zu `String` . Die-Anweisung, die zuweist, verwendet `title` `jobTitle` den ersten Operator, und der <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> Funktions Aufrufwert verwendet den zweiten.  
  
## <a name="compile-the-code"></a>Kompilieren des Codes  

 Stellen Sie sicher, dass die verwendete Klasse oder Struktur den Operator definiert, den Sie verwenden möchten. Gehen Sie nicht davon aus, dass die Klasse oder Struktur jeden Operator definiert hat, der für das überladen verfügbar ist. Eine Liste der verfügbaren Operatoren finden Sie unter [Operator Statement](../../../language-reference/statements/operator-statement.md).  
  
 Fügen Sie die entsprechende- `Imports` Anweisung für die SQL-Zeichenfolge am Anfang der Quelldatei ein (in diesem Fall <xref:System.Data.SqlTypes> ).  
  
 Das Projekt muss über Verweise auf System. Data und System.XML verfügen.  
  
## <a name="see-also"></a>Siehe auch

- [Operatorprozeduren](./operator-procedures.md)
- [Vorgehensweise: Definieren eines Operators](./how-to-define-an-operator.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)
- [Vorgehensweise: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)
- [Widening](../../../language-reference/modifiers/widening.md)
- [Narrowing](../../../language-reference/modifiers/narrowing.md)
- [Structure Statement](../../../language-reference/statements/structure-statement.md)
- [Vorgehensweise: Deklarieren einer Struktur](../data-types/how-to-declare-a-structure.md)
- [Implizite und explizite Konvertierungen](../data-types/implicit-and-explicit-conversions.md)
- [Widening and Narrowing Conversions](../data-types/widening-and-narrowing-conversions.md)
