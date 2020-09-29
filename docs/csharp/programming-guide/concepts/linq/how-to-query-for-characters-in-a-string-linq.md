---
title: 'Vorgehensweise: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (C#)'
description: Sie können eine Zeichenfolge in LINQ als eine Sequenz von Zeichen abfragen. In diesem C#-Beispiel wird eine Zeichenfolge abgefragt, um die Zahl von enthaltenen numerischen Ziffern zu bestimmen.
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: 73288924d057e720a744b853998a52437b9db481
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91153936"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a><span data-ttu-id="72c64-104">Vorgehensweise: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="72c64-104">How to query for characters in a string (LINQ) (C#)</span></span>

<span data-ttu-id="72c64-105">Da die <xref:System.String>-Klasse die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementiert, kann jede Zeichenfolge als Folge von Zeichen abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="72c64-105">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="72c64-106">Dies ist allerdings kein üblicher Einsatz von LINQ.</span><span class="sxs-lookup"><span data-stu-id="72c64-106">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="72c64-107">Verwenden Sie für komplex Musterabgleichvorgänge die <xref:System.Text.RegularExpressions.Regex>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="72c64-107">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="72c64-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="72c64-108">Example</span></span>  

 <span data-ttu-id="72c64-109">In folgendem Beispiel wird eine Zeichenfolge abgefragt, um die Zahl von enthaltenen numerischen Ziffern zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="72c64-109">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="72c64-110">Beachten Sie, dass die Abfrage „wieder verwendet“ wird, nachdem sie zum ersten Mal ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="72c64-110">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="72c64-111">Dies ist möglich, da die Abfrage selbst keine Ergebnisse speichert.</span><span class="sxs-lookup"><span data-stu-id="72c64-111">This is possible because the query itself does not store any actual results.</span></span>  
  
```csharp  
class QueryAString  
{  
    static void Main()  
    {  
        string aString = "ABCDE99F-J74-12-89A";  
  
        // Select only those characters that are numbers  
        IEnumerable<char> stringQuery =  
          from ch in aString  
          where Char.IsDigit(ch)  
          select ch;  
  
        // Execute the query  
        foreach (char c in stringQuery)  
            Console.Write(c + " ");  
  
        // Call the Count method on the existing query.  
        int count = stringQuery.Count();  
        Console.WriteLine("Count = {0}", count);  
  
        // Select all characters before the first '-'  
        IEnumerable<char> stringQuery2 = aString.TakeWhile(c => c != '-');  
  
        // Execute the second query  
        foreach (char c in stringQuery2)  
            Console.Write(c);  
  
        Console.WriteLine(System.Environment.NewLine + "Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
  Output: 9 9 7 4 1 2 8 9  
  Count = 8  
  ABCDE99F  
*/  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="72c64-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="72c64-112">Compiling the Code</span></span>  

 <span data-ttu-id="72c64-113">Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.</span><span class="sxs-lookup"><span data-stu-id="72c64-113">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72c64-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72c64-114">See also</span></span>

- [<span data-ttu-id="72c64-115">LINQ und Zeichenfolgen (C#)</span><span class="sxs-lookup"><span data-stu-id="72c64-115">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
- [<span data-ttu-id="72c64-116">Vorgehensweise: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (C#)</span><span class="sxs-lookup"><span data-stu-id="72c64-116">How to combine LINQ queries with regular expressions (C#)</span></span>](./how-to-combine-linq-queries-with-regular-expressions.md)
