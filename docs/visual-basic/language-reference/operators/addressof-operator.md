---
title: AddressOf-Operator (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 04a7c5be9b890faea561c28715093a271cf9eaa8
ms.lasthandoff: 03/13/2017

---
# <a name="addressof-operator-visual-basic"></a>AddressOf-Operator (Visual Basic)
Erstellt eine Instanz eines Delegaten, die die Prozedur verweist.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Teile  
 `procedurename`  
 Erforderlich. Gibt an, wie durch die neu erstellte Delegaten verwiesen werden.  
  
## <a name="remarks"></a>Hinweise  
 Die `AddressOf` Operator erstellt einen Funktionsdelegaten, der auf die angegebene Funktion zeigt `procedurename`. Wenn ist die angegebene Prozedur eine Instanzenmethode der Funktionsdelegat sowohl auf die Instanz als auch auf die Methode verweist. Klicken Sie dann wird der Funktionsdelegat aufgerufen wird, die angegebene Methode der angegebenen Instanz aufgerufen.  
  
 Die `AddressOf` -Operator kann als Operand eines Delegatkonstruktors verwendet werden, oder es kann verwendet werden, in einem Kontext, in dem der Typ des Delegaten vom Compiler bestimmt werden kann.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `AddressOf` Operator zum Festlegen eines Delegaten behandeln die `Click` Ereignis einer Schaltfläche.  
  
 [!code-vb[VbVbalrDelegates&#8;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `AddressOf` Operator, um die Startfunktion für einen Thread bezeichnet.  
  
 [!code-vb[VbVbalrDelegates&#9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)
