---
title: Lambdaausdrücke sind nicht gültig ist, im ersten Ausdruck einer &#39;Select Case&#39; Anweisung
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: c492615850ec089fe35c1ae4eaba90a741e30f42
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-39select-case39-statement"></a>Lambdaausdrücke sind nicht gültig ist, im ersten Ausdruck einer &#39;Select Case&#39; Anweisung
Sie können einen Lambda-Ausdruck keine für den Testausdruck in einer `Select Case` Anweisung. Definitionen der Lambda-Ausdruck zurückgeben, Funktionen und der Testausdruck eine `Select Case` -Anweisung muss ein elementarer Datentyp sein.  
  
 Der folgende Code verursacht diesen Fehler:  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 **Fehler-ID:** BC36635  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Überprüfen Sie den Code, um festzustellen, ob eine andere bedingte Konstruktion für Sie geeignet wäre, z. B. eine `If...Then...Else` -Anweisung.  
  
-   Sie können haben die Funktion aufrufen gedacht, wie im folgenden Code gezeigt:  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)  
 [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
 [Select...Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md)
