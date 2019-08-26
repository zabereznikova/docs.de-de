---
title: 'Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: 8e8945f0-4aba-439d-8d5d-c8d1eeef4e71
ms.openlocfilehash: decdbe45afd12581a53ed70ec843ee72f54f0409
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69593342"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-c"></a>Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (C#)
In diesem Beispiel wird veranschaulicht, wie Sie mit LINQ zwei Listen mit Zeichenfolgen vergleichen und die Zeilen ausgeben, die in names1.txt, aber nicht in names2.txt enthalten sind.  
  
### <a name="to-create-the-data-files"></a>So erstellen Sie die Datendateien  
  
1. Kopieren Sie die Dateien „names1.txt“ und „names2.txt“ in den Projektmappenordner, wie unter [Vorgehensweise: Verbinden und Vergleichen von Zeichenfolgenauflistungen (LINQ) (C#)](./how-to-combine-and-compare-string-collections-linq.md) gezeigt wird.  
  
## <a name="example"></a>Beispiel  
  
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
  
 Einige Arten der Abfragevorgänge in C# wie <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A> und <xref:System.Linq.Enumerable.Concat%2A> können nur in methodenbasierter Syntax ausgedrückt werden.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ und Zeichenfolgen (C#)](./linq-and-strings.md)
