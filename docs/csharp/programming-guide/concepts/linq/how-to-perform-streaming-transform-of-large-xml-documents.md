---
title: 'Vorgehensweise: Durchführen einer Streamingtransformation großer XML-Dokumente (C#)'
description: Hier erfahren Sie, wie Sie eine Streamingtransformation von Text in XML in C# durchführen, um eine übermäßige Speicherauslastung für einige Dateien zu vermeiden.
ms.date: 07/20/2015
ms.assetid: 5f16d1f8-5370-4b55-b0c8-e497df163037
ms.openlocfilehash: e1ab2866079b2244dc764271d7ba63173349e2f3
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87104862"
---
# <a name="how-to-perform-streaming-transform-of-large-xml-documents-c"></a>Vorgehensweise: Durchführen einer Streamingtransformation großer XML-Dokumente (C#)
Es kann vorkommen, dass Sie große XML-Dateien transformieren und Ihre Anwendung so schreiben müssen, dass der Arbeitsspeicherbedarf der Anwendung vorhersehbar ist. Wenn Sie versuchen, eine XML-Struktur mit einer sehr großen XML-Datei zu füllen, ändert sich Ihre Speicherbeanspruchung proportional zur Größe der Datei, also exzessiv. Deshalb sollten Sie stattdessen ein Streamingverfahren verwenden.  
  
 Streamingverfahren eignen sich vor allem für Situationen, bei denen Sie das Quelldokument nur einmal verarbeiten müssen und bei denen die Elemente in der Reihenfolge verarbeitet werden können, in der sie im Dokument auftreten. Einige Standardabfrageoperatoren, wie <xref:System.Linq.Enumerable.OrderBy%2A>, durchlaufen ihre Quelle, erfassen alle Daten, sortieren sie und geben dann das erste Element in der Sequenz zurück. Beachten Sie, dass Sie bei der Verwendung eines Abfrageoperators, der seine Quelle vor der Rückgabe des ersten Elements materialisiert, keine minimale Speicherbeanspruchung für Ihre Anwendung aufrechterhalten können.  
  
