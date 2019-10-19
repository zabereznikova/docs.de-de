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
ms.openlocfilehash: edaaf09f5a984344f7e89c9da988c529774934e9
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583257"
---
# <a name="return-statement-visual-basic"></a>Return-Anweisung (Visual Basic)
Gibt die Steuerung an den Code zurück, der eine `Function`, `Sub`, `Get`, `Set` oder `Operator` Prozedur aufgerufen hat.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a>Segment  
 `expression`  
 Erforderlich in einer `Function`-, `Get`-oder `Operator`-Prozedur. Ein Ausdruck, der den Wert darstellt, der an den aufrufenden Code zurückgegeben werden soll.  
  
## <a name="remarks"></a>Hinweise  
 In einer `Sub`-oder `Set` Prozedur entspricht die `Return`-Anweisung einer `Exit Sub`-oder `Exit Property`-Anweisung, und `expression` dürfen nicht angegeben werden.  
  
 In einer `Function`-, `Get`-oder `Operator` Prozedur muss die `Return`-Anweisung `expression` enthalten, und `expression` muss zu einem Datentyp ausgewertet werden, der in den Rückgabetyp der Prozedur konvertiert werden kann. In einer `Function`-oder `Get` Prozedur haben Sie auch die Alternative, dem Prozedur Namen einen Ausdruck zuzuweisen, der als Rückgabewert fungieren soll, und dann eine `Exit Function` oder `Exit Property` Anweisung auszuführen. In einer `Operator` Prozedur müssen Sie `Return expression` verwenden.  
  
 Sie können beliebig viele `Return` Anweisungen in der gleichen Prozedur einschließen.  
  
> [!NOTE]
> Der Code in einem `Finally`-Block wird ausgeführt, nachdem eine `Return`-Anweisung in einem `Try`-oder `Catch`-Block gefunden wurde, aber bevor diese `Return` Anweisung ausgeführt wird. Eine `Return`-Anweisung kann nicht in einen `Finally` Block eingeschlossen werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Return`-Anweisung mehrmals verwendet, um zum aufrufenden Code zurückzukehren, wenn die Prozedur keine andere Aktion ausführen muss.  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a>Siehe auch

- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)
- [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)
- [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
