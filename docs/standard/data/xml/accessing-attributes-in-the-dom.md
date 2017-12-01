---
title: Zugreifen auf die Attribute im DOM
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ce2df341-a1a4-4e97-8e1b-cd45b8e3e71e
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a433ec5f83a50aa4fe4b2017a0dac3d2a5e5710c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="accessing-attributes-in-the-dom"></a>Zugreifen auf die Attribute im DOM
Attribute sind Eigenschaften des Elements und keine untergeordneten Elemente des entsprechenden Elements. Dies stellt aufgrund der Methoden zum Navigieren zwischen nebengeordneten, übergeordneten und untergeordneten Knoten des XML-Dokumentobjektmodells (DOM) eine wichtige Unterscheidung dar. Z. B. die **PreviousSibling** und **NextSibling** Methoden werden nicht zum Navigieren von einem Element zu einem Attribut oder zwischen Attributen. Stattdessen ein Attribut ist eine Eigenschaft eines Elements und ist im Besitz eines Elements, verfügt über eine **OwnerElement** Eigenschaft und keine **ParentNode** -Eigenschaft, und verfügt über unterschiedliche Methoden der Navigation.  
  
 Wenn der aktuelle Knoten ein Element ist, verwenden Sie die **HasAttribute** Methode, um festzustellen, ob alle Attribute, die dem Element zugeordnet wurden. Wenn bekannt ist, dass ein Element Attribute besitzt, bestehen mehrere Möglichkeiten, um auf die Attribute zuzugreifen. Um ein einzelnes Attribut aus dem Element abzurufen, können Sie die **GetAttribute** und **GetAttributeNode** Methoden die **XmlElement** oder erhalten Sie alle Attribute in einer Auflistung. Es ist hilfreich, eine Auflistung abzurufen, wenn Sie die Auflistung durchlaufen müssen. Wenn Sie alle Attribute des Elements möchten, verwenden die **Attribute** Eigenschaft des Elements, das alle Attribute in einer Auflistung abzufragen.  
  
## <a name="retrieving-all-attributes-into-a-collection"></a>Abfragen aller Attribute in einer Auflistung  
 Rufen Sie gegebenenfalls alle versetzen die Attribute eines Elementknotens in eine Auflistung der **XmlElement.Attributes** Eigenschaft. Dadurch wird die **XmlAttributeCollection** , das alle Attribute eines Elements enthält. Die **XmlAttributeCollection** Klasse erbt von der **XmlNamedNode** Zuordnung. Daher die Methoden und Eigenschaften, die in der Auflistung verfügbaren enthalten auf einer Karte benannten Knoten verfügbar sind. darüber hinaus an Methoden und Eigenschaften, die spezifisch für die **XmlAttributeCollection** Klasse, z. B. die **ItemOf**  Eigenschaft oder die **Append** Methode. Jedes Element in der attributauflistung stellt einen **XmlAttribute** Knoten. Um die Anzahl der Attribute für ein Element zu suchen, erhalten die **XmlAttributeCollection**, und verwenden die **Anzahl** Eigenschaft, um wie viele **XmlAttribute** Knoten werden in der Auflistung.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine attributauflistung mit der **Anzahl** Methode für den Schleifenindex durchlaufen wird. Im folgenden Code wird dargestellt, wie ein einzelnes Attribut aus einer Auflistung abgefragt und dessen Wert angezeigt wird.  
  
```vb  
Imports System  
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
  
```  
genre = novel  
ISBN = 1-861001-57-5  
misc = sale item  
Display the attribute information.  
sale item  
```  
  
 Die Informationen in einer Attributauflistung können nach Namen oder Indexnummer abgefragt werden. Im oben aufgeführten Beispiel wird dargestellt, wie Daten nach Namen abgefragt werden. Im nächsten Beispiel wird dargestellt, wie Daten nach Indexnummer abgefragt werden.  
  
 Da die **XmlAttributeCollection** ist eine Auflistung durchlaufen werden kann, und wählen Sie Namen oder Index, in diesem Beispiel wird gezeigt, Auswählen des ersten Attributs aus der Auflistung mithilfe eines nullbasierten Index, und verwenden die folgende Datei **baseuri.xml**als Eingabe.  
  
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
  
Imports System  
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
        Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText)  
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
    Console.WriteLine("The value of the attribtue:  {0}", attr.InnerText);  
  }  
}  
```  
  
## <a name="retrieving-an-individual-attribute-node"></a>Abrufen eines einzelnen Attributknotens  
 Zum Abrufen eines einzelnen Attributknotens aus einem Element wird die <xref:System.Xml.XmlElement.GetAttributeNode%2A?displayProperty=nameWithType>-Methode verwendet. Es gibt ein Objekt des Typs **XmlAttribute**. Nachdem Sie haben eine **XmlAttribute**, alle Methoden und Eigenschaften verfügbar, in der <xref:System.Xml.XmlAttribute?displayProperty=nameWithType> Klasse stehen für dieses Objekt, wie das Suchen nach der **OwnerElement**.  
  
```vb  
Imports System  
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
  
 Sie können auch wie im vorherigen Beispiel vorgehen, in dem ein einzelner Attributknoten aus einer Attributauflistung abgerufen wird. Im folgenden Codebeispiel wird veranschaulicht wie eine Codezeile kann zum Abrufen eines einzelnen Attributs anhand der Indexnummer aus dem Stamm der XML-Dokument geschrieben werden, auch bekannt als Struktur die **DocumentElement** Eigenschaft.  
  
```  
XmlAttribute attr = doc.DocumentElement.Attributes[0];  
```  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentobjektmodell (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
