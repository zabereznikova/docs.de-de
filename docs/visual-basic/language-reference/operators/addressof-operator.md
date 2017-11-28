---
title: AddressOf-Operator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 52560a2d9071373fd28f7aad2e485da08324656d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
