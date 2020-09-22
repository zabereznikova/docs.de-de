---
title: Die Variable "<variablename>" verbirgt eine Variable in einem einschließenden Block.
ms.date: 07/20/2015
f1_keywords:
- vbc30616
- bc30616
helpviewer_keywords:
- BC30616
ms.assetid: e7658ebc-da45-451b-a409-a0f8915f0beb
ms.openlocfilehash: 04538be3431fb06518051db4378e986ea5711219
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875056"
---
# <a name="variable-variablename-hides-a-variable-in-an-enclosing-block"></a>Die Variable "\<variablename>" verbirgt eine Variable in einem einschließenden Block.

Eine in einen-Block eingeschlossene Variable hat denselben Namen wie eine andere lokale Variable.  
  
 **Fehler-ID:** BC30616  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Benennen Sie die Variable im eingeschlossenen Block so um, dass Sie nicht mit allen anderen lokalen Variablen identisch ist. Beispiel:  
  
    ```vb  
    Dim a, b, x As Integer  
    If a = b Then  
       Dim y As Integer = 20 ' Uniquely named block variable.  
    End If  
    ```  
  
- Eine häufige Ursache für diesen Fehler ist die Verwendung von `Catch e As Exception` innerhalb eines Ereignis Handlers. Wenn dies der Fall ist, benennen Sie die `Catch` Block Variable `ex` anstelle von `e` .  
  
- Eine weitere häufige Ursache für diesen Fehler ist der Versuch, auf eine lokale Variable zuzugreifen, die `Try` in einem Block in einem separaten Block deklariert ist `Catch` . Um dies zu korrigieren, deklarieren Sie die Variable außerhalb der- `Try...Catch...Finally` Struktur.  
  
## <a name="see-also"></a>Weitere Informationen

- [Try...Catch...Finally-Anweisung](../statements/try-catch-finally-statement.md)
- [Variablen Deklaration](../../programming-guide/language-features/variables/variable-declaration.md)
