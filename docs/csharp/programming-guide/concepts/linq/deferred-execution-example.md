---
title: Beispiel für eine verzögerte Ausführung (C#)
ms.date: 07/20/2015
ms.assetid: 50f4fbac-81fe-4f26-aedf-506e21419b19
ms.openlocfilehash: 0ad1ed2998cfbd612f7f2b60a0d15c7ffcef0daf
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43518474"
---
# <a name="deferred-execution-example-c"></a>Beispiel für eine verzögerte Ausführung (C#)
In diesem Thema wird gezeigt, wie sich die verzögerte Ausführung (Deferred Execution) und die verzögerte Auswertung (Lazy Evaluation) auf die Ausführung Ihrer LINQ to XML-Abfragen auswirken.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, in welcher Reihenfolge die Ausführung erfolgt, wenn eine Erweiterungsmethode verwendet wird, die mit verzögerter Ausführung arbeitet. Das Beispiel deklariert ein Array aus drei Zeichenfolgen. Anschließend durchläuft es die von `ConvertCollectionToUpperCase` zurückgegebene Auflistung.  
  
```csharp  
public static class LocalExtensions  
{  
    public static IEnumerable<string>  
      ConvertCollectionToUpperCase(this IEnumerable<string> source)  
    {  
        foreach (string str in source)  
        {  
            Console.WriteLine("ToUpper: source {0}", str);  
            yield return str.ToUpper();  
        }  
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        string[] stringArray = { "abc", "def", "ghi" };  
  
        var q = from str in stringArray.ConvertCollectionToUpperCase()  
                select str;  
  
        foreach (string str in q)  
            Console.WriteLine("Main: str {0}", str);  
    }  
}  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
ToUpper: source abc  
Main: str ABC  
ToUpper: source def  
Main: str DEF  
ToUpper: source ghi  
Main: str GHI  
```  
  
 Beachten Sie, dass beim Durchlaufen der von `ConvertCollectionToUpperCase` zurückgegebenen Auflistung erst jedes Element aus dem Quellzeichenfolgenarray abgerufen und in Großbuchstaben umgewandelt wird, bevor das nächste Element aus dem Quellzeichenfolgenarray abgerufen wird.  
  
 Wie Sie sehen, wird das gesamte Array von Zeichenfolgen erst dann in Großbuchstaben umgewandelt, wenn jedes Element in der zurückgegebenen Auflistung in der `foreach`-Schleife in `Main` verarbeitet wurde.  
  
 Im nächsten Thema dieses Lernprogramms wird das Verketten von Abfragen gezeigt:  
  
-   [Beispiel für das Verketten von Abfragen (C#)](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)  
  
## <a name="see-also"></a>Siehe auch

- [Tutorial: Verketten von Abfragen (C#)](../../../../csharp/programming-guide/concepts/linq/tutorial-chaining-queries-together.md)
