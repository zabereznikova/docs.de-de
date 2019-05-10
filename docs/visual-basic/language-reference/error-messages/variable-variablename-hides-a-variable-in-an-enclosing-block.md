---
title: Die Variable "<variablename>" verbirgt eine Variable in einem einschließenden Block.
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 36fe543dd4546c6fe930f259a55cea856917370f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662665"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a>Variable "\<Variablenname >' verbirgt eine Variable in einem einschließenden Block
Eine Variable in einem Block eingeschlossen hat den gleichen Namen wie eine andere lokale Variable.  
  
 **Fehler-ID:** BC30616  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Benennen Sie die Variable im-Block eingeschlossen, sodass sie nicht identisch mit anderen lokalen Variablen ist. Zum Beispiel:  
  
    ```  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- Eine häufige Ursache für diesen Fehler ist die Verwendung von `Catch e As Exception` innerhalb eines ereignishandlers. Wenn dies der Fall ist, den Namen der `Catch` Blockvariable `ex` statt `e`.  
  
- Eine andere übliche Quelle für diesen Fehler ist ein Zugriffsversuch auf eine lokale Variable deklariert, die innerhalb einer `Try` -block in einem separaten `Catch` Block. Um dies zu korrigieren, deklarieren Sie die Variable außerhalb der `Try...Catch...Finally` Struktur.  
  
## <a name="see-also"></a>Siehe auch

- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Variablendeklaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
