---
title: 'Vorgehensweise: Durchführen einer Streamingtransformation von Text in XML (C#)'
description: In diesem Artikel erfahren Sie, wie Sie eine Streamingtransformation von XML-Text in C# ausführen. Hierfür wird eine Textdatei zeilenweise gestreamt und eine LINQ-Abfrage zum Verarbeiten der Textdatei verwendet.
ms.date: 07/20/2015
ms.assetid: 9b3bd941-d0ff-4f2d-ae41-7c3b81d8fae6
ms.openlocfilehash: f933064be70d39b59cf7dbe51b4ee92e5226647a
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104744"
---
# <a name="how-to-perform-streaming-transformations-of-text-to-xml-c"></a>Vorgehensweise: Durchführen einer Streamingtransformation von Text in XML (C#)

Ein Ansatz für die Verarbeitung einer Textdatei besteht darin, eine Erweiterungsmethode zu schreiben, die die Textdatei mit dem `yield return`-Konstrukt zeilenweise streamt. Anschließend können Sie eine LINQ-Abfrage schreiben, die die Textdatei verzögert verarbeitet. Wenn Sie dann die Ausgabe mit <xref:System.Xml.Linq.XStreamingElement> streamen, erstellen Sie eine Transformation der Textdatei in XML, die, unabhängig von der Größe der ursprünglichen Textdatei, nur einen minimalen Teil des Arbeitsspeichers beansprucht.

 Beim Streamen von Transformationen gilt es jedoch, einige Punkte zu beachten. Streamingtransformationen eignen sich am besten in Situationen, in denen Sie die gesamte Datei auf einmal verarbeiten können und in denen Sie die Zeilen in derselben Reihenfolge wie im ursprünglichen Dokument verarbeiten können. Wenn Sie die Datei mehr als einmal verarbeiten müssen oder wenn Sie vor der Verarbeitung der Zeilen deren Reihenfolge ändern müssen, gehen viele Vorteile des Streamingverfahrens verloren.

## <a name="example"></a>Beispiel

 In diesem Beispiel wird die folgende Textdatei, <legacyBold>People.txt</legacyBold>, als Quelldatei verwendet:

```text
#This is a comment
1,Tai,Yee,Writer
2,Nikolay,Grachev,Programmer
3,David,Wright,Inventor
```

 Der folgende Code enthält eine Erweiterungsmethode, die die Zeilen der Textdatei verzögert streamt.

```csharp
public static class StreamReaderSequence
{
    public static IEnumerable<string> Lines(this StreamReader source)
    {
        if (source == null)
            throw new ArgumentNullException(nameof(source));

        string line;
        while ((line = source.ReadLine()) != null)
        {
            yield return line;
        }
    }
}

class Program
{
    static void Main(string[] args)
    {
        var sr = new StreamReader("People.txt");
        var xmlTree = new XStreamingElement("Root",
            from line in sr.Lines()
            let items = line.Split(',')
            where !line.StartsWith("#")
            select new XElement("Person",
                       new XAttribute("ID", items[0]),
                       new XElement("First", items[1]),
                       new XElement("Last", items[2]),
                       new XElement("Occupation", items[3])
                   )
        );
        Console.WriteLine(xmlTree);
        sr.Close();
    }
}
```

 Dieses Beispiel erzeugt die folgende Ausgabe:

```xml
<Root>
  <Person ID="1">
    <First>Tai</First>
    <Last>Yee</Last>
    <Occupation>Writer</Occupation>
  </Person>
  <Person ID="2">
    <First>Nikolay</First>
    <Last>Grachev</Last>
    <Occupation>Programmer</Occupation>
  </Person>
  <Person ID="3">
    <First>David</First>
    <Last>Wright</Last>
    <Occupation>Inventor</Occupation>
  </Person>
</Root>
```

## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XStreamingElement>
