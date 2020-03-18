---
title: Zwischenmaterialisierung (C#)
ms.date: 07/20/2015
ms.assetid: 7922d38f-5044-41cf-8e17-7173d6553a5e
ms.openlocfilehash: af1eb7df7da02d8e72fc102cda4ee5f329dc7974
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253165"
---
# <a name="intermediate-materialization-c"></a><span data-ttu-id="2bd1d-102">Zwischenmaterialisierung (C#)</span><span class="sxs-lookup"><span data-stu-id="2bd1d-102">Intermediate Materialization (C#)</span></span>
<span data-ttu-id="2bd1d-103">Bei fehlender Sorgfalt kann es in bestimmten Situationen dazu kommen, dass die Auflistungen in Ihren Abfragen vorzeitig materialisiert werden, wodurch sich das Speicher- und Leistungsprofil Ihrer Anwendung radikal ändert.</span><span class="sxs-lookup"><span data-stu-id="2bd1d-103">If you are not careful, in some situations you can drastically alter the memory and performance profile of your application by causing premature materialization of collections in your queries.</span></span> <span data-ttu-id="2bd1d-104">Einige Standardabfrageoperatoren verursachen die Materialisierung ihrer Quellauflistung, bevor auch nur ein einziges Element zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2bd1d-104">Some standard query operators cause materialization of their source collection before yielding a single element.</span></span> <span data-ttu-id="2bd1d-105">So durchläuft beispielsweise <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> zuerst die gesamte Quellauflistung, sortiert dann alle Elemente und gibt zum Schluss das erste Element zurück.</span><span class="sxs-lookup"><span data-stu-id="2bd1d-105">For example, <xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType> first iterates through its entire source collection, then sorts all items, and then finally yields the first item.</span></span> <span data-ttu-id="2bd1d-106">Das bedeutet, dass es zwar aufwendig ist, das erste Element einer sortierten Auflistung abzurufen, das Abrufen aller folgenden Elemente hingegen ist nicht aufwendig.</span><span class="sxs-lookup"><span data-stu-id="2bd1d-106">This means that it is expensive to get the first item of an ordered collection; each item thereafter is not expensive.</span></span> <span data-ttu-id="2bd1d-107">Dies ist sinnvoll, denn anders würde dieser Abfrageoperator nicht funktionieren.</span><span class="sxs-lookup"><span data-stu-id="2bd1d-107">This makes sense: It would be impossible for that query operator to do otherwise.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2bd1d-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2bd1d-108">Example</span></span>  
 <span data-ttu-id="2bd1d-109">Dieses Beispiel ändert das vorherige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="2bd1d-109">This example alters the previous example.</span></span> <span data-ttu-id="2bd1d-110">Die `AppendString`-Methode ruft vor dem Durchlaufen der Quelle <xref:System.Linq.Enumerable.ToList%2A> auf.</span><span class="sxs-lookup"><span data-stu-id="2bd1d-110">The `AppendString` method calls <xref:System.Linq.Enumerable.ToList%2A> before iterating through the source.</span></span> <span data-ttu-id="2bd1d-111">Dies verursacht eine Materialisierung.</span><span class="sxs-lookup"><span data-stu-id="2bd1d-111">This causes materialization.</span></span>  
  
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
        // the following statement materializes the source collection in a List<T>  
        // before iterating through it  
        foreach (string str in source.ToList())  
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
  
 <span data-ttu-id="2bd1d-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="2bd1d-112">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
ToUpper: source >def<  
ToUpper: source >ghi<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 <span data-ttu-id="2bd1d-113">Diesem Beispiel können Sie entnehmen, dass der Aufruf von <xref:System.Linq.Enumerable.ToList%2A>`AppendString` dazu veranlasst, vor der Rückgabe des ersten Elements seine gesamte Quelle aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="2bd1d-113">In this example, you can see that the call to <xref:System.Linq.Enumerable.ToList%2A> causes `AppendString` to enumerate its entire source before yielding the first item.</span></span> <span data-ttu-id="2bd1d-114">Wenn die Quelle ein großes Array wäre, würde dies das Arbeitsspeicherprofil der Anwendung deutlich verändern.</span><span class="sxs-lookup"><span data-stu-id="2bd1d-114">If the source were a large array, this would significantly alter the memory profile of the application.</span></span>  
  
 <span data-ttu-id="2bd1d-115">Standardabfrageoperatoren können auch miteinander verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="2bd1d-115">Standard query operators can also be chained together.</span></span> <span data-ttu-id="2bd1d-116">Informationen dazu finden Sie im letzten Thema dieses Lernprogramms:</span><span class="sxs-lookup"><span data-stu-id="2bd1d-116">The final topic in this tutorial illustrates this.</span></span>  
  
- [<span data-ttu-id="2bd1d-117">Verketten von Standardabfrageoperatoren (C#)</span><span class="sxs-lookup"><span data-stu-id="2bd1d-117">Chaining Standard Query Operators Together (C#)</span></span>](./chaining-standard-query-operators-together.md)  
  
## <a name="see-also"></a><span data-ttu-id="2bd1d-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2bd1d-118">See also</span></span>

- [<span data-ttu-id="2bd1d-119">Tutorial: Chaining Queries Together (C#) (Tutorial: Verketten von Abfragen (C#))</span><span class="sxs-lookup"><span data-stu-id="2bd1d-119">Tutorial: Chaining Queries Together (C#)</span></span>](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
