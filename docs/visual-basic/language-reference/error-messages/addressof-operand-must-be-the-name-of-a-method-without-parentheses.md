---
title: '&#39; AddressOf &#39; Operand muss dem Namen einer Methode (ohne Klammern).'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 02c996f1c94250526982e35395288b07db619db7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a>&#39; AddressOf &#39; Operand muss dem Namen einer Methode (ohne Klammern).
Der `AddressOf` -Operator erstellt eine Delegatinstanz einer Prozedur, die auf eine bestimmte Prozedur verweist. Die Syntax lautet wie folgt.  
  
 `AddressOf` `procedurename`  
  
 Runden Klammern folgende Argument `AddressOf`, wobei keine erforderlich sind.  
  
 **Fehler-ID:** BC30577  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die Klammern um das folgende Argument `AddressOf`.  
  
2.  Stellen Sie sicher, dass das Argument ein Methodenname ist.  
  
## <a name="see-also"></a>Siehe auch  
 [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)
