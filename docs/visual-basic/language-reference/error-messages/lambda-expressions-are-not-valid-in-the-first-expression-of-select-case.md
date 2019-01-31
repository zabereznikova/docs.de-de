---
title: Lambdaausdrücke sind im ersten Ausdruck einer 'Select Case'-Anweisung nicht gültig
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: d56515093020a4c987d132491957ce6db9e21683
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55287793"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a>Lambdaausdrücke sind im ersten Ausdruck einer 'Select Case'-Anweisung nicht gültig
Sie können einen Lambda-Ausdruck keine für den Testausdruck in einer `Select Case` Anweisung. Definitionen von Lambda-Ausdrücken zurückgegeben werden, Funktionen und der Testausdruck eine `Select Case` -Anweisung muss ein elementarer Datentyp sein.  
  
 Der folgende Code verursacht diesen Fehler:  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 **Fehler-ID:** BC36635  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Überprüfen Sie den Code, um festzustellen, ob eine andere bedingte Konstruktion für Sie geeignet wäre, z. B. eine `If...Then...Else` -Anweisung.  
  
-   Sie können beabsichtigt zum Aufrufen der Funktion, wie im folgenden Code gezeigt:  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a>Siehe auch
- [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [If...Then...Else-Anweisung](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Select...Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md)
