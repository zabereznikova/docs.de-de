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
ms.openlocfilehash: 098ca95687d8b0e9f4ac90d5c7e0df9a9a0ad950
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760376"
---
# <a name="addressof-operator-visual-basic"></a>AddressOf-Operator (Visual Basic)
Erstellt eine Delegatinstanz, die auf bestimmte Prozedur verweist.  
  
## <a name="syntax"></a>Syntax  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Teile  
 `procedurename`  
 Erforderlich. Gibt an, wie durch den neu erstellten Delegaten verwiesen werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `AddressOf` Operator erstellt einen Delegaten, der auf die Sub oder Funktion anhand des zeigt `procedurename`. Wenn die angegebene Prozedur ist, dass eine Instanzmethode klicken Sie dann den Delegaten auf die Instanz und die Methode verweist. Klicken Sie dann, wenn der Delegat aufgerufen wird, wird die angegebene Methode der angegebenen Instanz aufgerufen.  
  
 Die `AddressOf` Operator kann verwendet werden, wie der Operand eines Delegatkonstruktors oder in einem Kontext, in dem der Typ des Delegaten vom Compiler bestimmt werden kann, verwendet werden.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `AddressOf` Operator zum Festlegen eines Delegaten behandeln die `Click` -Ereignis einer Schaltfläche.  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `AddressOf` Operator, um die Startfunktion für einen Thread bezeichnet.  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Siehe auch

- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)
