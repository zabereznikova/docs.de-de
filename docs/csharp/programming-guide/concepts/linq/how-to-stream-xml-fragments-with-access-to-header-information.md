---
title: 'Vorgehensweise: Streamen von XML-Fragmenten mit Zugriff auf Headerinformationen (C#)'
ms.date: 07/20/2015
ms.assetid: 7f242770-b0c7-418d-894b-643215e1f8aa
ms.openlocfilehash: 5bc10bcadae0e33ee63f953608ca841d44dd6527
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75712389"
---
# <a name="how-to-stream-xml-fragments-with-access-to-header-information-c"></a>Vorgehensweise: Streamen von XML-Fragmenten mit Zugriff auf Headerinformationen (C#)
Es kann vorkommen, dass Sie willkürlich große XML-Dateien lesen und Ihre Anwendung so schreiben müssen, dass der Arbeitsspeicherbedarf der Anwendung vorhersehbar ist. Wenn Sie versuchen, eine XML-Struktur mit einer großen XML-Datei zu füllen, ändert sich Ihre Speicherbeanspruchung proportional zur Größe der Datei, also exzessiv. Deshalb sollten Sie stattdessen ein Streamingverfahren verwenden.  
  
Zu diesem Zweck können Sie die Anwendung mit <xref:System.Xml.XmlReader> schreiben. Es empfiehlt sich aber häufig, zum Abfragen der XML-Struktur LINQ zu verwenden. Bei Verwendung von {1} können Sie eine eigene benutzerdefinierte Achsenmethode schreiben. Weitere Informationen finden Sie unter [Vorgehensweise: Schreiben einer LINQ to XML-Axis-Methode (C#)](./how-to-write-a-linq-to-xml-axis-method.md).
  
 Zum Schreiben einer eigenen Achsenmethode müssen Sie zunächst eine kleine Methode schreiben, die mit dem <xref:System.Xml.XmlReader> Knoten so lange liest, bis sie zu einem der Knoten gelangt, die Sie interessieren. Die Methode ruft dann die <xref:System.Xml.Linq.XNode.ReadFrom%2A>-Methode auf, die aus dem <xref:System.Xml.XmlReader> liest und ein XML-Fragment instanziiert. Daraufhin wird jedes Fragment mit `yield return` an die Methode zurückgegeben, die Ihre benutzerdefinierte Achsenmethode aufzählt. Sie können dann LINQ-Abfragen für die benutzerdefinierte Achsenmethode schreiben.  
  
 Streamingverfahren eignen sich vor allem für Situationen, bei denen Sie das Quelldokument nur einmal verarbeiten müssen und bei denen die Elemente in der Reihenfolge verarbeitet werden können, in der sie im Dokument auftreten. Einige Standardabfrageoperatoren, wie <xref:System.Linq.Enumerable.OrderBy%2A>, durchlaufen ihre Quelle, erfassen alle Daten, sortieren sie und geben dann das erste Element in der Sequenz zurück. Bei Verwendung eines Abfrageoperators, der seine Quelle vor der Rückgabe des ersten Elements materialisiert, erhalten Sie keinen kleinen Arbeitsspeicher-Fußabdruck.  
  
## <a name="example"></a>Beispiel  

Manchmal wird das Problem noch ein wenig interessanter. Im folgenden XML-Dokument muss der Benutzer Ihrer benutzerdefinierten Achsenmethode auch die Namen der Kunden kennen, zu denen die einzelnen Elemente gehören.  
  
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
  
 Dieses Beispiel sucht auch nach diesen Headerinformationen, speichert sie und konstruiert dann eine kleine XML-Struktur, die sowohl die Headerinformationen als auch die Detailinformationen enthält, die von Ihnen aufgezählt werden. Die Achsenmethode gibt daraufhin diese neue, kleine XML-Struktur zurück. Die Abfrage verfügt damit sowohl über Zugriff auf die Headerinformationen als auch über Zugriff auf die Detailinformationen.  
  
 Dieser Ansatz führt zu einer geringen Speicherbeanspruchung. Da jedes XML-Detailfragment zurückgegeben wird, bleiben keine Verweise auf vorherige Fragmente erhalten. Es steht damit für die Garbage Collection (automatische Speicherbereinigung) zur Verfügung. Bei diesem Verfahren werden viele kurzlebige Objekte auf dem Heap erstellt.  
  
 Im folgenden Beispiel wird die Vorgehensweise bei der Implementierung und Verwendung einer benutzerdefinierten Achsenmethode gezeigt, die XML-Fragmente aus der durch den URI angegebenen Datei streamt. Diese benutzerdefinierte Achse ist so geschrieben, dass sie ein Dokument mit `Customer`-Elementen, `Name`-Elementen und `Item`-Elementen erwartet. Diese Elemente werden wie im Dokument `Source.xml` oben angeordnet. Dabei handelt es sich um eine eher einfache Implementierung. Eine robustere Implementierung würde darauf vorbereitet sein, ein ungültiges Dokument analysieren zu können.  
  
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
    XElement xmlTree = new XElement("Root",  
        from el in StreamCustomerItem("Source.xml")  
        where (int)el.Element("Key") >= 3 && (int)el.Element("Key") <= 7  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        )  
    );  
    Console.WriteLine(xmlTree);  
}  
```  
  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
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
</Root>  
```  
