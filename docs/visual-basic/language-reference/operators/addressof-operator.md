---
title: AddressOf-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 4f4f88551b6708ac3d0ee0f0f5bdcbdec1dfaaa9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54721067"
---
# <a name="addressof-operator-visual-basic"></a>AddressOf-Operator (Visual Basic)
Erstellt eine Instanz eines Delegaten, die auf bestimmte Prozedur verweist.  
  
## <a name="syntax"></a>Syntax  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Teile  
 `procedurename`  
 Erforderlich. Gibt an, wie durch den Delegaten für die neu erstellte Prozedur verwiesen werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `AddressOf` Operator erstellt eine zu delegierende Funktion, die auf die angegebene Funktion zeigt `procedurename`. Wenn ist die angegebene Prozedur an, dass eine Instanzmethode klicken Sie dann den Funktionsdelegaten auf die Instanz und die Methode verweist. Klicken Sie dann beim Aufrufen der Funktionsdelegaten wird die angegebene Methode der angegebenen Instanz aufgerufen.  
  
 Die `AddressOf` Operator kann verwendet werden, wie der Operand eines Delegatkonstruktors oder in einem Kontext, in dem der Typ des Delegaten vom Compiler bestimmt werden kann, verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `AddressOf` Operator zum Festlegen eines Delegaten behandeln die `Click` -Ereignis einer Schaltfläche.  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `AddressOf` Operator, um die Startfunktion für einen Thread bezeichnet.  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)
