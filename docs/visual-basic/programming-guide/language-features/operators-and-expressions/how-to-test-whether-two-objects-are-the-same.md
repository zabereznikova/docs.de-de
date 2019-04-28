---
title: 'Vorgehensweise: Überprüfen Sie, ob zwei Objekte der gleichen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- variables [Visual Basic], reference
- Is operator [Visual Basic], comparing objects
- reference variables [Visual Basic]
- variables [Visual Basic], referring to same object
- objects [Visual Basic], variables referring to same
- Visual Basic code, operators
ms.assetid: f760e828-8704-4256-bc2d-c22a4c93b524
ms.openlocfilehash: dbb268175d197e7b931af45a98f3a273c593e5a3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61864376"
---
# <a name="how-to-test-whether-two-objects-are-the-same-visual-basic"></a>Vorgehensweise: Überprüfen Sie, ob zwei Objekte der gleichen (Visual Basic)
Wenn Sie zwei Variablen, die auf Objekte verweisen verfügen, verwenden Sie entweder die `Is` oder `IsNot` Operator oder beides, um zu bestimmen, ob sie an dieselbe Instanz verweisen.  
  
### <a name="to-test-whether-two-objects-are-the-same"></a>Zum Überprüfen, ob zwei Objekte gleich sind.  
  
- Verwenden der [Is Operator](../../../../visual-basic/language-reference/operators/is-operator.md) oder [IsNot-Operator](../../../../visual-basic/language-reference/operators/isnot-operator.md) mit den beiden Variablen als Operanden.  
  
     [!code-vb[VbVbalrOperators#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#69)]  
  
 Sie möchten eine bestimmte Aktion ausgeführt abhängig davon, ob zwei Objekte auf dieselbe Instanz verweisen. Im vorherige Beispiel vergleicht Steuerelement `c` für das aktive Steuerelement im Formular `f`. Wenn keine aktiven Steuerelement vorhanden ist, oder ist es ein, aber es ist nicht der gleichen Instanz des Steuerelements als `c`, und klicken Sie dann die `If` Anweisung fehl, und die Prozedur zurückgegeben werden, ohne weitere Verarbeitung.  
  
 Gibt an, ob Sie verwenden `Is` oder `IsNot` persönliche aus Gründen der Bequemlichkeit für Sie ist. Eine möglicherweise einfacher, als das andere in einem bestimmten Ausdruck zu lesen.  
  
## <a name="see-also"></a>Siehe auch

- [Vergleichsoperatoren in Visual Basic](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
