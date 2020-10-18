---
title: Die Handles-Klausel erfordert eine WithEvents-Variable, die im enthaltenden Typ oder einem seiner Basistypen definiert wird.
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: e16a157d0621d5baecb06ce118e3ab390bf68cf8
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162881"
---
# <a name="bc30506-handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="f3be3-102">BC30506: die Handles-Klausel erfordert eine widervents-Variable, die im enthaltenden Typ oder einem seiner Basis Typen definiert ist.</span><span class="sxs-lookup"><span data-stu-id="f3be3-102">BC30506: Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>

<span data-ttu-id="f3be3-103">`WithEvents`In ihrer Klausel haben Sie keine Variable angegeben `Handles` .</span><span class="sxs-lookup"><span data-stu-id="f3be3-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="f3be3-104">Das `Handles` Schlüsselwort am Ende einer Prozedur Deklaration bewirkt, dass es Ereignisse behandelt, die von einer Objektvariablen ausgelöst werden, die mit dem- `WithEvents` Schlüsselwort deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="f3be3-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>

<span data-ttu-id="f3be3-105">**Fehler-ID:** BC30506</span><span class="sxs-lookup"><span data-stu-id="f3be3-105">**Error ID:** BC30506</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="f3be3-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f3be3-106">To correct this error</span></span>

<span data-ttu-id="f3be3-107">Geben Sie die erforderliche `WithEvents` Variable an.</span><span class="sxs-lookup"><span data-stu-id="f3be3-107">Supply the necessary `WithEvents` variable.</span></span>

## <a name="example"></a><span data-ttu-id="f3be3-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f3be3-108">Example</span></span>

<span data-ttu-id="f3be3-109">Im folgenden Beispiel generiert Visual Basic Compilerfehler, `BC30506` da das [widervents](../modifiers/withevents.md) -Schlüsselwort nicht in der Definition der- <xref:System.Timers.Timer?displayProperty=nameWithType> Instanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f3be3-109">In the following example, Visual Basic generates compiler error `BC30506` because the [WithEvents](../modifiers/withevents.md) keyword is not used in the definition of the <xref:System.Timers.Timer?displayProperty=nameWithType> instance.</span></span>

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

<span data-ttu-id="f3be3-110">Im folgenden Beispiel wird erfolgreich kompiliert, da die- `_timer1` Variable mit dem- `WithEvents` Schlüsselwort definiert wird:</span><span class="sxs-lookup"><span data-stu-id="f3be3-110">The following example compiles successfully because the `_timer1` variable is defined with the `WithEvents` keyword:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="f3be3-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f3be3-111">See also</span></span>

- [<span data-ttu-id="f3be3-112">Ziehpunkte</span><span class="sxs-lookup"><span data-stu-id="f3be3-112">Handles</span></span>](../statements/handles-clause.md)
