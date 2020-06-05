---
title: Return-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Return
helpviewer_keywords:
- Return statement [Visual Basic], syntax
- control flow [Visual Basic], returning control to expressions
- Return statement [Visual Basic]
- expressions [Visual Basic], returning control to
ms.assetid: ac86e7f0-5a67-42c3-9834-0e0381efa3ec
ms.openlocfilehash: cdb58e32c30c8e6c1662fb698ac5576c3f71258c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404199"
---
# <a name="return-statement-visual-basic"></a>Return-Anweisung (Visual Basic)
Gibt die Steuerung an den Code zurück, der die `Function` `Sub` Prozedur,, `Get` , oder aufgerufen hat `Set` `Operator` .  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Return  
' -or-  
Return expression  
```  
  
## <a name="part"></a>Teil  
 `expression`  
 Erforderlich in einer- `Function` ,- `Get` oder- `Operator` Prozedur. Ein Ausdruck, der den Wert darstellt, der an den aufrufenden Code zurückgegeben werden soll.  
  
## <a name="remarks"></a>Bemerkungen  
 In einer- `Sub` oder `Set` -Prozedur `Return` entspricht die-Anweisung einer `Exit Sub` `Exit Property` -oder-Anweisung und `expression` darf nicht angegeben werden.  
  
 In einer- `Function` ,- `Get` oder `Operator` -Prozedur `Return` muss die-Anweisung enthalten `expression` und muss `expression` zu einem Datentyp ausgewertet werden, der in den Rückgabetyp der Prozedur konvertiert werden kann. In einer- `Function` oder `Get` -Prozedur haben Sie auch die Alternative, dem Prozedur Namen einen Ausdruck zuzuweisen, der als Rückgabewert fungieren soll, und dann eine- `Exit Function` oder-Anweisung auszuführen `Exit Property` . In einer `Operator` Prozedur müssen Sie verwenden `Return expression` .  
  
 Sie können beliebig viele- `Return` Anweisungen in der gleichen Prozedur einschließen.  
  
> [!NOTE]
> Der Code in einem- `Finally` Block `Return` wird ausgeführt, nachdem eine-Anweisung in einem- `Try` oder-Block gefunden `Catch` wurde, aber bevor diese `Return` Anweisung ausgeführt wird. Eine- `Return` Anweisung kann nicht in einen-Block eingeschlossen werden `Finally` .  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die- `Return` Anweisung mehrmals verwendet, um zum aufrufenden Code zurückzukehren, wenn die Prozedur keine andere Aktion ausführen muss.  
  
 [!code-vb[VbVbalrStatements#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#53)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Function-Anweisung](function-statement.md)
- [Sub-Anweisung](sub-statement.md)
- [Get-Anweisung](get-statement.md)
- [Set-Anweisung](set-statement.md)
- [Operator Statement](operator-statement.md)
- [Property Statement](property-statement.md)
- [Exit-Anweisung](exit-statement.md)
- [Try...Catch...Finally-Anweisung](try-catch-finally-statement.md)
