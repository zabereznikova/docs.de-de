---
title: Die Verwendung der Iterationsvariablen in einem Lambda-Ausdruck kann zu unerwarteten Ergebnissen führen
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: d0deea94084565ea91debe2b6db30def4cd9e00e
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92161490"
---
# <a name="bc42324-using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="9f39e-102">BC42324: die Verwendung der Iterations Variablen in einem Lambda-Ausdruck kann zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="9f39e-102">BC42324: Using the iteration variable in a lambda expression may have unexpected results</span></span>

<span data-ttu-id="9f39e-103">Die Verwendung der Iterations Variablen in einem Lambda-Ausdruck kann zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="9f39e-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="9f39e-104">Erstellen Sie stattdessen eine lokale Variable innerhalb der Schleife, und weisen Sie Ihr den Wert der Iterations Variablen zu.</span><span class="sxs-lookup"><span data-stu-id="9f39e-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>

 <span data-ttu-id="9f39e-105">Diese Warnung wird angezeigt, wenn Sie eine Schleifen Iterations Variable in einem Lambda Ausdruck verwenden, der innerhalb der-Schleife deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="9f39e-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="9f39e-106">Beispielsweise bewirkt das folgende Beispiel, dass die Warnung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9f39e-106">For example, the following example causes the warning to appear.</span></span>

```vb
For i As Integer = 1 To 10
    ' The warning is given for the use of i.
    Dim exampleFunc As Func(Of Integer) = Function() i
Next
```

 <span data-ttu-id="9f39e-107">Das folgende Beispiel zeigt die unerwarteten Ergebnisse, die auftreten können.</span><span class="sxs-lookup"><span data-stu-id="9f39e-107">The following example shows the unexpected results that might occur.</span></span>

```vb
Module Module1
    Sub Main()
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}

        For i As Integer = 0 To 4
            array1(i) = Function() i
        Next

        For Each funcElement In array1
            System.Console.WriteLine(funcElement())
        Next

    End Sub
End Module
```

 <span data-ttu-id="9f39e-108">Die- `For` Schleife erstellt ein Array von Lambda-Ausdrücken, von denen jede den Wert der Schleifen Iterations Variablen zurückgibt `i` .</span><span class="sxs-lookup"><span data-stu-id="9f39e-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="9f39e-109">Wenn die Lambda-Ausdrücke in der- `For Each` Schleife ausgewertet werden, erwarten Sie möglicherweise, dass 0, 1, 2, 3 und 4 angezeigt werden, die aufeinander folgenden Werte von `i` in der- `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="9f39e-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="9f39e-110">Stattdessen wird der endgültige Wert von `i` fünfmal angezeigt:</span><span class="sxs-lookup"><span data-stu-id="9f39e-110">Instead, you see the final value of `i` displayed five times:</span></span>

 `5`

 `5`

 `5`

 `5`

 `5`

 <span data-ttu-id="9f39e-111">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="9f39e-111">By default, this message is a warning.</span></span> <span data-ttu-id="9f39e-112">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="9f39e-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>

 <span data-ttu-id="9f39e-113">**Fehler-ID:** BC42324</span><span class="sxs-lookup"><span data-stu-id="9f39e-113">**Error ID:** BC42324</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="9f39e-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9f39e-114">To correct this error</span></span>

- <span data-ttu-id="9f39e-115">Weisen Sie den Wert der Iterations Variablen einer lokalen Variablen zu, und verwenden Sie die lokale Variable im Lambda-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="9f39e-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>

```vb
Module Module1
    Sub Main()
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}

        For i As Integer = 0 To 4
            Dim j = i
            array1(i) = Function() j
        Next

        For Each funcElement In array1
            System.Console.WriteLine(funcElement())
        Next

    End Sub
End Module
```

## <a name="see-also"></a><span data-ttu-id="9f39e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f39e-116">See also</span></span>

- [<span data-ttu-id="9f39e-117">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="9f39e-117">Lambda Expressions</span></span>](../../programming-guide/language-features/procedures/lambda-expressions.md)
