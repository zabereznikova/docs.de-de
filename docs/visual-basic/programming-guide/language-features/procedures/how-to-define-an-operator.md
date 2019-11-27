---
title: 'Gewusst wie: Definieren eines Operators'
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
ms.openlocfilehash: b99af8ff4d5428f1749bfc1a4c51a136f12405ee
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344875"
---
# <a name="how-to-define-an-operator-visual-basic"></a>Gewusst wie: Definieren eines Operators (Visual Basic)
Wenn Sie eine Klasse oder Struktur definiert haben, können Sie das Verhalten eines Standard Operators (z. b. `*`, `<>`oder `And`) definieren, wenn mindestens einer der Operanden vom Typ der Klasse oder Struktur ist.  
  
 Definieren Sie den Standard Operator als Operator Prozedur innerhalb der Klasse oder Struktur. Alle Operator Prozeduren müssen `Shared``Public` werden.  
  
 Die Definition eines Operators für eine Klasse oder Struktur wird auch als *überladen* des Operators bezeichnet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `+`-Operator für eine Struktur mit dem Namen `height`definiert. Die Struktur verwendet Höhen, gemessen in Höhe und Zoll. Ein *Zoll* beträgt 2,54 Zentimeter und ein *Fuß* ist 12 Zoll. Um normalisierte Werte (Zoll < 12,0) sicherzustellen, führt der Konstruktor *Modulo* 12-Arithmetik aus. Der `+`-Operator verwendet den-Konstruktor, um normalisierte Werte zu generieren.  
  
 [!code-vb[VbVbcnProcedures#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#25)]  
  
 Sie können die Struktur `height` mit dem folgenden Code testen.  
  
 [!code-vb[VbVbcnProcedures#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#26)]  

## <a name="see-also"></a>Siehe auch

- [Operatorprozeduren](./operator-procedures.md)
- [Gewusst wie: Definieren eines Konvertierungsoperators](./how-to-define-a-conversion-operator.md)
- [Gewusst wie: Aufrufen einer Operatorprozedur](./how-to-call-an-operator-procedure.md)
- [Gewusst wie: Verwenden einer Klasse, die Operatoren definiert](./how-to-use-a-class-that-defines-operators.md)
- [Operator Statement](../../../../visual-basic/language-reference/statements/operator-statement.md)
- [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)
- [Gewusst wie: Deklarieren einer Struktur](../../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Mod-Operator](../../../../visual-basic/language-reference/operators/mod-operator.md)
