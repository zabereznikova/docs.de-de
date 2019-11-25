---
title: Zugreifen auf die Attribute im DOM
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: ce2df341-a1a4-4e97-8e1b-cd45b8e3e71e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9b456dc407f634e7f40f69bbac9b6d932f1f4420
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350711"
---
# <a name="accessing-attributes-in-the-dom"></a>Zugreifen auf die Attribute im DOM

Attribute sind Eigenschaften des Elements und keine untergeordneten Elemente des entsprechenden Elements. Dies stellt aufgrund der Methoden zum Navigieren zwischen nebengeordneten, übergeordneten und untergeordneten Knoten des XML-Dokumentobjektmodells (DOM) eine wichtige Unterscheidung dar. Die **PreviousSibling**- und die **NextSibling**-Methode werden beispielsweise nicht zum Wechseln von einem Element zu einem Attribut oder zwischen Attributen verwendet. Stattdessen ist ein Attribut eine Eigenschaft eines Elements und gehört zu einem Element. Das Attribut verfügt über eine **OwnerElement**-Eigenschaft und nicht über eine **parentNode**-Eigenschaft. Außerdem besitzt es verschiedene Navigationsmethoden.

Wenn es sich bei dem aktuellen Knoten um ein Element handelt, verwenden Sie die **HasAttribute**-Methode, um zu prüfen, ob Attribute mit dem Element verbunden sind. Wenn bekannt ist, dass ein Element Attribute besitzt, bestehen mehrere Möglichkeiten, um auf die Attribute zuzugreifen. Um ein einzelnes Attribut von einem Element abzufragen, können Sie die **GetAttribute**-Methode und die **GetAttributeNode**-Methode des **XmlElement** verwenden oder alle Attribute in einer Auflistung abrufen. Es ist hilfreich, eine Auflistung abzurufen, wenn Sie die Auflistung durchlaufen müssen. Wenn Sie alle Attribute des Elements benötigen, verwenden Sie die **Attributes**-Eigenschaft des Elements, um alle Attribute in einer Auflistung abzufragen.

## <a name="retrieving-all-attributes-into-a-collection"></a>Abfragen aller Attribute in einer Auflistung

Falls Sie alle Attribute eines Elementknotens in einer Auflistung benötigen, rufen Sie die **XmlElement.Attributes**-Eigenschaft auf. Dadurch wird die **XmlAttributeCollection** abgerufen, die alle Attribute eines Elements enthält. Die **XmlAttributeCollection**-Klasse erbt von der **XmlNamedNode**-Zuordnung. Deshalb zählen zu den in der Auflistung verfügbaren Methoden und Eigenschaften außer spezifischen Methoden und Eigenschaften der **XmlAttributeCollection**-Klasse (z.B. die **ItemOf**-Eigenschaft oder die **Append**-Methode) auch solche Methoden und Eigenschaften, die in einer benannten Knotenzuordnung verfügbar sind. Jeder Eintrag in der Attributauflistung stellt einen **XmlAttribute**-Knoten dar. Um die Anzahl von Attributen in einem Element zu bestimmen, rufen Sie die **XmlAttributeCollection** ab, und verwenden Sie die **Count**-Eigenschaft, um anzuzeigen, wie viele **XmlAttribute**-Knoten die Auflistung enthält.

Im folgenden Codebeispiel wird dargestellt, wie eine Attributauflistung mit der **Count**-Methode für den Schleifenindex durchlaufen wird. Im folgenden Code wird dargestellt, wie ein einzelnes Attribut aus einer Auflistung abgefragt und dessen Wert angezeigt wird.

```vb
Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()

        Dim doc As XmlDocument = New XmlDocument()
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _
               "<title>The Handmaid's Tale</title>" & _
               "<price>14.95</price>" & _
               "</book>")

        ' Move to an element.
        Dim myElement As XmlElement = doc.DocumentElement

        ' Create an attribute collection from the element.
        Dim attrColl As XmlAttributeCollection = myElement.Attributes

        ' Show the collection by iterating over it.
        Console.WriteLine("Display all the attributes in the collection...")
        Dim i As Integer
        For i = 0 To attrColl.Count - 1
            Console.Write("{0} = ", attrColl.ItemOf(i).Name)
            Console.Write("{0}", attrColl.ItemOf(i).Value)
            Console.WriteLine()
        Next

        ' Retrieve a single attribute from the collection; specifically, the
        ' attribute with the name "misc".
        Dim attr As XmlAttribute = attrColl("misc")

        ' Retrieve the value from that attribute.
        Dim miscValue As String = attr.InnerXml

        Console.WriteLine("Display the attribute information.")
        Console.WriteLine(miscValue)

    End Sub
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;

public class Sample
{

    public static void Main()
    {
        XmlDocument doc = new XmlDocument();
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" +
                      "<title>The Handmaid's Tale</title>" +
                      "<price>14.95</price>" +
                      "</book>");

        // Move to an element.
        XmlElement myElement = doc.DocumentElement;

        // Create an attribute collection from the element.
        XmlAttributeCollection attrColl = myElement.Attributes;

        // Show the collection by iterating over it.
        Console.WriteLine("Display all the attributes in the collection...");
        for (int i = 0; i < attrColl.Count; i++)
        {
            Console.Write("{0} = ", attrColl[i].Name);
            Console.Write("{0}", attrColl[i].Value);
            Console.WriteLine();
        }

        // Retrieve a single attribute from the collection; specifically, the
        // attribute with the name "misc".
        XmlAttribute attr = attrColl["misc"];

        // Retrieve the value from that attribute.
        String miscValue = attr.InnerXml;

        Console.WriteLine("Display the attribute information.");
        Console.WriteLine(miscValue);

    }
}
```

