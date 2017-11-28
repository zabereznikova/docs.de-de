---
title: Verketten von Standardabfrageoperatoren (C#)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 66f2b0a9-2c23-4735-988e-bbc9dfb55c7b
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 47e936bffd79784b0ee6850bfc29d1d1f5b3224d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="chaining-standard-query-operators-together-c"></a><span data-ttu-id="f9b07-102">Verketten von Standardabfrageoperatoren (C#)</span><span class="sxs-lookup"><span data-stu-id="f9b07-102">Chaining Standard Query Operators Together (C#)</span></span>
<span data-ttu-id="f9b07-103">Dies ist das letzte Thema von [Tutorial: Verketten von Abfragen (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md).</span><span class="sxs-lookup"><span data-stu-id="f9b07-103">This is the final topic in the [Tutorial: Chaining Queries Together (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md) tutorial.</span></span>  
  
 <span data-ttu-id="f9b07-104">Die Standardabfrageoperatoren können ebenfalls verkettet werden.</span><span class="sxs-lookup"><span data-stu-id="f9b07-104">The standard query operators can also be chained together.</span></span> <span data-ttu-id="f9b07-105">So können Sie z. B. den <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType>-Operator verwenden; dieser funktioniert ebenfalls verzögert.</span><span class="sxs-lookup"><span data-stu-id="f9b07-105">For example, you can interject the <xref:System.Linq.Enumerable.Where%2A?displayProperty=nameWithType> operator, and it also operates in a lazy fashion.</span></span> <span data-ttu-id="f9b07-106">Er materialisiert keinerlei Zwischenergebnisse.</span><span class="sxs-lookup"><span data-stu-id="f9b07-106">No intermediate results are materialized by it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9b07-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9b07-107">Example</span></span>  
 <span data-ttu-id="f9b07-108">In diesem Beispiel wird die <xref:System.Linq.Enumerable.Where%2A>-Methode aufgerufen, bevor `ConvertCollectionToUpperCase` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f9b07-108">In this example, the <xref:System.Linq.Enumerable.Where%2A> method is called before calling `ConvertCollectionToUpperCase`.</span></span> <span data-ttu-id="f9b07-109">Die <xref:System.Linq.Enumerable.Where%2A>-Methode funktioniert fast genauso wie die in den vorherigen Beispielen dieses Lernprogramms verwendeten verzögerten Methoden `ConvertCollectionToUpperCase` und `AppendString`.</span><span class="sxs-lookup"><span data-stu-id="f9b07-109">The <xref:System.Linq.Enumerable.Where%2A> method operates in almost exactly the same way as the lazy methods used in previous examples in this tutorial, `ConvertCollectionToUpperCase` and `AppendString`.</span></span>  
  
 <span data-ttu-id="f9b07-110">Ein Unterschied besteht darin, dass die <xref:System.Linq.Enumerable.Where%2A>-Methode in diesem Fall ihre Quellauflistung durchläuft, dabei feststellt, dass das erste Element kein Prädikat übergibt, und dann zum nächsten Element geht, das ein Prädikat übergibt.</span><span class="sxs-lookup"><span data-stu-id="f9b07-110">One difference is that in this case, the <xref:System.Linq.Enumerable.Where%2A> method iterates through its source collection, determines that the first item does not pass the predicate, and then gets the next item, which does pass.</span></span> <span data-ttu-id="f9b07-111">Anschließend gibt die Methode das zweite Element zurück.</span><span class="sxs-lookup"><span data-stu-id="f9b07-111">It then yields the second item.</span></span>  
  
 <span data-ttu-id="f9b07-112">Die Grundidee ist aber dieselbe: Zwischenauflistungen werden nur dann materialisiert, wenn dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="f9b07-112">However, the basic idea is the same: Intermediate collections are not materialized unless they have to be.</span></span>  
  
 <span data-ttu-id="f9b07-113">Bei Verwendung von Abfrageausdrücken werden diese in Aufrufe für die Standardabfrageoperatoren umgewandelt, und es werden dieselben Prinzipien angewendet.</span><span class="sxs-lookup"><span data-stu-id="f9b07-113">When query expressions are used, they are converted to calls to the standard query operators, and the same principles apply.</span></span>  
  
 <span data-ttu-id="f9b07-114">Alle Beispiele in diesem Abschnitt, die Office Open-XML-Dokumente abfragen, verwenden dasselbe Prinzip.</span><span class="sxs-lookup"><span data-stu-id="f9b07-114">All of the examples in this section that are querying Office Open XML documents use the same principle.</span></span> <span data-ttu-id="f9b07-115">Die verzögerte Ausführung und die verzögerte Auswertung sind nur zwei der grundlegenden Konzepte, mit denen Sie vertraut sein müssen, um LINQ (und LINQ to XML) effektiv nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="f9b07-115">Deferred execution and lazy evaluation are some of the fundamental concepts that you must understand  to use LINQ (and LINQ to XML) effectively.</span></span>  
  
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
  
 <span data-ttu-id="f9b07-116">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="f9b07-116">This example produces the following output:</span></span>  
  
```  
ToUpper: source >abc<  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9b07-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9b07-117">See Also</span></span>  
 [<span data-ttu-id="f9b07-118">Tutorial: Verketten von Abfragen (C#)</span><span class="sxs-lookup"><span data-stu-id="f9b07-118">Tutorial: Chaining Queries Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
