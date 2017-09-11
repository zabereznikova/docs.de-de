---
title: 'Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (C#)'
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
ms.assetid: 8e8945f0-4aba-439d-8d5d-c8d1eeef4e71
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8089da9a1502b48018929978550bd2ceb2c0ec20
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-c"></a><span data-ttu-id="3fe94-102">Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="3fe94-102">How to: Find the Set Difference Between Two Lists (LINQ) (C#)</span></span>
<span data-ttu-id="3fe94-103">In diesem Beispiel wird veranschaulicht, wie Sie mit LINQ zwei Listen mit Zeichenfolgen vergleichen und die Zeilen ausgeben, die in names1.txt, aber nicht in names2.txt enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="3fe94-103">This example shows how to use LINQ to compare two lists of strings and output those lines that are in names1.txt but not in names2.txt.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="3fe94-104">So erstellen Sie die Datendateien</span><span class="sxs-lookup"><span data-stu-id="3fe94-104">To create the data files</span></span>  
  
1.  <span data-ttu-id="3fe94-105">Kopieren Sie names1.txt und names2.txt in den Projektmappenordner, sowie in [Vorgehensweise: Kombinieren und Vergleichen Zeichenfolgenauflistungen (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md).</span><span class="sxs-lookup"><span data-stu-id="3fe94-105">Copy names1.txt and names2.txt to your solution folder as shown in [How to: Combine and Compare String Collections (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fe94-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3fe94-106">Example</span></span>  
  
```csharp  
class CompareLists  
{          
    static void Main()  
    {  
        // Create the IEnumerable data sources.  
        string[] names1 = System.IO.File.ReadAllLines(@"../../../names1.txt");  
        string[] names2 = System.IO.File.ReadAllLines(@"../../../names2.txt");  
  
        // Create the query. Note that method syntax must be used here.  
        IEnumerable<string> differenceQuery =  
          names1.Except(names2);  
  
        // Execute the query.  
        Console.WriteLine("The following lines are in names1.txt but not names2.txt");  
        foreach (string s in differenceQuery)  
            Console.WriteLine(s);  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
     The following lines are in names1.txt but not names2.txt  
    Potra, Cristina  
    Noriega, Fabricio  
    Aw, Kam Foo  
    Toyoshima, Tim  
    Guy, Wey Yuan  
    Garcia, Debra  
     */  
```  
  
 <span data-ttu-id="3fe94-107">Einige Arten der Abfragevorgänge in C# wie <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A> und <xref:System.Linq.Enumerable.Concat%2A> können nur in methodenbasierter Syntax ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="3fe94-107">Some types of query operations in C#, such as <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, and <xref:System.Linq.Enumerable.Concat%2A>, can only be expressed in method-based syntax.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3fe94-108">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="3fe94-108">Compiling the Code</span></span>  
 <span data-ttu-id="3fe94-109">Erstellen Sie ein neues Projekt, das auf die .NET Framework-Version 3.5 oder höher ausgelegt ist, mit einer Referenz zu System.Core.dll und `using`-Direktiven für System.Linq- und System.IO-Namespaces.</span><span class="sxs-lookup"><span data-stu-id="3fe94-109">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fe94-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3fe94-110">See Also</span></span>  
 [<span data-ttu-id="3fe94-111">LINQ und Zeichenfolgen (C#)</span><span class="sxs-lookup"><span data-stu-id="3fe94-111">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)

