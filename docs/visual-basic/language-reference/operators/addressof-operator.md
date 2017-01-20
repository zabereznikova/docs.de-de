---
title: "AddressOf Operator (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AddressOf"
  - "vb.AddressOf"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "AddressOf operator"
  - "addresses, passing to API procedures"
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# AddressOf Operator (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Erstellt eine Instanz eines Prozedurdelegaten, die auf die bestimmte Prozedur verweist.  
  
## Syntax  
  
```  
  
AddressOf procedurename  
```  
  
## Teile  
 `procedurename`  
 Erforderlich.  Gibt die Prozedur an, auf die vom neu erstellten Prozedurdelegaten verwiesen werden soll.  
  
## Hinweise  
 Der Operator `AddressOf` erstellt einen Funktionsdelegaten, der auf die Funktion zeigt, die durch `procedurename` angegeben wurde.  Wenn die angegebene Prozedur eine Instanzenmethode ist, verweist der Funktionsdelegat sowohl auf die Instanz als auch auf die Methode.  Wenn der Funktionsdelegat aufgerufen wird, wird die angegebene Methode der angegebenen Instanz aufgerufen.  
  
 Der Operator `AddressOf` kann als Operand eines Delegatkonstruktors oder in einem Kontext verwendet werden, in dem der Delegattyp vom Compiler festgelegt werden kann.  
  
## Beispiel  
 In diesem Beispiel wird mit dem Operator `AddressOf` ein Delegat bezeichnet, der das `Click`\-Ereignis einer Schaltfläche verarbeitet.  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## Beispiel  
 Im folgenden Beispiel wird mit dem Operator `AddressOf` die Startfunktion für einen Thread bezeichnet.  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## Siehe auch  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Delegates](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)