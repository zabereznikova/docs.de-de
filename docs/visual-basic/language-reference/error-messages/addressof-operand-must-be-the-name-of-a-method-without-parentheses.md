---
title: '&#39;AddressOf&#39; Operand muss der Name einer Methode (ohne Klammern)'
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: 6f9827d885996ffab8bdab91d0f774a57073e4a3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54565149"
---
# <a name="39addressof39-operand-must-be-the-name-of-a-method-without-parentheses"></a>&#39;AddressOf&#39; Operand muss der Name einer Methode (ohne Klammern)
Der `AddressOf` -Operator erstellt eine Delegatinstanz einer Prozedur, die auf eine bestimmte Prozedur verweist. Die Syntax lautet wie folgt aus.  
  
 `AddressOf` `procedurename`  
  
 Runden Klammern Folgendes Argument `AddressOf`, wo keine erforderlich sind.  
  
 **Fehler-ID:** BC30577  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Entfernen Sie die Klammern um die folgenden Argument `AddressOf`.  
  
2.  Stellen Sie sicher, dass das Argument den Namen einer Methode ist.  
  
## <a name="see-also"></a>Siehe auch
- [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)
