---
title: Optional (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3aa01c2c1ae731c8fe00fdee24521760db69e624
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)
Gibt an, dass ein Prozedurarguments ausgelassen werden kann, wenn die Prozedur aufgerufen wird.  
  
## <a name="remarks"></a>Hinweise  
 Für jeden optionalen Parameter müssen Sie einen konstanten Ausdruck als der Standardwert dieses Parameters angeben. Wenn der ausgewertete Ausdruck [nichts](../../../visual-basic/language-reference/nothing.md), der Standardwert des Datentyps Wert als der Standardwert des Parameters verwendet wird.  
  
 Wenn die Parameterliste einen optionalen Parameter enthält, muss jeder Parameter, die darauf folgt ebenfalls optional sein.  
  
 Der `Optional`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
-   [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  Wenn eine Prozedur mit oder ohne optionale Parameter aufgerufen wird, können Sie Argumente anhand der Position oder anhand des Namens übergeben. Weitere Informationen finden Sie unter [übergeben von Argumenten nach Position und Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).  
  
> [!NOTE]
>  Sie können auch eine Prozedur mit optionalen Parametern definieren, indem Sie mithilfe des Überladens. Wenn Sie einen optionalen Parameter verfügen, können Sie zwei überladene Versionen der Prozedur, eine, die der Parameter akzeptiert und eine, die nicht definieren. Weitere Informationen finden Sie unter [Prozedurüberladung](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine Prozedur mit einem optionalen Parameter.  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine Prozedur mit nach Position übergebenen Argumente und nach Namen übergebenen Argumenten aufgerufen wird. Die Prozedur besitzt zwei optionale Parameter.  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [Optionale Parameter](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)  
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
