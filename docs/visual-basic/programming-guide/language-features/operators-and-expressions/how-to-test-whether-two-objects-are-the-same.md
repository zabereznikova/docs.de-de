---
title: 'Gewusst wie: Überprüfen, ob zwei Objekte identisch sind'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: 22e8e1e688d9e3bc3804899103ee78814aac235b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343622"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Gewusst wie: Überprüfen, ob zwei Objekte identisch sind (Visual Basic)
Wenn Sie über zwei Variablen verfügen, die auf-Objekte verweisen, können Sie entweder den `Is`-oder `IsNot`-Operator oder beides verwenden, um zu bestimmen, ob Sie auf dieselbe Instanz verweisen.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>So testen Sie, ob zwei Objekte identisch sind  
  
- Verwenden Sie den [is-Operator](../../../../visual-basic/language-reference/operators/is-operator.md) oder den [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) mit den beiden Variablen als Operanden.  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 Möglicherweise möchten Sie abhängig davon, ob zwei-Objekte auf dieselbe Instanz verweisen, eine bestimmte Aktion durchführen. Im vorangehenden Beispiel wird die Steuerelement `c` mit dem aktiven Steuerelement im Formular `f`verglichen. Wenn kein aktives Steuerelement vorhanden ist, oder wenn es ein Steuerelement ist, aber nicht die gleiche Steuerelement Instanz wie `c`, dann schlägt die `If` Anweisung fehl, und die Prozedur wird ohne weitere Verarbeitung zurückgegeben.  
  
 Unabhängig davon, ob Sie `Is` oder `IsNot` verwenden, sind Sie für Sie persönlich. Eine ist möglicherweise einfacher zu lesen als die andere in einem gegebenen Ausdruck.  
  
## <a name="see-also"></a>Siehe auch

- [Vergleichs Operatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
