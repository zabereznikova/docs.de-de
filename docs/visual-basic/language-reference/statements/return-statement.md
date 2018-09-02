---
title: Return-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: fe200add4e29fe4bbe0fdf335dcd94107b8ff1eb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43425637"
---
# <a name="return-statement-visual-basic"></a>Return-Anweisung (Visual Basic)
Übergibt die Steuerung an den Code, der Namen einer `Function`, `Sub`, `Get`, `Set`, oder `Operator` Verfahren.  
  
## <a name="syntax"></a>Syntax  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a>Segment  
 `expression`  
 Muss eine `Function`, `Get`, oder `Operator` Verfahren. Ausdruck, der den Wert an den aufrufenden Code zurückgegeben werden darstellt.  
  
## <a name="remarks"></a>Hinweise  
 In einer `Sub` oder `Set` Verfahren der `Return` Anweisung entspricht einer `Exit Sub` oder `Exit Property` -Anweisung und `expression` muss nicht angegeben werden.  
  
 In einem `Function`, `Get`, oder `Operator` Verfahren der `Return` -Anweisung muss enthalten `expression`, und `expression` muss in einen Datentyp, der in den Rückgabetyp der Prozedur konvertiert werden ausgewertet. In einer `Function` oder `Get` Verfahren haben Sie auch die Alternative, den Namen der Prozedur, dient als Rückgabewert einen Ausdruck zuweisen und dann eine `Exit Function` oder `Exit Property` Anweisung. In einer `Operator` Verfahren verwenden Sie `Return expression`.  
  
 Sie können beliebig viele einschließen `Return` Anweisungen nach Bedarf in der gleichen Prozedur.  
  
> [!NOTE]
>  Der Code in eine `Finally` Block ausgeführt wird, nachdem eine `Return` -Anweisung in eine `Try` oder `Catch` Block ist, allerdings bevor, `Return` -Anweisung ausführt. Ein `Return` -Anweisung kann nicht eingefügt werden, einem `Finally` Block.  
  
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
