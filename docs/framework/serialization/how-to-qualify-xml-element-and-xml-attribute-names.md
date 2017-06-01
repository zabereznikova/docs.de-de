---
title: "Vorgehensweise: Qualifizieren von XML-Element- und XML-Attributnamen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Qualifizieren von XML-Elementen"
  - "Qualifizieren von XML-Namen"
  - "XML-Namespaces, Qualifizieren von Elementen und Namen in"
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Vorgehensweise: Qualifizieren von XML-Element- und XML-Attributnamen
[Codebeispiel](#cpconworkingwithxmlnamespacesanchor1)  
  
 In Instanzen der [XmlSerializerNamespaces](frlrfSystemXmlSerializationXmlSerializerNamespacesClassTopic)\-Klasse enthaltene XML\-Namespaces müssen der Spezifikation "Namespaces in XML" des World Wide Web Consortium \(www.w3.org\) entsprechen.  
  
 XML\-Namespaces stellen eine Methode zur Qualifizierung der Namen von XML\-Elementen und XML\-Attributen in XML\-Dokumenten bereit.Ein qualifizierter Name besteht aus einem Präfix und einem lokalen Namen, die durch einen Doppelpunkt voneinander getrennt sind.Das Präfix wird nur als Platzhalter verwendet und ist einem URI zugeordnet, der den Namespace angibt.Die Kombination aus dem global verwalteten URI\-Namespace und dem lokalen Namen bildet einen weltweit garantiert eindeutigen Namen.  
  
 Sie können die in einem XML\-Dokument verwendeten Präfixe festlegen, indem Sie eine Instanz von **XmlSerializerNamespaces** erstellen und die Namespacepaare dem Objekt hinzufügen.  
  
### So erstellen Sie qualifizierte Namen in einem XML\-Dokument  
  
1.  Erstellen Sie eine Instanz der **XmlSerializerNamespaces**\-Klasse.  
  
2.  Fügen Sie alle Präfixe und Namespacepaare zu **XmlSerializerNamespaces** hinzu.  
  
3.  Wenden Sie das geeignete **System.Xml.Serialization**\-Attribut auf jeden Member oder jede Klasse an, die von [XmlSerializer](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx) in ein XML\-Dokument serialisiert werden soll.  
  
     Folgende Attribute sind verfügbar: [XmlAnyElementAttribute](frlrfSystemXmlSerializationXmlAnyElementAttributeClassTopic), [XmlArrayAttribute](frlrfSystemXmlSerializationXmlArrayAttributeClassTopic), [XmlArrayItemAttribute](frlrfSystemXmlSerializationXmlArrayItemAttributeClassTopic), [XmlAttributeAttribute](frlrfSystemXmlSerializationXmlAttributeAttributeClassTopic), [XmlElementAttribute](frlrfSystemXmlSerializationXmlElementAttributeClassTopic), [XmlRootAttribute](frlrfSystemXmlSerializationXmlRootAttributeClassTopic) und [XmlTypeAttribute](frlrfSystemXmlSerializationXmlTypeAttributeClassTopic).  
  
4.  Legen Sie die **Namespace**\-Eigenschaft jedes Attributs auf einen der Namespacewerte aus dem **XmlSerializerNamespaces**\-Objekt fest.  
  
5.  Übergeben Sie **XmlSerializerNamespaces** an die **Serialize**\-Methode von **XmlSerializer**.  
  
## Beispiel  
 Im folgenden Beispiel wird ein **XmlSerializerNamespaces**\-Objekt erstellt, dem zwei Paare aus Präfix und Namespace hinzugefügt werden.Durch den Code wird ein **XmlSerializer**\-Objekt erstellt, das verwendet wird, um eine Instanz der `Books`\-Klasse zu serialisieren.Im Code wird die **Serialize**\-Methode mit **XmlSerializerNamespaces** aufgerufen. Der XML\-Stream kann daher Namespaces mit Präfixen enthalten.  
  
```vb  
Option Explicit   
public class Price  
{  
    [XmlAttribute(Namespace = "http://www.cpandl.com")]  
    public string currency;  
    [XmlElement(Namespace = "http://www.cohowinery.com")]  
    public decimal price;  
}  
  
Option Strict  
  
Imports System  
Imports System.IO  
Imports System.Xml  
Imports System.Xml.Serialization  
  
Public Class Run  
  
    Public Shared Sub Main()  
        Dim test As New Run()  
        test.SerializeObject("XmlNamespaces.xml")  
    End Sub 'Main  
  
    Public Sub SerializeObject(filename As String)  
        Dim mySerializer As New XmlSerializer(GetType(Books))  
        ' Writing a file requires a TextWriter.  
        Dim myWriter As New StreamWriter(filename)  
  
        ' Creates an XmlSerializerNamespaces and adds two  
        ' prefix-namespace pairs.   
        Dim myNamespaces As New XmlSerializerNamespaces()  
        myNamespaces.Add("books", "http://www.cpandl.com")  
        myNamespaces.Add("money", "http://www.cohowinery.com")  
  
        ' Creates a Book.  
        Dim myBook As New Book()  
        myBook.TITLE = "A Book Title"  
        Dim myPrice As New Price()  
        myPrice.price = CDec(9.95)  
        myPrice.currency = "US Dollar"  
        myBook.PRICE = myPrice  
        Dim myBooks As New Books()  
        myBooks.Book = myBook  
        mySerializer.Serialize(myWriter, myBooks, myNamespaces)  
        myWriter.Close()  
    End Sub  
End Class  
  
Public Class Books  
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
    Public Book As Book  
End Class 'Books  
  
<XmlType([Namespace] := "http://www.cpandl.com")> _  
Public Class Book  
  
    <XmlElement([Namespace] := "http://www.cpandl.com")> _  
    Public TITLE As String  
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
    Public PRICE As Price  
End Class  
  
Public Class Price  
    <XmlAttribute([Namespace] := "http://www.cpandl.com")> _  
    Public currency As String  
    Public <XmlElement([Namespace] := "http://www.cohowinery.com")> _  
        price As Decimal  
End Class  
  
```  
  
```csharp  
using System;  
using System.IO;  
using System.Xml;  
using System.Xml.Serialization;  
  
public class Run  
{  
    public static void Main()  
    {  
        Run test = new Run();  
        test.SerializeObject("XmlNamespaces.xml");  
    }  
    public void SerializeObject(string filename)  
    {  
        XmlSerializer mySerializer = new XmlSerializer(typeof(Books));  
        // Writing a file requires a TextWriter.  
        TextWriter myWriter = new StreamWriter(filename);  
  
        // Creates an XmlSerializerNamespaces and adds two  
        // prefix-namespace pairs.  
        XmlSerializerNamespaces myNamespaces =   
        new XmlSerializerNamespaces();  
        myNamespaces.Add("books", "http://www.cpandl.com");  
        myNamespaces.Add("money", "http://www.cohowinery.com");  
  
        // Creates a Book.  
        Book myBook = new Book();  
        myBook.TITLE = "A Book Title";  
        Price myPrice = new Price();  
        myPrice.price = (decimal) 9.95;  
        myPrice.currency = "US Dollar";  
        myBook.PRICE = myPrice;  
        Books myBooks = new Books();  
        myBooks.Book = myBook;  
        mySerializer.Serialize(myWriter,myBooks,myNamespaces);  
        myWriter.Close();  
    }  
}  
  
public class Books  
{  
    [XmlElement(Namespace = "http://www.cohowinery.com")]  
    public Book Book;  
}  
  
[XmlType(Namespace ="http://www.cpandl.com")]  
public class Book  
{  
    [XmlElement(Namespace = "http://www.cpandl.com")]  
    public string TITLE;  
    [XmlElement(Namespace ="http://www.cohowinery.com")]  
    public Price PRICE;  
}  
```  
  
## Siehe auch  
 [Das XML Schema Definition\-Tool und die XML\-Serialisierung](../../../docs/framework/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)   
 [Einführung in die XML\-Serialisierung](../../../docs/framework/serialization/introducing-xml-serialization.md)   
 [XmlSerializer Class](https://msdn.microsoft.com/en-us/library/system.xml.serialization.xmlserializer.aspx)   
 [Attribute zur Steuerung der XML\-Serialisierung](../../../docs/framework/serialization/attributes-that-control-xml-serialization.md)   
 [XmlSerializerNamespaces Class](frlrfSystemXmlSerializationXmlSerializerNamespacesClassTopic)   
 [Vorgehensweise: Angeben eines alternativen Elementnamens für einen XML\-Stream](../../../docs/framework/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)   
 [Vorgehensweise: Serialisieren eines Objekts](../../../docs/framework/serialization/how-to-serialize-an-object.md)   
 [Vorgehensweise: Deserialisieren eines Objekts](../../../docs/framework/serialization/how-to-deserialize-an-object.md)