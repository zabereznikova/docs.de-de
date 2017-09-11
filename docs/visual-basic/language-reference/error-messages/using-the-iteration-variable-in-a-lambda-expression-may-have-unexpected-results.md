---
title: "Verwendung der Iterationsvariablen in einem Lambda-Ausdruck möglicherweise unerwartete Ergebnisse | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42324
- bc42324
dev_langs:
- VB
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1c2e0e322ff46b9e215a169cd4cf3805c7dc3943
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a><span data-ttu-id="c2a7a-102">Die Verwendung der Iterationsvariablen in einem Lambdaausdruck kann zu unerwarteten Ergebnissen führen</span><span class="sxs-lookup"><span data-stu-id="c2a7a-102">Using the iteration variable in a lambda expression may have unexpected results</span></span>
<span data-ttu-id="c2a7a-103">Die Verwendung der Iterationsvariablen in einem Lambda-Ausdruck kann zu unerwarteten Ergebnissen führen.</span><span class="sxs-lookup"><span data-stu-id="c2a7a-103">Using the iteration variable in a lambda expression may have unexpected results.</span></span> <span data-ttu-id="c2a7a-104">Stattdessen erstellen Sie eine lokale Variable innerhalb der Schleife, und weisen sie den Wert der Iterationsvariablen.</span><span class="sxs-lookup"><span data-stu-id="c2a7a-104">Instead, create a local variable within the loop and assign it the value of the iteration variable.</span></span>  
  
 <span data-ttu-id="c2a7a-105">Diese Warnung wird angezeigt, wenn Sie eine Schleifeniterationsvariablen in einem Lambda-Ausdruck verwenden, die innerhalb der Schleife deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="c2a7a-105">This warning appears when you use a loop iteration variable in a lambda expression that is declared inside the loop.</span></span> <span data-ttu-id="c2a7a-106">Beispielsweise wird im folgenden Beispiel wird die Warnung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c2a7a-106">For example, the following example causes the warning to appear.</span></span>  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 <span data-ttu-id="c2a7a-107">Das folgende Beispiel zeigt die unerwarteten Ergebnisse, die auftreten können.</span><span class="sxs-lookup"><span data-stu-id="c2a7a-107">The following example shows the unexpected results that might occur.</span></span>  
  
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
  
 <span data-ttu-id="c2a7a-108">Die `For` Schleife erstellt ein Array von Lambda-Ausdrücken, von denen jeder den Wert der Schleifenvariablen Iteration zurückgibt `i`.</span><span class="sxs-lookup"><span data-stu-id="c2a7a-108">The `For` loop creates an array of lambda expressions, each of which returns the value of the loop iteration variable `i`.</span></span> <span data-ttu-id="c2a7a-109">Bei der Auswertung von Lambda-Ausdrücke in der `For Each` -Schleife, die Sie erwarten können, um 0, 1, 2, 3 und 4 angezeigt, die nachfolgenden Werte finden Sie unter `i` in den `For` Schleife.</span><span class="sxs-lookup"><span data-stu-id="c2a7a-109">When the lambda expressions are evaluated in the `For Each` loop, you might expect to see 0, 1, 2, 3, and 4 displayed, the successive values of `i` in the `For` loop.</span></span> <span data-ttu-id="c2a7a-110">Stattdessen sehen Sie den endgültigen Wert der `i` fünfmal angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c2a7a-110">Instead, you see the final value of `i` displayed five times:</span></span>  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 <span data-ttu-id="c2a7a-111">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="c2a7a-111">By default, this message is a warning.</span></span> <span data-ttu-id="c2a7a-112">Weitere Informationen zum Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c2a7a-112">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="c2a7a-113">**Fehler-ID:** BC42324</span><span class="sxs-lookup"><span data-stu-id="c2a7a-113">**Error ID:** BC42324</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c2a7a-114">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c2a7a-114">To correct this error</span></span>  
  
-   <span data-ttu-id="c2a7a-115">Weisen Sie den Wert der Iterationsvariablen in eine lokale Variable, und verwenden Sie die lokale Variable im Lambda-Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="c2a7a-115">Assign the value of the iteration variable to a local variable, and use the local variable in the lambda expression.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c2a7a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2a7a-116">See Also</span></span>  
 [<span data-ttu-id="c2a7a-117">Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="c2a7a-117">Lambda Expressions</span></span>](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
