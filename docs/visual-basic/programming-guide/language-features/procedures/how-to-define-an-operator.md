---
title: 'Vorgehensweise: Definieren eines Operators (Visual Basic)'
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
ms.openlocfilehash: 14aa25de78eb357f8474d3828aa45e48e7a4f9c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59126112"
---
# <a name="how-to-define-an-operator-visual-basic"></a>Vorgehensweise: Definieren eines Operators (Visual Basic)
Wenn Sie eine Klasse oder Struktur definiert haben, können Sie das Verhalten von Standardoperatoren definieren (z. B. `*`, `<>`, oder `And`) Wenn eine oder beide der Operanden vom Typ der Klasse oder Struktur ist.  
  
 Definieren Sie den standard-Operator als einer Operatorprozedur innerhalb der Klasse oder Struktur. Alle Operatorprozeduren muss `Public` `Shared`.  
  
 Definieren eines Operators in einer Klasse oder Struktur ist die Abkürzung *überladen* den Operator.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert die `+` Operator für eine Struktur namens `height`. Die Struktur wird verwendet, gemessen in Fuß und Zoll Höhe. Eine *Zoll* ist 2,54 Zentimeter, *foot* ist 12 Zoll. Um sicherzustellen, dass normalisierte Werte (Zoll < 12.0), der Konstruktor führt *modulo* arithmetische 12. Die `+` Operator wird der Konstruktor verwendet, um normalisierte Werte zu generieren.  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 Sie können die Struktur testen `height` durch den folgenden Code.  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a>Siehe auch

- [Operatorprozeduren](./operator-procedures.md)
- [Vorgehensweise: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)
- [Vorgehensweise: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)
- [Vorgehensweise: Verwenden Sie eine Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md)
- [Operator-Anweisung](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Vorgehensweise: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Mod-Operator](../../../../visual-basic/language-reference/operators/mod-operator.md)
