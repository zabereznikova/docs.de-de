---
title: Variable &#39; &lt;Variablename&gt; &#39; verbirgt eine Variable in einem einschließenden Block
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 23ec659535b71ee9af189f5c4fec0dec2bb1cd8f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54719429"
---
# <a name="variable-39ltvariablenamegt39-hides-a-variable-in-an-enclosing-block"></a>Variable &#39; &lt;Variablename&gt; &#39; verbirgt eine Variable in einem einschließenden Block
Eine Variable in einem Block eingeschlossen hat den gleichen Namen wie eine andere lokale Variable.  
  
 **Fehler-ID:** BC30616  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Benennen Sie die Variable im-Block eingeschlossen, sodass sie nicht identisch mit anderen lokalen Variablen ist. Zum Beispiel:  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
-   Eine häufige Ursache für diesen Fehler ist die Verwendung von `Catch e As Exception` innerhalb eines ereignishandlers. Wenn dies der Fall ist, den Namen der `Catch` Blockvariable `ex` statt `e`.  
  
-   Eine andere übliche Quelle für diesen Fehler ist ein Zugriffsversuch auf eine lokale Variable deklariert, die innerhalb einer `Try` -block in einem separaten `Catch` Block. Um dies zu korrigieren, deklarieren Sie die Variable außerhalb der `Try...Catch...Finally` Struktur.  
  
## <a name="see-also"></a>Siehe auch
- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Variablendeklaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
