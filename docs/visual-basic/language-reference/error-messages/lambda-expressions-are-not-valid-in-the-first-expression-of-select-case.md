---
title: Lambda-Ausdrücke sind im ersten Ausdruck einer 'Select Case'-Anweisung nicht gültig
ms.date: 07/20/2015
f1_keywords:
- bc36635
- vbc36635
helpviewer_keywords:
- BC36635
ms.assetid: 74609979-9c03-4864-bbce-f588aa2e0917
ms.openlocfilehash: 9f200ea44e7505c407c7df56e596435024394875
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873879"
---
# <a name="lambda-expressions-are-not-valid-in-the-first-expression-of-a-select-case-statement"></a>Lambda-Ausdrücke sind im ersten Ausdruck einer 'Select Case'-Anweisung nicht gültig

Ein Lambda-Ausdruck kann nicht für den Test Ausdruck in einer-Anweisung verwendet werden `Select Case` . Lambda-Ausdrucks Definitionen geben Funktionen zurück, und der Test Ausdruck einer `Select Case` Anweisung muss ein grundlegender Datentyp sein.  
  
 Der folgende Code verursacht diesen Fehler:  
  
```vb  
' Select Case (Function(arg) arg Is Nothing)  
    ' List of the cases.  
' End Select  
```  
  
 **Fehler-ID:** BC36635  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Überprüfen Sie den Code, um festzustellen, ob eine andere bedingte Konstruktion für Sie geeignet wäre, z. B. eine `If...Then...Else` -Anweisung.  
  
- Möglicherweise haben Sie die Funktion aufgerufen, wie im folgenden Code gezeigt:  
  
```vb  
Dim num? As Integer  
Select Case ((Function(arg? As Integer) arg Is Nothing)(num))  
    ' List of the cases  
End Select  
```  
  
## <a name="see-also"></a>Siehe auch

- [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md)
- [If...Then...Else-Anweisung](../statements/if-then-else-statement.md)
- [Select...Case-Anweisung](../statements/select-case-statement.md)
