---
title: Die Verwendung der Iterationsvariablen in einem Lambdaausdruck kann zu unerwarteten Ergebnissen führen
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: 7144a5fd4a197fddaf1ac4132df0ff70995ad067
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33594161"
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="f66fd-102">Die Verwendung der Iterationsvariablen in einem Lambdaausdruck kann zu unerwarteten Ergebnissen führen</span><span class="sxs-lookup"><span data-stu-id="f66fd-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="f66fd-103">Verwendung der Iterationsvariablen in einem Lambdaausdruck möglicherweise unerwartete Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="f66fd-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="f66fd-104">Stattdessen erstellen Sie eine lokale Variable innerhalb der Schleife, und weisen sie den Wert der Iterationsvariablen.</span><span class="sxs-lookup"><span data-stu-id="f66fd-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="f66fd-105">Diese Warnung wird angezeigt, wenn Sie eine Schleifeniterationsvariablen in einem Lambdaausdruck verwenden, die innerhalb der Schleife deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="f66fd-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="f66fd-106">Im folgende Beispiel wird z. B. die Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f66fd-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="f66fd-107">Das folgende Beispiel zeigt die unerwarteten Ergebnisse, die auftreten können.</span><span class="sxs-lookup"><span data-stu-id="f66fd-107">The following example shows the unexpected results that might occur.</span></span>  
  
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
  
 <span data-ttu-id="f66fd-108">Die `For` Schleife erstellt ein Array von Lambda-Ausdrücke, von denen jede den Wert der Schleifenvariablen Iteration gibt `i`.</span><span class="sxs-lookup"><span data-stu-id="f66fd-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="f66fd-109">Bei der Auswertung von Lambda-Ausdrücke in der `For Each` -Schleife, die Sie erwarten können, um 0, 1, 2, 3 und 4 angezeigt, die nachfolgenden Werte finden Sie unter `i` in die `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="f66fd-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="f66fd-110">Den endgültigen Wert der stattdessen angezeigt `i` fünfmal angezeigt:</span><span class="sxs-lookup"><span data-stu-id="f66fd-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="f66fd-111">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="f66fd-111">By default, this message is a warning.</span></span> <span data-ttu-id="f66fd-112">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="f66fd-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="f66fd-113">**Fehler-ID:** BC42324</span><span class="sxs-lookup"><span data-stu-id="f66fd-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="f66fd-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="f66fd-114">To correct this error</span></span>  
  
-   <span data-ttu-id="f66fd-115">Weisen Sie den Wert der Iterationsvariablen in eine lokale Variable, und verwenden Sie die lokale Variable im Lambda-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="f66fd-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f66fd-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f66fd-116">See Also</span></span>  
 [<span data-ttu-id="f66fd-117">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="f66fd-117">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
