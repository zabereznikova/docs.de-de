---
title: 'Vorgehensweise: Abfragen von ArrayList mit LINQ (C#)'
ms.date: 07/20/2015
ms.assetid: 2bfb471c-6e9a-4e60-bd83-4a1778abde11
ms.openlocfilehash: b8edb90d33c92324d4f76c7e6977641fe4499d9d
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345704"
---
# <a name="how-to-query-an-arraylist-with-linq-c"></a><span data-ttu-id="6aa61-102">Vorgehensweise: Abfragen von ArrayList mit LINQ (C#)</span><span class="sxs-lookup"><span data-stu-id="6aa61-102">How to query an ArrayList with LINQ (C#)</span></span>
<span data-ttu-id="6aa61-103">Bei Verwendung von LINQ zum Abfragen nicht generischer <xref:System.Collections.IEnumerable>-Auflistungen wie z.B. <xref:System.Collections.ArrayList> müssen Sie den Typ der Bereichsvariablen entsprechend dem spezifischen Typ der Objekte in der Auflistung explizit deklarieren.</span><span class="sxs-lookup"><span data-stu-id="6aa61-103">When using LINQ to query non-generic <xref:System.Collections.IEnumerable> collections such as <xref:System.Collections.ArrayList>, you must explicitly declare the type of the range variable to reflect the specific type of the objects in the collection.</span></span> <span data-ttu-id="6aa61-104">Wenn Sie zum Beispiel eine <xref:System.Collections.ArrayList> mit `Student`-Objekten haben, sollte die [from-Klausel](../../../language-reference/keywords/from-clause.md) wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="6aa61-104">For example, if you have an <xref:System.Collections.ArrayList> of `Student` objects, your [from clause](../../../language-reference/keywords/from-clause.md) should look like this:</span></span>  
  
```csharp
var query = from Student s in arrList  
//...
```  
  
 <span data-ttu-id="6aa61-105">Indem Sie den Typ der Bereichsvariablen angeben, wandeln Sie jedes Element in der <xref:System.Collections.ArrayList> in ein `Student` um.</span><span class="sxs-lookup"><span data-stu-id="6aa61-105">By specifying the type of the range variable, you are casting each item in the <xref:System.Collections.ArrayList> to a `Student`.</span></span>  
  
 <span data-ttu-id="6aa61-106">Die Verwendung einer explizit typisierten Bereichsvariablen in einem Abfrageausdruck entspricht dem Aufrufen der <xref:System.Linq.Enumerable.Cast%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="6aa61-106">The use of an explicitly typed range variable in a query expression is equivalent to calling the <xref:System.Linq.Enumerable.Cast%2A> method.</span></span> <span data-ttu-id="6aa61-107"><xref:System.Linq.Enumerable.Cast%2A> löst eine Ausnahme aus, wenn bei der Umwandlung ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="6aa61-107"><xref:System.Linq.Enumerable.Cast%2A> throws an exception if the specified cast cannot be performed.</span></span> <span data-ttu-id="6aa61-108"><xref:System.Linq.Enumerable.Cast%2A> und <xref:System.Linq.Enumerable.OfType%2A> sind zwei Standardabfrageoperator-Methoden, die mit nicht generischen <xref:System.Collections.IEnumerable>-Typen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="6aa61-108"><xref:System.Linq.Enumerable.Cast%2A> and <xref:System.Linq.Enumerable.OfType%2A> are the two Standard Query Operator methods that operate on non-generic <xref:System.Collections.IEnumerable> types.</span></span> <span data-ttu-id="6aa61-109">Weitere Informationen finden Sie unter [Typbeziehungen in LINQ-Abfragevorgängen](./type-relationships-in-linq-query-operations.md).</span><span class="sxs-lookup"><span data-stu-id="6aa61-109">For more information, see [Type Relationships in LINQ Query Operations](./type-relationships-in-linq-query-operations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6aa61-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6aa61-110">Example</span></span>  
 <span data-ttu-id="6aa61-111">Im folgenden Beispiel wird eine einfache Abfrage von <xref:System.Collections.ArrayList> veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6aa61-111">The following example shows a simple query over an <xref:System.Collections.ArrayList>.</span></span> <span data-ttu-id="6aa61-112">Beachten Sie, dass in diesem Beispiel Objektinitialisierer verwendet werden, wenn der Code die <xref:System.Collections.ArrayList.Add%2A>-Methode aufruft, aber dies ist keine Voraussetzung.</span><span class="sxs-lookup"><span data-stu-id="6aa61-112">Note that this example uses object initializers when the code calls the <xref:System.Collections.ArrayList.Add%2A> method, but this is not a requirement.</span></span>  
  
```csharp  
using System;  
using System.Collections;  
using System.Linq;  
  
namespace NonGenericLINQ  
{  
    public class Student  
    {  
        public string FirstName { get; set; }  
        public string LastName { get; set; }  
        public int[] Scores { get; set; }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ArrayList arrList = new ArrayList();  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Svetlana", LastName = "Omelchenko", Scores = new int[] { 98, 92, 81, 60 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Claire", LastName = "O’Donnell", Scores = new int[] { 75, 84, 91, 39 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Sven", LastName = "Mortensen", Scores = new int[] { 88, 94, 65, 91 }  
                    });  
            arrList.Add(  
                new Student  
                    {  
                        FirstName = "Cesar", LastName = "Garcia", Scores = new int[] { 97, 89, 85, 82 }  
                    });  
  
            var query = from Student student in arrList  
                        where student.Scores[0] > 95  
                        select student;  
  
            foreach (Student s in query)  
                Console.WriteLine(s.LastName + ": " + s.Scores[0]);  
  
            // Keep the console window open in debug mode.  
            Console.WriteLine("Press any key to exit.");  
            Console.ReadKey();  
        }  
    }  
}  
/* Output:   
    Omelchenko: 98  
    Garcia: 97  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="6aa61-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6aa61-113">See also</span></span>

- [<span data-ttu-id="6aa61-114">LINQ to Objects (C#)</span><span class="sxs-lookup"><span data-stu-id="6aa61-114">LINQ to Objects (C#)</span></span>](./linq-to-objects.md)
