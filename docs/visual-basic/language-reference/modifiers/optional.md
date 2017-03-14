---
title: "Optional (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Optional"
  - "vb.optional"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Optional keyword, contexts"
  - "Optional keyword"
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
caps.latest.revision: 14
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 14
---
# Optional (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt an, dass ein Prozedurargument beim Aufruf der Prozedur ausgelassen werden kann.  
  
## Hinweise  
 Für jeden optionalen Parameter müssen Sie einen konstanten Ausdruck als Standardwert dieses Parameters angeben.  Wenn der Ausdruck [Nichts](../../../visual-basic/language-reference/nothing.md) ergibt, wird der Standardwert des Werts datentyps als Standardwert des Parameters verwendet.  
  
 Wenn die Parameterliste einen optionalen Parameter enthält, muss jeder Parameter, der ihr folgt ebenfalls optional sein.  
  
 Der `Optional`\-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
-   [Declare\-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Function\-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property\-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Sub\-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  Wenn Sie eine Prozedur mit oder ohne optionale Parameter aufrufen, können Sie Argumente durch Position oder Namen übergeben.  Weitere Informationen finden Sie unter [Passing Arguments by Position and by Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).  
  
> [!NOTE]
>  Sie können eine Prozedur mit optionalen Parametern definieren, indem Sie die Überladung verwenden.  Wenn ein optionaler Parameter vorhanden ist, können Sie zwei überladene Versionen der Prozedur, der bzw. die den Parameter, und akzeptiert der definieren, die nicht vorhanden ist.  Weitere Informationen finden Sie unter [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## Beispiel  
 Im folgenden Beispiel wird eine Prozedur mit einem optionalen Parameter verfügt.  
  
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
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine Prozedur mit Argumenten aufruft, die durch Position übergeben werden und mit den Argumenten, die über den Namen übergeben werden.  Die Prozedur verfügt über zwei optionale Parameter.  
  
 [!code-vb[VbVbalrKeywords#21](../../../visual-basic/language-reference/codesnippet/VisualBasic/optional_1.vb)]  
  
## Siehe auch  
 [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md)   
 [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)