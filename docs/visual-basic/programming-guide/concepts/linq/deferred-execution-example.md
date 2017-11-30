---
title: "Beispiel für die verzögerte Ausführung (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a22bea1-c755-4aac-800a-fcd9e5107ace
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a4d2146901d9282b0df706b483afef79f714f660
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="deferred-execution-example-visual-basic"></a><span data-ttu-id="b4f86-102">Beispiel für die verzögerte Ausführung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4f86-102">Deferred Execution Example (Visual Basic)</span></span>
<span data-ttu-id="b4f86-103">In diesem Thema wird gezeigt, wie sich die verzögerte Ausführung (Deferred Execution) und die verzögerte Auswertung (Lazy Evaluation) auf die Ausführung Ihrer LINQ to XML-Abfragen auswirken.</span><span class="sxs-lookup"><span data-stu-id="b4f86-103">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4f86-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b4f86-104">Example</span></span>  
 <span data-ttu-id="b4f86-105">Im folgenden Beispiel wird gezeigt, in welcher Reihenfolge die Ausführung erfolgt, wenn eine Erweiterungsmethode verwendet wird, die mit verzögerter Ausführung arbeitet.</span><span class="sxs-lookup"><span data-stu-id="b4f86-105">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="b4f86-106">Das Beispiel deklariert ein Array aus drei Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="b4f86-106">The example declares an array of three strings.</span></span> <span data-ttu-id="b4f86-107">Anschließend durchläuft es die von `ConvertCollectionToUpperCase` zurückgegebene Auflistung.</span><span class="sxs-lookup"><span data-stu-id="b4f86-107">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module Module1  
  
    <Extension()>  
    Private Iterator Function ConvertCollectionToUpperCase(  
    ByVal source As IEnumerable(Of String)) _  
    As IEnumerable(Of String)   
        For Each str As String In source  
            Console.WriteLine("ToUpper: source {0}", str)   
            Yield str.ToUpper()  
        Next  
    End Function  
  
    Sub Main()  
        Dim stringArray = New String() {"abc", "def", "ghi"}  
  
        Dim q = From str In stringArray.ConvertCollectionToUpperCase()  
                Select str  
  
        For Each Str As String In q  
            Console.WriteLine("Main: str {0}", Str)   
        Next  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="b4f86-108">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="b4f86-108">This example produces the following output:</span></span>  
  
```  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 <span data-ttu-id="b4f86-109">Beachten Sie, dass beim Durchlaufen der von `ConvertCollectionToUpperCase` zurückgegebenen Auflistung erst jedes Element aus dem Quellzeichenfolgenarray abgerufen und in Großbuchstaben umgewandelt wird, bevor das nächste Element aus dem Quellzeichenfolgenarray abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b4f86-109">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>  
  
 <span data-ttu-id="b4f86-110">Wie Sie sehen, wird das gesamte Array von Zeichenfolgen erst dann in Großbuchstaben umgewandelt, wenn jedes Element in der zurückgegebenen Auflistung in der `foreach`-Schleife in `Main` verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="b4f86-110">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4f86-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b4f86-111">See Also</span></span>  
 [<span data-ttu-id="b4f86-112">Lernprogramm: Verzögerte Ausführung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4f86-112">Tutorial: Deferred Execution (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/tutorial-deferred-execution.md)