In diesem Beispiel wird die folgende Ausgabe dargestellt:

**Ausgabe**

Alle Attribute in der Auflistung anzeigen.

```console
genre = novel
ISBN = 1-861001-57-5
misc = sale item
Display the attribute information.
sale item
```

Die Informationen in einer Attributauflistung können nach Namen oder Indexnummer abgefragt werden. Im oben aufgeführten Beispiel wird dargestellt, wie Daten nach Namen abgefragt werden. Im nächsten Beispiel wird dargestellt, wie Daten nach Indexnummer abgefragt werden.

Da es sich bei der **XmlAttributeCollection**-Klasse um eine Auflistung handelt, die nach Namen oder Index durchlaufen werden kann, wird in diesem Beispiel die Auswahl des ersten Attributs aus der Auflistung mit einem nullbasierten (0) Index dargestellt, wobei die Datei **baseuri.xml** als Eingabe verwendet wird.

### <a name="input"></a>Eingabe

```xml
<!-- XML fragment -->
<book genre="novel">
  <title>Pride And Prejudice</title>
</book>
```

```vb
Option Explicit On
Option Strict On

Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()
        ' Create the XmlDocument.
        Dim doc As New XmlDocument()
        doc.Load("http://localhost/baseuri.xml")

        ' Display information on the attribute node. The value
        ' returned for BaseURI is 'http://localhost/baseuri.xml'.
        Dim attr As XmlAttribute = doc.DocumentElement.Attributes(0)
        Console.WriteLine("Name of the attribute:  {0}", attr.Name)
        Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI)
        Console.WriteLine("The value of the attribute:  {0}", attr.InnerText)
    End Sub 'Main
End Class 'Sample
```

```csharp
using System;
using System.IO;
using System.Xml;

public class Sample
{
  public static void Main()
  {
    // Create the XmlDocument.
    XmlDocument doc = new XmlDocument();

    doc.Load("http://localhost/baseuri.xml");

    // Display information on the attribute node. The value
    // returned for BaseURI is 'http://localhost/baseuri.xml'.
    XmlAttribute attr = doc.DocumentElement.Attributes[0];
    Console.WriteLine("Name of the attribute:  {0}", attr.Name);
    Console.WriteLine("Base URI of the attribute:  {0}", attr.BaseURI);
    Console.WriteLine("The value of the attribute:  {0}", attr.InnerText);
  }
}
```

## <a name="retrieving-an-individual-attribute-node"></a>Abrufen eines einzelnen Attributknotens

Zum Abrufen eines einzelnen Attributknotens aus einem Element wird die <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType>-Methode verwendet. Sie gibt ein Objekt des Typs **XmlAttribute** zurück. Wenn das **XmlAttribute**-Objekt vorhanden ist, sind alle Methoden und Eigenschaften, die in der <xref:System.Xml.XmlAttribute?displayProperty=nameWithType>-Klasse verfügbar sind, in diesem Objekt verfügbar, wie das Suchen nach dem **OwnerElement**.

```vb
Imports System.IO
Imports System.Xml

Public Class Sample

    Public Shared Sub Main()

        Dim doc As XmlDocument = New XmlDocument()
        doc.LoadXml("<book genre='novel' ISBN='1-861001-57-5' misc='sale item'>" & _
               "<title>The Handmaid's Tale</title>" & _
               "<price>14.95</price>" & _
               "</book>")

        ' Move to an element.
        Dim root As XmlElement
        root = doc.DocumentElement

        ' Get an attribute.
        Dim attr As XmlAttribute
        attr = root.GetAttributeNode("ISBN")

        ' Display the value of the attribute.
        Dim attrValue As String
        attrValue = attr.InnerXml
        Console.WriteLine(attrValue)

    End Sub
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;

 public class Sample
 {
      public static void Main()
      {
    XmlDocument doc = new XmlDocument();
     doc.LoadXml("<book genre='novel' ISBN='1-861003-78' misc='sale item'>" +
                   "<title>The Handmaid's Tale</title>" +
                   "<price>14.95</price>" +
                   "</book>");

    // Move to an element.
     XmlElement root = doc.DocumentElement;

    // Get an attribute.
     XmlAttribute attr = root.GetAttributeNode("ISBN");

    // Display the value of the attribute.
     String attrValue = attr.InnerXml;
     Console.WriteLine(attrValue);

    }
}
```

Sie können auch wie im vorherigen Beispiel vorgehen, in dem ein einzelner Attributknoten aus einer Attributauflistung abgerufen wird. Im folgenden Beispiel wird dargestellt, wie eine Codezeile geschrieben werden kann, damit ein einzelnes Attribut nach der Indexnummer aus dem Stamm der XML-Dokumentstruktur abgerufen wird, auch als **DocumentElement**-Eigenschaft bezeichnet.

```csharp
XmlAttribute attr = doc.DocumentElement.Attributes[0];
```

## <a name="see-also"></a>Siehe auch

- [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
