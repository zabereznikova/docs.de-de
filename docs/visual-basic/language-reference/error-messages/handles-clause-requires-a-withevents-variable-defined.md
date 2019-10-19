---
title: Die Handles-Klausel erfordert eine WithEvents-Variable, die im enthaltenden Typ oder einem seiner Basistypen definiert wird.
ms.date: 07/20/2015
f1_keywords:
- vbc30506
- bc30506
helpviewer_keywords:
- BC30506
ms.assetid: 5b66f6a8-f050-4e03-a57f-a64e85f80cb5
ms.openlocfilehash: 191415408f607d0ff768e50c41fa9b3c4405a688
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582830"
---
# <a name="handles-clause-requires-a-withevents-variable-defined-in-the-containing-type-or-one-of-its-base-types"></a><span data-ttu-id="0772e-102">Die Handles-Klausel erfordert eine WithEvents-Variable, die im enthaltenden Typ oder einem seiner Basistypen definiert wird.</span><span class="sxs-lookup"><span data-stu-id="0772e-102">Handles clause requires a WithEvents variable defined in the containing type or one of its base types</span></span>

<span data-ttu-id="0772e-103">In ihrer `Handles`-Klausel haben Sie keine `WithEvents` Variable angegeben.</span><span class="sxs-lookup"><span data-stu-id="0772e-103">You did not supply a `WithEvents` variable in your `Handles` clause.</span></span> <span data-ttu-id="0772e-104">Das `Handles`-Schlüsselwort am Ende einer Prozedur Deklaration bewirkt, dass es Ereignisse behandelt, die von einer Objektvariablen ausgelöst werden, die mit dem Schlüsselwort `WithEvents` deklariert wurde.</span><span class="sxs-lookup"><span data-stu-id="0772e-104">The `Handles` keyword at the end of a procedure declaration causes it to handle events raised by an object variable declared using the `WithEvents` keyword.</span></span>

<span data-ttu-id="0772e-105">**Fehler-ID:** BC30506</span><span class="sxs-lookup"><span data-stu-id="0772e-105">**Error ID:** BC30506</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0772e-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="0772e-106">To correct this error</span></span>

<span data-ttu-id="0772e-107">Geben Sie die erforderliche `WithEvents` Variable an.</span><span class="sxs-lookup"><span data-stu-id="0772e-107">Supply the necessary `WithEvents` variable.</span></span>

## <a name="example"></a><span data-ttu-id="0772e-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0772e-108">Example</span></span>

<span data-ttu-id="0772e-109">Im folgenden Beispiel generiert Visual Basic Compilerfehler `BC30506`, da das [widervents](../modifiers/withevents.md) -Schlüsselwort nicht in der Definition der <xref:System.Timers.Timer?displayProperty=nameWithType> Instanz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0772e-109">In the following example, Visual Basic generates compiler error `BC30506` because the [WithEvents](../modifiers/withevents.md) keyword is not used in the definition of the <xref:System.Timers.Timer?displayProperty=nameWithType> instance.</span></span>

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

<span data-ttu-id="0772e-110">Im folgenden Beispiel wird erfolgreich kompiliert, da die `_timer1` Variable mit dem Schlüsselwort `WithEvents` definiert wird:</span><span class="sxs-lookup"><span data-stu-id="0772e-110">The following example compiles successfully because the `_timer1` variable is defined with the `WithEvents` keyword:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="0772e-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0772e-111">See also</span></span>

- [<span data-ttu-id="0772e-112">Handles</span><span class="sxs-lookup"><span data-stu-id="0772e-112">Handles</span></span>](../../../visual-basic/language-reference/statements/handles-clause.md)
