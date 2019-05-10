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
ms.openlocfilehash: 6301228d786fe55e8851b6207dd84819671656f4
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649681"
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
