---
title: Beispiel für das Verketten von Abfragen (C#)
ms.date: 07/20/2015
ms.assetid: abbca162-d95e-43af-b92c-e46e6aa2540e
ms.openlocfilehash: 45e3a4f341ca8eb06ff0f553e0f933956e6c6546
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "70205413"
---
# <a name="chaining-queries-example-c"></a>Beispiel für das Verketten von Abfragen (C#)
Dieses Beispiel baut auf dem vorherigen Beispiel auf und zeigt, was passiert, wenn Sie zwei Abfragen miteinander verketten, die beide mit verzögerter Ausführung und verzögerter Auswertung arbeiten.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird eine andere Erweiterungsmethode eingeführt: `AppendString`. Diese Methode fügt jeder Zeichenfolge in der Quellauflistung eine bestimmte Zeichenfolge an und gibt dann die neuen Zeichenfolgen zurück.  
  
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
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```output  
ToUpper: source >abc<  
AppendString: source >ABC<  
Main: str >ABC!!!<  
  
ToUpper: source >def<  
AppendString: source >DEF<  
Main: str >DEF!!!<  
  
ToUpper: source >ghi<  
AppendString: source >GHI<  
Main: str >GHI!!!<  
```  
  
 In diesem Beispiel können Sie sehen, dass jede Erweiterungsmethode für jedes Element in der Quellauflistung immer nur einmal gleichzeitig ausgeführt wird.  
  
 In diesem Beispiel wird deutlich, dass auch dann, wenn Abfragen verkettet wurden, die Auflistungen zurückgeben, keine Materialisierung von Zwischenauflistungen erfolgt. Stattdessen wird jedes Element von einer verzögerten Methode an die nächste übergeben. Auf diese Weise wird wesentlich weniger Speicher beansprucht, als wenn zunächst ein Array von Zeichenfolgen hergenommen und dann ein zweites Array von Zeichenfolgen erstellt wird, die in Großbuchstaben umgewandelt werden, woraufhin schließlich ein drittes Array von Zeichenfolgen erstellt wird, in dem an jede Zeichenfolge das Ausrufezeichen angefügt wurde.  
  
 Im nächsten Thema dieses Lernprogramms wird die Zwischenmaterialisierung erläutert:  
  
- [Zwischenmaterialisierung (C#)](./intermediate-materialization.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Tutorial: Chaining Queries Together (C#) (Tutorial: Verketten von Abfragen (C#))](./deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)