Aber selbst dann, wenn Sie das in [Vorgehensweise: Streamen von XML-Fragmenten mit Zugriff auf Headerinformationen (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) beschriebene Verfahren verwenden, wird die Speicherbeanspruchung zu groß, wenn Sie versuchen, eine XML-Struktur unter Einbeziehung des transformierten Dokuments zusammenzustellen.
  
 Es gibt im Wesentlichen zwei Lösungsansätze: Zum einen können Sie versuchen, sich die verzögerte Verarbeitung von <xref:System.Xml.Linq.XStreamingElement> zunutze zu machen, und zum anderen können Sie einen <xref:System.Xml.XmlWriter> erstellen und dann mithilfe von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Elemente in den <xref:System.Xml.XmlWriter> zu schreiben. In diesem Thema werden beide Ansätze besprochen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel baut auf dem Beispiel in [Vorgehensweise: Streamen von XML-Fragmenten mit Zugriff auf Headerinformationen (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) auf.
  
 In diesem Beispiel wird die verzögerte Ausführung von <xref:System.Xml.Linq.XStreamingElement> verwendet, um die Ausgabe zu streamen. Damit kann auch ein sehr großes Dokument transformiert werden, ohne dass die Speicherbeanspruchung zu groß wird.  
  
 Beachten Sie, dass die benutzerdefinierte Achse (`StreamCustomerItem`) so geschrieben ist, dass sie über ein Dokument mit `Customer`-Elementen, `Name`-Elementen und `Item`-Elementen verfügt. Diese Elemente werden wie im folgenden Source.xml-Dokument angeordnet. Eine robustere Implementierung würde jedoch darauf vorbereitet sein, ein ungültiges Dokument analysieren zu können.  
  
 Das Quelldokument (<legacyBold>Source.xml</legacyBold>) sieht wie folgt aus:  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>
<Root>  
  <Customer>  
    <Name>A. Datum Corporation</Name>  
    <Item>  
      <Key>0001</Key>  
    </Item>  
    <Item>  
      <Key>0002</Key>  
    </Item>  
    <Item>  
      <Key>0003</Key>  
    </Item>  
    <Item>  
      <Key>0004</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Fabrikam, Inc.</Name>  
    <Item>  
      <Key>0005</Key>  
    </Item>  
    <Item>  
      <Key>0006</Key>  
    </Item>  
    <Item>  
      <Key>0007</Key>  
    </Item>  
    <Item>  
      <Key>0008</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Southridge Video</Name>  
    <Item>  
      <Key>0009</Key>  
    </Item>  
    <Item>  
      <Key>0010</Key>  
    </Item>  
  </Customer>  
</Root>  
```  
  
```csharp  
static IEnumerable<XElement> StreamCustomerItem(string uri)  
{  
    using (XmlReader reader = XmlReader.Create(uri))  
    {  
        XElement name = null;  
        XElement item = null;  
  
        reader.MoveToContent();  
  
        // Parse the file, save header information when encountered, and yield the  
        // Item XElement objects as they are created.  
  
        // loop through Customer elements  
        while (reader.Read())  
        {  
            if (reader.NodeType == XmlNodeType.Element  
                && reader.Name == "Customer")  
            {  
                // move to Name element  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.Element &&  
                        reader.Name == "Name")  
                    {  
                        name = XElement.ReadFrom(reader) as XElement;  
                        break;  
                    }  
                }  
  
                // loop through Item elements  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.EndElement)  
                        break;  
                    if (reader.NodeType == XmlNodeType.Element  
                        && reader.Name == "Item")  
                    {  
                        item = XElement.ReadFrom(reader) as XElement;  
                        if (item != null)  
                        {  
                            XElement tempRoot = new XElement("Root",  
                                new XElement(name)  
                            );  
                            tempRoot.Add(item);  
                            yield return item;  
                        }  
                    }  
                }  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    XStreamingElement root = new XStreamingElement("Root",  
        from el in StreamCustomerItem("Source.xml")  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        )  
    );  
    root.Save("Test.xml");  
    Console.WriteLine(File.ReadAllText("Test.xml"));  
}  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  
## <a name="example"></a>Beispiel  
Das folgende Beispiel baut ebenfalls auf dem Beispiel in [Vorgehensweise: Streamen von XML-Fragmenten mit Zugriff auf Headerinformationen (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) auf.
  
 In diesem Beispiel wird die Fähigkeit von [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] genutzt, Elemente in einen <xref:System.Xml.XmlWriter> zu schreiben. Damit kann auch ein sehr großes Dokument transformiert werden, ohne dass die Speicherbeanspruchung zu groß wird.  
  
 Beachten Sie, dass die benutzerdefinierte Achse (`StreamCustomerItem`) so geschrieben ist, dass sie über ein Dokument mit `Customer`-Elementen, `Name`-Elementen und `Item`-Elementen verfügt. Diese Elemente werden wie im folgenden Source.xml-Dokument angeordnet. Eine robustere Implementierung würde jedoch entweder das Quelldokument mit einer XSD prüfen oder darauf vorbereitet sein, ein ungültiges Dokument analysieren zu können.  
  
 In diesem Beispiel wird das gleiche Quelldokument (<legacyBold>Source.xml</legacyBold>) wie im Beispiel oben verwendet. Es erzeugt auch genau die gleiche Ausgabe.  
  
 Für das Streamen der XML-Ausgabe wird empfohlen, nicht in einen <xref:System.Xml.Linq.XStreamingElement> zu schreiben, sondern <xref:System.Xml.XmlWriter> zu verwenden.  
  
```csharp  
static IEnumerable<XElement> StreamCustomerItem(string uri)  
{  
    using (XmlReader reader = XmlReader.Create(uri))  
    {  
        XElement name = null;  
        XElement item = null;  
  
        reader.MoveToContent();  
  
        // Parse the file, save header information when encountered, and yield the  
        // Item XElement objects as they are created.  
  
        // loop through Customer elements  
        while (reader.Read())  
        {  
            if (reader.NodeType == XmlNodeType.Element  
                && reader.Name == "Customer")  
            {  
                // move to Name element  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.Element &&  
                        reader.Name == "Name")  
                    {  
                        name = XElement.ReadFrom(reader) as XElement;  
                        break;  
                    }  
                }  
  
                // loop through Item elements  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.EndElement)  
                        break;  
                    if (reader.NodeType == XmlNodeType.Element  
                        && reader.Name == "Item")  
                    {  
                        item = XElement.ReadFrom(reader) as XElement;  
                        if (item != null) {  
                            XElement tempRoot = new XElement("Root",  
                                new XElement(name)  
                            );  
                            tempRoot.Add(item);  
                            yield return item;  
                        }  
                    }  
                }  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    IEnumerable<XElement> srcTree =  
        from el in StreamCustomerItem("Source.xml")  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        );  
    XmlWriterSettings xws = new XmlWriterSettings();  
    xws.OmitXmlDeclaration = true;  
    xws.Indent = true;  
    using (XmlWriter xw = XmlWriter.Create("Output.xml", xws)) {  
        xw.WriteStartElement("Root");  
        foreach (XElement el in srcTree)  
            el.WriteTo(xw);  
        xw.WriteEndElement();  
    }  
  
    string str = File.ReadAllText("Output.xml");  
    Console.WriteLine(str);  
}  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  