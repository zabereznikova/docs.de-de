---
title: 'Vorgehensweise: Überprüfen, ob zwei Objekte identisch sind'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: b215225dbc2d8c0d2bdfe2206e5d4a4f1faa6d0c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403420"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Gewusst wie: Überprüfen, ob zwei Objekte identisch sind (Visual Basic)
Wenn Sie über zwei Variablen verfügen, die auf-Objekte verweisen, können Sie entweder den-oder den- `Is` `IsNot` Operator oder beides verwenden, um zu bestimmen, ob Sie auf dieselbe Instanz verweisen.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>So testen Sie, ob zwei Objekte identisch sind  
  
- Verwenden Sie den [is-Operator](../../../language-reference/operators/is-operator.md) oder den [IsNot-Operator](../../../language-reference/operators/isnot-operator.md) mit den beiden Variablen als Operanden.  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 Möglicherweise möchten Sie abhängig davon, ob zwei-Objekte auf dieselbe Instanz verweisen, eine bestimmte Aktion durchführen. Im vorangehenden Beispiel wird das Steuerelement `c` mit dem aktiven Steuerelement auf dem Formular verglichen `f` . Wenn kein aktives Steuerelement vorhanden ist, oder wenn es ein Steuerelement ist, aber nicht die gleiche Steuerelement Instanz wie `c` , `If` schlägt die Anweisung fehl, und die Prozedur gibt ohne weitere Verarbeitung zurück.  
  
 `Is`Unabhängig davon, ob Sie oder verwenden `IsNot` , sind Sie für Sie persönlich. Eine ist möglicherweise einfacher zu lesen als die andere in einem gegebenen Ausdruck.  
  
## <a name="see-also"></a>Weitere Informationen

- [Comparison Operators in Visual Basic](comparison-operators.md)
