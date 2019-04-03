---
title: Call-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 755443a99a1ad8b0430a76d2dba1ff27472d4c9d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832644"
---
# <a name="call-statement-visual-basic"></a>Call-Anweisung (Visual Basic)
Überträgt die Steuerung an eine `Function`, `Sub`, oder eine Dynamic Link Library (DLL)-Prozedur.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>Teile  
|||
|---|---|
|`procedureName`|Erforderlich. Der Name der Prozedur aufrufen.|
|`argumentList`|Dies ist optional. Liste der Variablen oder Ausdrücke zurück, die Argumente, die an die Prozedur übergeben werden, wenn sie aufgerufen wird. Mehrere Argumente werden durch Kommas getrennt. Wenn Sie einschließen `argumentList`, müssen Sie es in Klammern einschließen.|
|||
  
## <a name="remarks"></a>Hinweise  
 Sie können die `Call` -Schlüsselwort, wenn Sie eine Prozedur aufrufen. Für die meisten Aufrufe von Prozeduren müssen Sie sich nicht auf dieses Schlüsselwort verwenden.  
  
 In der Regel die `Call` -Schlüsselwort, wenn der aufgerufene Ausdruck nicht mit einer ID, startet. Verwenden der `Call` Schlüsselwort für einen anderen Verwendungszweck wird nicht empfohlen.  
  
 Wenn die Prozedur einen Wert zurückgibt, die `Call` Anweisung verworfen.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt zwei Beispiele, in denen die `Call` Schlüsselwort ist erforderlich, um eine Prozedur aufrufen. In beiden Beispielen beginnen nicht der aufgerufene Ausdruck mit einem Bezeichner.  
  
 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a>Siehe auch

- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
