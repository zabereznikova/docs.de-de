---
title: Return-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b66d16a249164b8989f05f10c785b97055bfde9e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="return-statement-visual-basic"></a>Return-Anweisung (Visual Basic)
Die Steuerung an den Code, aufgerufen zurückgegeben eine `Function`, `Sub`, `Get`, `Set`, oder `Operator` Prozedur.  
  
## <a name="syntax"></a>Syntax  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a>Segment  
 `expression`  
 Erforderlich einer `Function`, `Get`, oder `Operator` Prozedur. Der Ausdruck den Wert an den aufrufenden Code zurückgegeben werden.  
  
## <a name="remarks"></a>Hinweise  
 In einer `Sub` oder `Set` Prozedur, die `Return` Anweisung entspricht einer `Exit Sub` oder `Exit Property` -Anweisung und `expression` muss nicht angegeben werden.  
  
 In einem `Function`, `Get`, oder `Operator` Prozedur, die `Return` -Anweisung muss enthalten `expression`, und `expression` muss in einen Datentyp, der in den Rückgabetyp der Prozedur konvertiert werden ausgewertet. In einem `Function` oder `Get` Prozedur, Sie haben auch die Alternative einen Ausdruck zuweisen, um den Namen der Prozedur, die als Rückgabewert dient, und klicken Sie dann Ausführen einer `Exit Function` oder `Exit Property` Anweisung. In einer `Operator` Verfahren verwenden Sie `Return``expression`.  
  
 Sie können beliebig viele einschließen `Return` Anweisungen nach Bedarf in der gleichen Prozedur.  
  
> [!NOTE]
>  Der Code in eine `Finally` Block ausgeführt wird, nachdem ein `Return` -Anweisung in einer `Try` oder `Catch` Block ist aufgetreten, aber vor, `Return` -Anweisung ausführt. Ein `Return` -Anweisung kann nicht eingefügt werden, einem `Finally` Block.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Return` Anweisung mehrmals an den aufrufenden Code zurückgegeben werden soll, wenn die Prozedur keinen nichts weiter tun.  
  
 [!code-vb[VbVbalrStatements#53](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/return-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)  
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)  
 [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
