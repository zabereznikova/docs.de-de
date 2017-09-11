---
title: "Vorgehensweise: Zählen der Vorkommen eines Worts in einer Zeichenfolge (LINQ) (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: f8e6f546-7c14-4aa1-8a75-e8d09f3b8ccd
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4f4542dad23b49f38f4270d7a75c5aeb3921f1cf
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-count-occurrences-of-a-word-in-a-string-linq-c"></a><span data-ttu-id="423c5-102">Vorgehensweise: Zählen der Vorkommen eines Worts in einer Zeichenfolge (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="423c5-102">How to: Count Occurrences of a Word in a String (LINQ) (C#)</span></span>
<span data-ttu-id="423c5-103">Dieses Beispiel zeigt, wie Sie eine LINQ-Abfrage verwenden, um die Vorkommen eines angegebenen Worts in einer Zeichenfolge zu zählen.</span><span class="sxs-lookup"><span data-stu-id="423c5-103">This example shows how to use a LINQ query to count the occurrences of a specified word in a string.</span></span> <span data-ttu-id="423c5-104">Beachten Sie, dass zuerst die <xref:System.String.Split%2A>-Methode aufgerufen wird, um ein Array von Worten zu erstellen, damit die Zählung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="423c5-104">Note that to perform the count, first the <xref:System.String.Split%2A> method is called to create an array of words.</span></span> <span data-ttu-id="423c5-105">Für die <xref:System.String.Split%2A>-Methode werden Leistungskosten berechnet.</span><span class="sxs-lookup"><span data-stu-id="423c5-105">There is a performance cost to the <xref:System.String.Split%2A> method.</span></span> <span data-ttu-id="423c5-106">Wenn der einzige Vorgang in der Zeichenfolge die Zählung der Wörter ist, überlegen Sie sich, ob Sie nicht stattdessen die <xref:System.Text.RegularExpressions.Regex.Matches%2A>- oder <xref:System.String.IndexOf%2A>-Methode verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="423c5-106">If the only operation on the string is to count the words, you should consider using the <xref:System.Text.RegularExpressions.Regex.Matches%2A> or <xref:System.String.IndexOf%2A> methods instead.</span></span> <span data-ttu-id="423c5-107">Wenn jedoch die Leistung kein zentrales Problem ist oder Sie die Sequenz in eine Reihenfolge gebracht haben, um andere Abfragetypen darauf auszuführen, macht es Sinn, auch LINQ zum Zählen der Wörter oder Sätze zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="423c5-107">However, if performance is not a critical issue, or you have already split the sentence in order to perform other types of queries over it, then it makes sense to use LINQ to count the words or phrases as well.</span></span>  
  
## <a name="example"></a><span data-ttu-id="423c5-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="423c5-108">Example</span></span>  
  
```csharp  
class CountWords  
{  
    static void Main()  
    {  
        string text = @"Historically, the world of data and the world of objects" +  
          @" have not been well integrated. Programmers work in C# or Visual Basic" +  
          @" and also in SQL or XQuery. On the one side are concepts such as classes," +  
          @" objects, fields, inheritance, and .NET Framework APIs. On the other side" +  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="423c5-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="423c5-109">Compiling the Code</span></span>  
 <span data-ttu-id="423c5-110">Erstellen Sie ein neues Projekt, das auf die .NET Framework-Version 3.5 oder höher ausgelegt ist, mit einer Referenz zu System.Core.dll und `using`-Direktiven für System.Linq- und System.IO-Namespaces.</span><span class="sxs-lookup"><span data-stu-id="423c5-110">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="423c5-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="423c5-111">See Also</span></span>  
 [<span data-ttu-id="423c5-112">LINQ und Zeichenfolgen (C#)</span><span class="sxs-lookup"><span data-stu-id="423c5-112">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)

