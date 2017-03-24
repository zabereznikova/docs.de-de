---
title: '&quot;AddressOf&quot;-Operand muss der Name einer Methode (ohne Klammern) | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
dev_langs:
- VB
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 10
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
ms.openlocfilehash: 04103fe23ee55bb751d9604ef74614edeead8886
ms.lasthandoff: 03/13/2017

---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a>"AddressOf"-Operand muss der Name einer Methode (ohne Klammern) sein.
Der `AddressOf` -Operator erstellt eine Delegatinstanz einer Prozedur, die auf eine bestimmte Prozedur verweist. Die Syntax lautet wie folgt.  
  
 `AddressOf` `procedurename`  
  
 Runden Klammern folgende Argument `AddressOf`, wobei keine benötigt werden.  
  
 **Fehler-ID:** BC30577  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die Klammern um das Argument nach `AddressOf`.  
  
2.  Stellen Sie sicher, dass das Argument ein Methodenname ist.  
  
## <a name="see-also"></a>Siehe auch  
 [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)
