---
title: Beispiel für eine verzögerte Ausführung (C#)
description: Hier erfahren Sie, wie sich die verzögerte Ausführung und die verzögerte Auswertung in C# auf die Ausführung Ihrer LINQ to XML-Abfragen auswirken.
ms.date: 07/20/2015
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
ms.openlocfilehash: 65ba4cc150f2fc9d8f44aee352987ea0eeaab0a5
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103958"
---
# <a name="deferred-execution-example-c"></a><span data-ttu-id="f5a69-103">Beispiel für eine verzögerte Ausführung (C#)</span><span class="sxs-lookup"><span data-stu-id="f5a69-103">Deferred Execution Example (C#)</span></span>
<span data-ttu-id="f5a69-104">In diesem Thema wird gezeigt, wie sich die verzögerte Ausführung (Deferred Execution) und die verzögerte Auswertung (Lazy Evaluation) auf die Ausführung Ihrer LINQ to XML-Abfragen auswirken.</span><span class="sxs-lookup"><span data-stu-id="f5a69-104">This topic shows how deferred execution and lazy evaluation affect the execution of your LINQ to XML queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5a69-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f5a69-105">Example</span></span>  
 <span data-ttu-id="f5a69-106">Im folgenden Beispiel wird gezeigt, in welcher Reihenfolge die Ausführung erfolgt, wenn eine Erweiterungsmethode verwendet wird, die mit verzögerter Ausführung arbeitet.</span><span class="sxs-lookup"><span data-stu-id="f5a69-106">The following example shows the order of execution when using an extension method that uses deferred execution.</span></span> <span data-ttu-id="f5a69-107">Das Beispiel deklariert ein Array aus drei Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="f5a69-107">The example declares an array of three strings.</span></span> <span data-ttu-id="f5a69-108">Anschließend durchläuft es die von `ConvertCollectionToUpperCase` zurückgegebene Auflistung.</span><span class="sxs-lookup"><span data-stu-id="f5a69-108">It then iterates through the collection returned by `ConvertCollectionToUpperCase`.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source {0}", str);  
            yield return str.ToUpper();  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        var q = from str in stringArray.ConvertCollectionToUpperCase()  
                select str;  
  
        foreach (string str in q)  
            Console.WriteLine("Main: str {0}", str);  
    }  
}  
```  
  
 <span data-ttu-id="f5a69-109">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="f5a69-109">This example produces the following output:</span></span>  
  
```output  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 <span data-ttu-id="f5a69-110">Beachten Sie, dass beim Durchlaufen der von `ConvertCollectionToUpperCase` zurückgegebenen Auflistung erst jedes Element aus dem Quellzeichenfolgenarray abgerufen und in Großbuchstaben umgewandelt wird, bevor das nächste Element aus dem Quellzeichenfolgenarray abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f5a69-110">Notice that when iterating through the collection returned by `ConvertCollectionToUpperCase`, each item is retrieved from the source string array and converted to uppercase before the next item is retrieved from the source string array.</span></span>  
  
 <span data-ttu-id="f5a69-111">Wie Sie sehen, wird das gesamte Array von Zeichenfolgen erst dann in Großbuchstaben umgewandelt, wenn jedes Element in der zurückgegebenen Auflistung in der `foreach`-Schleife in `Main` verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="f5a69-111">You can see that the entire array of strings is not converted to uppercase before each item in the returned collection is processed in the `foreach` loop in `Main`.</span></span>  
  
 <span data-ttu-id="f5a69-112">Im nächsten Thema dieses Lernprogramms wird das Verketten von Abfragen gezeigt:</span><span class="sxs-lookup"><span data-stu-id="f5a69-112">The next topic in this tutorial illustrates chaining queries together:</span></span>  
  
- [<span data-ttu-id="f5a69-113">Beispiel für das Verketten von Abfragen (C#)</span><span class="sxs-lookup"><span data-stu-id="f5a69-113">Chaining Queries Example (C#)</span></span>](./chaining-queries-example.md)  
  
## <a name="see-also"></a><span data-ttu-id="f5a69-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5a69-114">See also</span></span>

- [<span data-ttu-id="f5a69-115">Tutorial: Verketten von Abfragen (C#)</span><span class="sxs-lookup"><span data-stu-id="f5a69-115">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
