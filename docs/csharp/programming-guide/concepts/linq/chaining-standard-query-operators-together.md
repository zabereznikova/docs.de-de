---
title: Verketten von Standardabfrageoperatoren (C#)
description: Dieses Beispiel zeigt, wie Standardabfrageoperatoren in C# ebenfalls verkettet werden können. Die Abfrage materialisiert keine Zwischenergebnisse.
ms.date: 07/20/2015
ms.assetid: 66f2b0a9-2c23-4735-988e-bbc9dfb55c7b
ms.openlocfilehash: 41a7e4c7910c783d07181fe16254b0cac6902794
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104073"
---
# <a name="chaining-standard-query-operators-together-c"></a><span data-ttu-id="a60a0-104">Verketten von Standardabfrageoperatoren (C#)</span><span class="sxs-lookup"><span data-stu-id="a60a0-104">Chaining Standard Query Operators Together (C#)</span></span>
<span data-ttu-id="a60a0-105">Das ist das letzte Thema im [Tutorial: Verketten von Abfragen (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a60a0-105">This is the final topic in the [Tutorial: Chaining Queries Together (C#)](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md) tutorial.</span></span>  
  
 <span data-ttu-id="a60a0-106">Die Standardabfrageoperatoren können ebenfalls verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="a60a0-106">The standard query operators can also be chained together.</span></span> <span data-ttu-id="a60a0-107">So können Sie z. B. den <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType>-Operator verwenden; dieser funktioniert ebenfalls verzögert.</span><span class="sxs-lookup"><span data-stu-id="a60a0-107">For example, you can interject the <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> operator, and it also operates in a lazy fashion.</span></span> <span data-ttu-id="a60a0-108">Er materialisiert keinerlei Zwischenergebnisse.</span><span class="sxs-lookup"><span data-stu-id="a60a0-108">No intermediate results are materialized by it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a60a0-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a60a0-109">Example</span></span>  
 <span data-ttu-id="a60a0-110">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Where%2A>-Methode aufgerufen, bevor `ConvertCollectionToUpperCase` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a60a0-110">In this example, the <xref:System.Linq.Enumerable.Where%2A> method is called before calling `ConvertCollectionToUpperCase`.</span></span> <span data-ttu-id="a60a0-111">Die <xref:System.Linq.Enumerable.Where%2A>-Methode funktioniert fast genauso wie die in den vorherigen Beispielen dieses Lernprogramms verwendeten verzögerten Methoden `ConvertCollectionToUpperCase` und `AppendString`.</span><span class="sxs-lookup"><span data-stu-id="a60a0-111">The <xref:System.Linq.Enumerable.Where%2A> method operates in almost exactly the same way as the lazy methods used in previous examples in this tutorial, `ConvertCollectionToUpperCase` and `AppendString`.</span></span>  
  
 <span data-ttu-id="a60a0-112">Ein Unterschied besteht darin, dass die <xref:System.Linq.Enumerable.Where%2A>-Methode in diesem Fall ihre Quellauflistung durchläuft, dabei feststellt, dass das erste Element kein Prädikat übergibt, und dann zum nächsten Element geht, das ein Prädikat übergibt.</span><span class="sxs-lookup"><span data-stu-id="a60a0-112">One difference is that in this case, the <xref:System.Linq.Enumerable.Where%2A> method iterates through its source collection, determines that the first item does not pass the predicate, and then gets the next item, which does pass.</span></span> <span data-ttu-id="a60a0-113">Anschließend gibt die Methode das zweite Element zurück.</span><span class="sxs-lookup"><span data-stu-id="a60a0-113">It then yields the second item.</span></span>  
  
 <span data-ttu-id="a60a0-114">Die Grundidee bleibt jedoch dieselbe: Zwischenauflistungen werden nur dann materialisiert, wenn dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a60a0-114">However, the basic idea is the same: Intermediate collections are not materialized unless they have to be.</span></span>  
  
 <span data-ttu-id="a60a0-115">Bei Verwendung von Abfrageausdrücken werden diese in Aufrufe für die Standardabfrageoperatoren umgewandelt, und es werden dieselben Prinzipien angewendet.</span><span class="sxs-lookup"><span data-stu-id="a60a0-115">When query expressions are used, they are converted to calls to the standard query operators, and the same principles apply.</span></span>  
  
 <span data-ttu-id="a60a0-116">Alle Beispiele in diesem Abschnitt, die Office Open-XML-Dokumente abfragen, verwenden dasselbe Prinzip.</span><span class="sxs-lookup"><span data-stu-id="a60a0-116">All of the examples in this section that are querying Office Open XML documents use the same principle.</span></span> <span data-ttu-id="a60a0-117">Die verzögerte Ausführung und die verzögerte Auswertung sind nur zwei der grundlegenden Konzepte, mit denen Sie vertraut sein müssen, um LINQ (und LINQ to XML) effektiv nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="a60a0-117">Deferred execution and lazy evaluation are some of the fundamental concepts that you must understand  to use LINQ (and LINQ to XML) effectively.</span></span>  
  
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
            where s.CompareTo("D") >= 0  
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
  
 <span data-ttu-id="a60a0-118">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a60a0-118">This example produces the following output:</span></span>  
  
```output  
ToUpper: source >abc<  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
