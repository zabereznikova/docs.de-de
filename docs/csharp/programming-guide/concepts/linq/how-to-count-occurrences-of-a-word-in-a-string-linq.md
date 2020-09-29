---
title: 'Vorgehensweise: Zählen der Vorkommen eines Worts in einer Zeichenfolge (LINQ) (C#)'
description: Dieses Beispiel zeigt, wie Sie eine LINQ-Abfrage in C# verwenden, um zu zählen, wie oft ein bestimmtes Wort in einer Zeichenfolge vorkommt. Die Split-Methode wird verwendet, um ein Array von Wörtern zu erstellen.
ms.date: 07/20/2015
ms.assetid: f8e6f546-7c14-4aa1-8a75-e8d09f3b8ccd
ms.openlocfilehash: b354947c59747e49b5f3d099ebc3ea891fb4af90
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159071"
---
# <a name="how-to-count-occurrences-of-a-word-in-a-string-linq-c"></a><span data-ttu-id="2be0a-104">Vorgehensweise: Zählen der Vorkommen eines Worts in einer Zeichenfolge (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="2be0a-104">How to count occurrences of a word in a string (LINQ) (C#)</span></span>

<span data-ttu-id="2be0a-105">Dieses Beispiel zeigt, wie Sie eine LINQ-Abfrage verwenden, um die Vorkommen eines angegebenen Worts in einer Zeichenfolge zu zählen.</span><span class="sxs-lookup"><span data-stu-id="2be0a-105">This example shows how to use a LINQ query to count the occurrences of a specified word in a string.</span></span> <span data-ttu-id="2be0a-106">Beachten Sie, dass zuerst die <xref:System.String.Split%2A>-Methode aufgerufen wird, um ein Array von Worten zu erstellen, damit die Zählung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2be0a-106">Note that to perform the count, first the <xref:System.String.Split%2A> method is called to create an array of words.</span></span> <span data-ttu-id="2be0a-107">Für die <xref:System.String.Split%2A>-Methode werden Leistungskosten berechnet.</span><span class="sxs-lookup"><span data-stu-id="2be0a-107">There is a performance cost to the <xref:System.String.Split%2A> method.</span></span> <span data-ttu-id="2be0a-108">Wenn der einzige Vorgang in der Zeichenfolge die Zählung der Wörter ist, überlegen Sie sich, ob Sie nicht stattdessen die <xref:System.Text.RegularExpressions.Regex.Matches%2A>- oder <xref:System.String.IndexOf%2A>-Methode verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="2be0a-108">If the only operation on the string is to count the words, you should consider using the <xref:System.Text.RegularExpressions.Regex.Matches%2A> or <xref:System.String.IndexOf%2A> methods instead.</span></span> <span data-ttu-id="2be0a-109">Wenn jedoch die Leistung kein zentrales Problem ist oder Sie die Sequenz in eine Reihenfolge gebracht haben, um andere Abfragetypen darauf auszuführen, macht es Sinn, auch LINQ zum Zählen der Wörter oder Sätze zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="2be0a-109">However, if performance is not a critical issue, or you have already split the sentence in order to perform other types of queries over it, then it makes sense to use LINQ to count the words or phrases as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2be0a-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2be0a-110">Example</span></span>  
  
```csharp  
class CountWords  
{  
    static void Main()  
    {  
        string text = @"Historically, the world of data and the world of objects" +  
          @" have not been well integrated. Programmers work in C# or Visual Basic" +  
          @" and also in SQL or XQuery. On the one side are concepts such as classes," +  
          @" objects, fields, inheritance, and .NET APIs. On the other side" +  
          @" are tables, columns, rows, nodes, and separate languages for dealing with" +  
          @" them. Data types often require translation between the two worlds; there are" +  
          @" different standard functions. Because the object world has no notion of query, a" +  
          @" query can only be represented as a string without compile-time type checking or" +  
          @" IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to" +  
          @" objects in memory is often tedious and error-prone.";  
  
        string searchTerm = "data";  
  
        //Convert the string into an array of words  
        string[] source = text.Split(new char[] { '.', '?', '!', ' ', ';', ':', ',' }, StringSplitOptions.RemoveEmptyEntries);  
  
        // Create the query.  Use ToLowerInvariant to match "data" and "Data"
        var matchQuery = from word in source  
                         where word.ToLowerInvariant() == searchTerm.ToLowerInvariant()  
                         select word;  
  
        // Count the matches, which executes the query.  
        int wordCount = matchQuery.Count();  
        Console.WriteLine("{0} occurrences(s) of the search term \"{1}\" were found.", wordCount, searchTerm);  
  
        // Keep console window open in debug mode  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
   3 occurrences(s) of the search term "data" were found.  
*/  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2be0a-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2be0a-111">Compiling the Code</span></span>  

 <span data-ttu-id="2be0a-112">Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.</span><span class="sxs-lookup"><span data-stu-id="2be0a-112">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2be0a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2be0a-113">See also</span></span>

- [<span data-ttu-id="2be0a-114">LINQ und Zeichenfolgen (C#)</span><span class="sxs-lookup"><span data-stu-id="2be0a-114">LINQ and Strings (C#)</span></span>](./linq-and-strings.md)
