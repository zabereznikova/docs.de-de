---
title: Die Verwendung der Iterationsvariablen in einem Lambda-Ausdruck kann zu unerwarteten Ergebnissen führen
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: 618fc88a2ca92ec911a3fbd82de580403d924430
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841099"
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="53bb4-102">Die Verwendung der Iterationsvariablen in einem Lambda-Ausdruck kann zu unerwarteten Ergebnissen führen</span><span class="sxs-lookup"><span data-stu-id="53bb4-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="53bb4-103">Verwendung der Iterationsvariablen in einem Lambda-Ausdruck möglicherweise unerwartete Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="53bb4-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="53bb4-104">Stattdessen erstellen Sie eine lokale Variable innerhalb der Schleife aus, und weisen Sie diesem den Wert der Iterationsvariablen.</span><span class="sxs-lookup"><span data-stu-id="53bb4-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="53bb4-105">Diese Warnung wird angezeigt, wenn Sie eine Schleifeniterationsvariablen in einem Lambda-Ausdruck verwenden, die innerhalb der Schleife deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="53bb4-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="53bb4-106">Im folgende Beispiel wird z. B. die Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="53bb4-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="53bb4-107">Das folgende Beispiel zeigt die unerwarteten Ergebnisse, die auftreten können.</span><span class="sxs-lookup"><span data-stu-id="53bb4-107">The following example shows the unexpected results that might occur.</span></span>  
  
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
  
 <span data-ttu-id="53bb4-108">Die `For` Schleife erstellt ein Array von Lambda-Ausdrücken, von denen jeder den Wert der Schleifenvariablen Iteration gibt `i`.</span><span class="sxs-lookup"><span data-stu-id="53bb4-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="53bb4-109">Bei der Auswertung die Lambda-Ausdrücke in der `For Each` Schleife möglicherweise erwarten, 0, 1, 2, 3 und 4 angezeigt, die nachfolgenden Werte `i` in die `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="53bb4-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="53bb4-110">Stattdessen sehen Sie den endgültigen Wert der `i` fünfmal angezeigt:</span><span class="sxs-lookup"><span data-stu-id="53bb4-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="53bb4-111">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="53bb4-111">By default, this message is a warning.</span></span> <span data-ttu-id="53bb4-112">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="53bb4-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="53bb4-113">**Fehler-ID:** BC42324</span><span class="sxs-lookup"><span data-stu-id="53bb4-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="53bb4-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="53bb4-114">To correct this error</span></span>  
  
-   <span data-ttu-id="53bb4-115">Weisen Sie den Wert für die Iterationsvariable zu einer lokalen Variablen, und verwenden Sie die lokale Variable im Lambda-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="53bb4-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="53bb4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53bb4-116">See also</span></span>

- [<span data-ttu-id="53bb4-117">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="53bb4-117">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
