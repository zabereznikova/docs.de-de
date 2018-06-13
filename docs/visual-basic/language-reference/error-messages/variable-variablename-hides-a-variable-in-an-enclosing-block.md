---
title: Variable &#39; &lt;Variablename&gt; &#39; verbirgt eine Variable in einem einschließenden Block
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 58e09caeb477d6b1df7f3be17e0a8ee05be3551e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33595091"
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a>Variable &#39; &lt;Variablename&gt; &#39; verbirgt eine Variable in einem einschließenden Block
Eine Variable in einem Block eingeschlossen hat den gleichen Namen wie eine andere lokale Variable.  
  
 **Fehler-ID:** BC30616  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Benennen Sie die Variable in der eingeschlossenen Block, damit er nicht mit der lokalen Variablen identisch ist. Zum Beispiel:  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   Eine häufige Ursache für diesen Fehler ist die Verwendung von `Catch e As Exception` innerhalb eines ereignishandlers. Wenn dies der Fall ist, benennen Sie die `Catch` Blockvariable `ex` statt `e`.  
  
-   Eine andere übliche Quelle für diesen Fehler ist der Versuch, eine lokale Variable deklariert den Zugriff auf eine `Try` blockieren in einer separaten `Catch` Block. Um dies zu korrigieren, deklarieren Sie die Variable außerhalb der `Try...Catch...Finally` Struktur.  
  
## <a name="see-also"></a>Siehe auch  
 [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Variablendeklaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
