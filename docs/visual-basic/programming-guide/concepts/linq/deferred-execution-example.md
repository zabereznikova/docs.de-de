---
title: Beispiel für eine verzögerte Ausführung
ms.date: 07/20/2015
ms.assetid: 9a22bea1-c755-4aac-800a-fcd9e5107ace
ms.openlocfilehash: 863b018b6047d61f6fb4a5c1ac68151ed69d24a1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84410798"
---
# <a name="deferred-execution-example-visual-basic"></a><span data-ttu-id="dd086-102">Beispiel für eine verzögerte Ausführung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd086-102">Deferred Execution Example (Visual Basic)</span></span>

<span data-ttu-id="dd086-103">In diesem Thema wird gezeigt, wie sich die verzögerte Ausführung (Deferred Execution) und die verzögerte Auswertung (Lazy Evaluation) auf die Ausführung Ihrer LINQ to XML-Abfragen auswirken.</span><span class="sxs-lookup"><span data-stu-id="dd086-103">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>

## <a name="example"></a><span data-ttu-id="dd086-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd086-104">Example</span></span>

<span data-ttu-id="dd086-105">Im folgenden Beispiel wird gezeigt, in welcher Reihenfolge die Ausführung erfolgt, wenn eine Erweiterungsmethode verwendet wird, die mit verzögerter Ausführung arbeitet.</span><span class="sxs-lookup"><span data-stu-id="dd086-105">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="dd086-106">Das Beispiel deklariert ein Array aus drei Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="dd086-106">The example declares an array of three strings.</span></span> <span data-ttu-id="dd086-107">Anschließend durchläuft es die von `ConvertCollectionToUpperCase` zurückgegebene Auflistung.</span><span class="sxs-lookup"><span data-stu-id="dd086-107">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>

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

<span data-ttu-id="dd086-108">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="dd086-108">This example produces the following output:</span></span>

```console
ToUpper: source abc
Main: str ABC
ToUpper: source def
Main: str DEF
ToUpper: source ghi
Main: str GHI
```

<span data-ttu-id="dd086-109">Beachten Sie, dass beim Durchlaufen der von `ConvertCollectionToUpperCase` zurückgegebenen Auflistung erst jedes Element aus dem Quellzeichenfolgenarray abgerufen und in Großbuchstaben umgewandelt wird, bevor das nächste Element aus dem Quellzeichenfolgenarray abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="dd086-109">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>

<span data-ttu-id="dd086-110">Wie Sie sehen, wird das gesamte Array von Zeichenfolgen erst dann in Großbuchstaben umgewandelt, wenn jedes Element in der zurückgegebenen Auflistung in der `foreach`-Schleife in `Main` verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="dd086-110">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>

## <a name="see-also"></a><span data-ttu-id="dd086-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd086-111">See also</span></span>

- [<span data-ttu-id="dd086-112">Tutorial: verzögerte Ausführung (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dd086-112">Tutorial: Deferred Execution (Visual Basic)</span></span>](tutorial-deferred-execution.md)
