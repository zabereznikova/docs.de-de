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
ms.openlocfilehash: af49ea95d7f9d01072190ac3ccf6ba2f1041347e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957676"
---
# <a name="return-statement-visual-basic"></a>Return-Anweisung (Visual Basic)
Gibt die Steuerung an den Code zurück, `Function`der `Sub`die `Get`Prozedur `Set`,, `Operator` , oder aufgerufen hat.  
  
## <a name="syntax"></a>Syntax  
  
```  
Return  
-or-  
Return expression  
```  
  
## <a name="part"></a>Segment  
 `expression`  
 Erforderlich in einer `Function`- `Get`,- `Operator` oder-Prozedur. Ein Ausdruck, der den Wert darstellt, der an den aufrufenden Code zurückgegeben werden soll.  
  
## <a name="remarks"></a>Hinweise  
 In einer `Sub` - `Set` oder-Prozedur `Return` entspricht die-Anweisung einer `Exit Sub` - `Exit Property` oder-Anweisung `expression` und darf nicht angegeben werden.  
  
 In einer `Function`- `Get`,- `Operator` oder-Prozedur `Return` muss die- `expression`Anweisung enthalten `expression` und muss zu einem Datentyp ausgewertet werden, der in den Rückgabetyp der Prozedur konvertiert werden kann. In einer `Function` - `Get` oder-Prozedur haben Sie auch die Alternative, dem Prozedur Namen einen Ausdruck zuzuweisen, der als Rückgabewert fungieren soll, und dann eine `Exit Function` - `Exit Property` oder-Anweisung auszuführen. In einer `Operator` Prozedur müssen Sie verwenden `Return expression`.  
  
 Sie können beliebig viele `Return` -Anweisungen in der gleichen Prozedur einschließen.  
  
> [!NOTE]
> Der Code in einem `Finally` -Block wird ausgeführt `Return` , nachdem eine `Try` - `Catch` Anweisung in einem-oder-Block `Return` gefunden wurde, aber bevor diese Anweisung ausgeführt wird. Eine `Return` -Anweisung kann nicht in einen `Finally` -Block eingeschlossen werden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Return` -Anweisung mehrmals verwendet, um zum aufrufenden Code zurückzukehren, wenn die Prozedur keine andere Aktion ausführen muss.  
  
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
