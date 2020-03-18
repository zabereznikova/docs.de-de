---
title: Beispiel für das Verketten von Abfragen (C#)
ms.date: 07/20/2015
ms.assetid: abbca162-d95e-43af-b92c-e46e6aa2540e
ms.openlocfilehash: 45e3a4f341ca8eb06ff0f553e0f933956e6c6546
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70205413"
---
# <a name="chaining-queries-example-c"></a><span data-ttu-id="bfa50-102">Beispiel für das Verketten von Abfragen (C#)</span><span class="sxs-lookup"><span data-stu-id="bfa50-102">Chaining Queries Example (C#)</span></span>
<span data-ttu-id="bfa50-103">Dieses Beispiel baut auf dem vorherigen Beispiel auf und zeigt, was passiert, wenn Sie zwei Abfragen miteinander verketten, die beide mit verzögerter Ausführung und verzögerter Auswertung arbeiten.</span><span class="sxs-lookup"><span data-stu-id="bfa50-103">This example builds on the previous example and shows what happens when you chain together two queries that both use deferred execution and lazy evaluation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bfa50-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bfa50-104">Example</span></span>  
 <span data-ttu-id="bfa50-105">In diesem Beispiel wird eine andere Erweiterungsmethode eingeführt: `AppendString`. Diese Methode fügt jeder Zeichenfolge in der Quellauflistung eine bestimmte Zeichenfolge an und gibt dann die neuen Zeichenfolgen zurück.</span><span class="sxs-lookup"><span data-stu-id="bfa50-105">In this example, another extension method is introduced, `AppendString`, which appends a specified string onto every string in the source collection, and then yields the new strings.</span></span>  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source >{0}<", str);  
            yield return str.ToUpper();  
        }  
    }  
  
    public static IEnumerable<string>  
      AppendString(this IEnumerable<string> source, string stringToAppend)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("AppendString: source >{0}<", str);  
            yield return str + stringToAppend;  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        IEnumerable<string> q1 =  
            from s in stringArray.ConvertCollectionToUpperCase()  
            select s;  
  
        IEnumerable<string> q2 =  
            from s in q1.AppendString("!!!")  
            select s;  
  
        foreach (string str in q2)  
        {  
            Console.WriteLine("Main: str >{0}<", str);  
            Console.WriteLine();  
        }  
    }  
}  
```  
  
 <span data-ttu-id="bfa50-106">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="bfa50-106">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 <span data-ttu-id="bfa50-107">In diesem Beispiel können Sie sehen, dass jede Erweiterungsmethode für jedes Element in der Quellauflistung immer nur einmal gleichzeitig ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="bfa50-107">In this example, you can see that each extension method operates one at a time for each item in the source collection.</span></span>  
  
 <span data-ttu-id="bfa50-108">In diesem Beispiel wird deutlich, dass auch dann, wenn Abfragen verkettet wurden, die Auflistungen zurückgeben, keine Materialisierung von Zwischenauflistungen erfolgt.</span><span class="sxs-lookup"><span data-stu-id="bfa50-108">What should be clear from this example is that even though we have chained together queries that yield collections, no intermediate collections are materialized.</span></span> <span data-ttu-id="bfa50-109">Stattdessen wird jedes Element von einer verzögerten Methode an die nächste übergeben.</span><span class="sxs-lookup"><span data-stu-id="bfa50-109">Instead, each item is passed from one lazy method to the next.</span></span> <span data-ttu-id="bfa50-110">Auf diese Weise wird wesentlich weniger Speicher beansprucht, als wenn zunächst ein Array von Zeichenfolgen hergenommen und dann ein zweites Array von Zeichenfolgen erstellt wird, die in Großbuchstaben umgewandelt werden, woraufhin schließlich ein drittes Array von Zeichenfolgen erstellt wird, in dem an jede Zeichenfolge das Ausrufezeichen angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="bfa50-110">This results in a much smaller memory footprint than an approach that would first take one array of strings, then create a second array of strings that have been converted to uppercase, and finally create a third array of strings where each string has the exclamation points appended to it.</span></span>  
  
 <span data-ttu-id="bfa50-111">Im nächsten Thema dieses Lernprogramms wird die Zwischenmaterialisierung erläutert:</span><span class="sxs-lookup"><span data-stu-id="bfa50-111">The next topic in this tutorial illustrates intermediate materialization:</span></span>  
  
- [<span data-ttu-id="bfa50-112">Zwischenmaterialisierung (C#)</span><span class="sxs-lookup"><span data-stu-id="bfa50-112">Intermediate Materialization (C#)</span></span>](./intermediate-materialization.md)  
  
## <a name="see-also"></a><span data-ttu-id="bfa50-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bfa50-113">See also</span></span>

- [<span data-ttu-id="bfa50-114">Tutorial: Chaining Queries Together (C#) (Tutorial: Verketten von Abfragen (C#))</span><span class="sxs-lookup"><span data-stu-id="bfa50-114">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
