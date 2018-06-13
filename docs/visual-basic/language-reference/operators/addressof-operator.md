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
ms.openlocfilehash: 7c229c32a3b295b4dbfe50ca2abc60d4ad5f2145
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597786"
---
# <a name="addressof-operator-visual-basic"></a>AddressOf-Operator (Visual Basic)
Erstellt eine Delegatinstanz einer Prozedur, die bestimmte Prozedur verweist.  
  
## <a name="syntax"></a>Syntax  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Teile  
 `procedurename`  
 Erforderlich. Gibt an, wie durch den Delegaten neu erstellte Prozedur verwiesen werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `AddressOf` Operator erstellt ein Funktionsdelegat, der auf die angegebene Funktion zeigt `procedurename`. Wenn ist die angegebene Prozedur an, dass die Instanz und die Methode eine Instanzmethode der Funktionsdelegat bezieht. Klicken Sie dann wird den Funktionsdelegat aufgerufen wird, die angegebene Methode der angegebenen Instanz aufgerufen.  
  
 Die `AddressOf` -Operator kann verwendet werden, wie der Operand eines Delegatkonstruktors oder in einem Kontext, in dem der Typ des Delegaten vom Compiler bestimmt werden kann, verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `AddressOf` Operator zum Festlegen eines Delegaten behandeln die `Click` Ereignis einer Schaltfläche.  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `AddressOf` Operator, um die Autostart-Funktion für einen Thread zu kennzeichnen.  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)
