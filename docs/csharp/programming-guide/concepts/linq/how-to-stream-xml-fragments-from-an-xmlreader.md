---
title: 'Vorgehensweise: Streamen von XML-Fragmenten aus einem XmlReader | Microsoft-Dokumentation'
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
ms.assetid: 4a8f0e45-768a-42e2-bc5f-68bdf0e0a726
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 400dfda51d978f35c3995f90840643aaff1b9c13
ms.openlocfilehash: 06e2cf4b350fecf8e8310519c573ac140f05267a
ms.contentlocale: de-de
ms.lasthandoff: 03/24/2017

---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-c"></a>Vorgehensweise: Streamen von XML-Fragmenten aus einem XmlReader (C#)
Wenn Sie große XML-Dateien verarbeiten müssen, kann u. U. nicht die gesamte XML-Struktur in den Arbeitsspeicher geladen werden. Dieses Thema zeigt, wie Fragmente direkt mit einem <xref:System.Xml.XmlReader> gestreamt werden.  
  
 Eine der effektivsten Arten, einen <xref:System.Xml.XmlReader> zu verwenden, um <xref:System.Xml.Linq.XElement>-Objekte zu lesen, ist das Schreiben einer eigenen benutzerdefinierten Achsenmethode. Eine Achsenmethode gibt typischerweise eine Auflistung wie <xref:System.Collections.Generic.IEnumerable%601> von <xref:System.Xml.Linq.XElement> zurück, wie in dem Beispiel in diesem Thema gezeigt. Nachdem Sie in der benutzerdefinierten Achsenmethode durch Aufrufen der <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode das XML-Fragment erstellt haben, geben Sie die Auflistung mit `yield return` zurück. Auf diese Weise versehen Sie Ihre benutzerdefinierte Achsenmethode mit der Semantik für eine verzögerte Ausführung.  
  
 Wenn Sie einen XML-Baum aus einem <xref:System.Xml.XmlReader>-Objekt erstellen, muss sich der <xref:System.Xml.XmlReader> auf einem Element befinden. Die <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode gibt erst dann einen Wert zurück, wenn sie das Endtag des Elements gelesen hat.  
  
 Wenn Sie einen Teilbaum erstellen möchten, können Sie einen <xref:System.Xml.XmlReader> instanziieren, den Reader auf dem Knoten positionieren, den Sie in einen <xref:System.Xml.Linq.XElement>-Baum konvertieren möchten, und anschließend das <xref:System.Xml.Linq.XElement>-Objekt erstellen.  
  
 Unter [How to: Stream XML Fragments with Access to Header Information (C#) (Vorgehensweise: Streamen von XML-Fragmenten mit Zugriff auf Headerinformationen (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md) finden Sie weitere Informationen und ein Beispiel, wie Sie ein komplexeren Dokument streamen können.  
  
 Unter [How to: Perform Streaming Transform of Large XML Documents (C#) (vorgehensweise: Durchführen einer Streamingtransformation großer XML-Dokumente (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md) finden Sie ein Beispiel für das Verwenden von LINQ to XML, um ein sehr großes XML-Dokument umzuwandeln, während Sie gleichzeitig eine geringe Speicherbeanspruchung beibehalten.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel erstellt eine benutzerdefinierte Achsenmethode. Zum Abfragen kann eine [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]-Abfrage verwendet werden. Die benutzerdefinierte Achsenmethode `StreamRootChildDoc` eignet sich vor allem zum Lesen eines Dokuments, das ein sich wiederholendes `Child`-Element enthält.  
  
```csharp  
static IEnumerable<XElement> StreamRootChildDoc(StringReader stringReader)  
{  
    using (XmlReader reader = XmlReader.Create(stringReader))  
    {  
        reader.MoveToContent();  
        // Parse the file and display each of the nodes.  
        while (reader.Read())  
        {  
            switch (reader.NodeType)  
            {  
                case XmlNodeType.Element:  
                    if (reader.Name == "Child") {  
                        XElement el = XElement.ReadFrom(reader) as XElement;  
                        if (el != null)  
                            yield return el;  
                    }  
                    break;  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    string markup = @"<Root>  
      <Child Key=""01"">  
        <GrandChild>aaa</GrandChild>  
      </Child>  
      <Child Key=""02"">  
        <GrandChild>bbb</GrandChild>  
      </Child>  
      <Child Key=""03"">  
        <GrandChild>ccc</GrandChild>  
      </Child>  
    </Root>";  
  
    IEnumerable<string> grandChildData =  
        from el in StreamRootChildDoc(new StringReader(markup))  
        where (int)el.Attribute("Key") > 1  
        select (string)el.Element("GrandChild");  
  
    foreach (string str in grandChildData) {  
        Console.WriteLine(str);  
    }  
}  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
bbb  
ccc  
```  
  
 In diesem Beispiel ist das Quelldokument sehr klein. Dieses Beispiel würde aber auch dann wenig Speicher beanspruchen, wenn das Quelldokument Millionen `Child`-Elemente enthielte.  
  
## <a name="see-also"></a>Siehe auch  
 [Analysieren von XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
