---
title: Die Handles-Klausel erfordert eine WithEvents-Variable, die im enthaltenden Typ oder einem seiner Basistypen definiert wird.
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 94c4229d4036382e344cffb09295e218642c55d4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402900"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a>Die Handles-Klausel erfordert eine WithEvents-Variable, die im enthaltenden Typ oder einem seiner Basistypen definiert wird.

`WithEvents`In ihrer Klausel haben Sie keine Variable angegeben `Handles` . Das `Handles` Schlüsselwort am Ende einer Prozedur Deklaration bewirkt, dass es Ereignisse behandelt, die von einer Objektvariablen ausgelöst werden, die mit dem- `WithEvents` Schlüsselwort deklariert wurde.

**Fehler-ID:** BC30506

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

Geben Sie die erforderliche `WithEvents` Variable an.

## <a name="example"></a>Beispiel

Im folgenden Beispiel generiert Visual Basic Compilerfehler, `BC30506` da das [widervents](../modifiers/withevents.md) -Schlüsselwort nicht in der Definition der- <xref:System.Timers.Timer?displayProperty=nameWithType> Instanz verwendet wird.

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

Im folgenden Beispiel wird erfolgreich kompiliert, da die- `_timer1` Variable mit dem- `WithEvents` Schlüsselwort definiert wird:

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

## <a name="see-also"></a>Weitere Informationen

- [Ziehpunkte](../statements/handles-clause.md)
