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
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a>Vorgehensweise: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (C#)

Da die <xref:System.String>-Klasse die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementiert, kann jede Zeichenfolge als Folge von Zeichen abgefragt werden. Dies ist allerdings kein üblicher Einsatz von LINQ. Verwenden Sie für komplex Musterabgleichvorgänge die <xref:System.Text.RegularExpressions.Regex>-Klasse.  
  
## <a name="example"></a>Beispiel  

 In folgendem Beispiel wird eine Zeichenfolge abgefragt, um die Zahl von enthaltenen numerischen Ziffern zu bestimmen. Beachten Sie, dass die Abfrage „wieder verwendet“ wird, nachdem sie zum ersten Mal ausgeführt wurde. Dies ist möglich, da die Abfrage selbst keine Ergebnisse speichert.  
  
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
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  

 Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ und Zeichenfolgen (C#)](./linq-and-strings.md)
- [Vorgehensweise: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (C#)](./how-to-combine-linq-queries-with-regular-expressions.md)
