---
title: Die Handles-Klausel erfordert eine WithEvents-Variable, die im enthaltenden Typ oder einem seiner Basistypen definiert wird.
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 04c94d3d32660d1a186a9bb377c49a53e1451be6
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2019
ms.locfileid: "68512730"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a>Die Handles-Klausel erfordert eine WithEvents-Variable, die im enthaltenden Typ oder einem seiner Basistypen definiert wird.
In Ihrer `WithEvents` `Handles` Klausel haben Sie keine Variable angegeben. Das `Handles` Schlüsselwort am Ende einer Prozedur Deklaration bewirkt, dass es Ereignisse behandelt, die von einer Objektvariablen ausgelöst `WithEvents` werden, die mit dem-Schlüsselwort deklariert wurde.
  
 **Fehler-ID:** BC30506

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler
  
- Geben Sie die `WithEvents` erforderliche Variable an.
  
## <a name="example"></a>Beispiel

Im folgenden Beispiel generiert Visual Basic Compilerfehler `BC30506` , da das [widervents](../modifiers/withevents.md) -Schlüsselwort nicht in <xref:System.Timers.Timer?displayProperty=nameWithType> der Definition der-Instanz verwendet wird.

```vb
Imports System.Timers

Module Module1
    Private _timer1 As New Timer() With {.Interval = 1000, .Enabled = True}
    
    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub
End Module
```

Im folgenden Beispiel wird erfolgreich kompiliert, da `_timer1` die-Variable mit dem `WithEvents` -Schlüsselwort definiert wird:

```vb
Imports System.Timers

Module Module1
    Private WithEvents _timer1 As New Timer() With {.Interval = 1000}

    Sub Main()
        Console.WriteLine("Press any key to start the timer...")
        Console.ReadKey()
        _timer1.Start()
        Console.ReadKey()
    End Sub

    Private Sub Timer1_Tick(sender As Object, args As EventArgs) Handles _timer1.Elapsed
        Console.WriteLine("Press any key to terminate...")
    End Sub

End Module
```

## <a name="see-also"></a>Siehe auch

- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
