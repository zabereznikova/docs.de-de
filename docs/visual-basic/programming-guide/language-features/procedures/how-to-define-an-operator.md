---
title: 'Gewusst wie: Definieren eines Operators (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- operators [Visual Basic], defining
- procedures [Visual Basic], operator
- Visual Basic code, operators
- syntax [Visual Basic], Operator procedures
- operators [Visual Basic], overloading
- operator procedures [Visual Basic], about operator procedures
- return values [Visual Basic], Operator procedures
- operator overloading
ms.assetid: d4b0e253-092a-4e6e-9fe2-01f562140a29
ms.openlocfilehash: 1f5a020a710cecdfd8722a9fca0a8b329697eced
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805398"
---
# <a name="how-to-define-an-operator-visual-basic"></a>Gewusst wie: Definieren eines Operators (Visual Basic)
Wenn Sie eine Klasse oder Struktur definiert haben, können Sie das Verhalten eines standard-Operators definieren (z. B. `*`, `<>`, oder `And`) Wenn einer oder beide der Operanden vom Typ der Klasse oder Struktur ist.  
  
 Definieren Sie den standard-Operator als einer Operatorprozedur innerhalb der Klasse oder Struktur. Alle Operatorprozeduren muss `Public` `Shared`.  
  
 Definieren eines Operators in einer Klasse oder Struktur ist so genannte *überladen* den Operator.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert die `+` -Operator für eine Struktur aufgerufen `height`. Die Struktur verwendet in Fuß und Zoll gemessen Höhe. Eine *Zoll* handelt 2,54 Zentimeter und mindestens ein *foot* beträgt 12 Zoll. Um sicherzustellen, dass normalisierte Werte (Zoll < 12.0), der Konstruktor führt *modulo* arithmetische 12. Die `+` -Operator verwendet den Konstruktor, um normalisierte Werte zu generieren.  
  
 [!code-vb[VbVbcnProcedures#25](./codesnippet/VisualBasic/how-to-define-an-operator_1.vb)]  
  
 Sie können die Struktur testen `height` durch den folgenden Code.  
  
 [!code-vb[VbVbcnProcedures#26](./codesnippet/VisualBasic/how-to-define-an-operator_2.vb)]  
  
 Weitere Informationen und Beispiele finden Sie unter [Operator Overloading in Visual Basic 2005 (Operatorüberladung in Visual Basic 2005)](https://msdn.microsoft.com/library/ms379613(v=vs.80).aspx).  
  
## <a name="see-also"></a>Siehe auch  
 [Operatorprozeduren](./operator-procedures.md)  
 [Gewusst wie: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)  
 [Gewusst wie: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)  
 [Gewusst wie: Verwenden einer Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md)  
 [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)  
 [Mod-Operator](../../../../visual-basic/language-reference/operators/mod-operator.md)
