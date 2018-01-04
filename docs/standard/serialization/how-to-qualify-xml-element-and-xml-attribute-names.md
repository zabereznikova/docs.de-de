---
title: 'Gewusst wie: Qualifizieren von XML-Element- und XML-Attributnamen'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- qualifying XML names
- qualifying XML elements
- XML namespaces, qualifying elements and names in
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 048bcc587915467f644a2cce695cec352147223a
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a><span data-ttu-id="af33b-102">Gewusst wie: Qualifizieren von XML-Element- und XML-Attributnamen</span><span class="sxs-lookup"><span data-stu-id="af33b-102">How to: Qualify XML Element and XML Attribute Names</span></span>
[<span data-ttu-id="af33b-103">Code Example (Codebeispiel)</span><span class="sxs-lookup"><span data-stu-id="af33b-103">Code Example</span></span>](#cpconworkingwithxmlnamespacesanchor1)  
  
 <span data-ttu-id="af33b-104">In Instanzen der <xref:System.Xml.Serialization.XmlSerializerNamespaces>-Klasse enthaltene XML-Namespaces müssen der Spezifikation "Namespaces in XML" des World Wide Web Consortium (www.w3.org) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="af33b-104">XML namespaces contained by instances of the <xref:System.Xml.Serialization.XmlSerializerNamespaces> class must conform to the World Wide Web Consortium (www.w3.org) specification called "Namespaces in XML."</span></span>  
  
 <span data-ttu-id="af33b-105">XML-Namespaces stellen eine Methode zur Qualifizierung der Namen von XML-Elementen und XML-Attributen in XML-Dokumenten bereit.</span><span class="sxs-lookup"><span data-stu-id="af33b-105">XML namespaces provide a method for qualifying the names of XML elements and XML attributes in XML documents.</span></span> <span data-ttu-id="af33b-106">Ein qualifizierter Name besteht aus einem Präfix und einem lokalen Namen, die durch einen Doppelpunkt voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="af33b-106">A qualified name consists of a prefix and a local name, separated by a colon.</span></span> <span data-ttu-id="af33b-107">Das Präfix wird nur als Platzhalter verwendet und ist einem URI zugeordnet, der den Namespace angibt.</span><span class="sxs-lookup"><span data-stu-id="af33b-107">The prefix functions only as a placeholder; it is mapped to a URI that specifies a namespace.</span></span> <span data-ttu-id="af33b-108">Die Kombination aus dem global verwalteten URI-Namespace und dem lokalen Namen bildet einen weltweit garantiert eindeutigen Namen.</span><span class="sxs-lookup"><span data-stu-id="af33b-108">The combination of the universally managed URI namespace and the local name produces a name that is guaranteed to be universally unique.</span></span>  
  
 <span data-ttu-id="af33b-109">Sie können die in einem XML-Dokument verwendeten Präfixe festlegen, indem Sie eine Instanz von `XmlSerializerNamespaces` erstellen und die Namespacepaare dem Objekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="af33b-109">By creating an instance of `XmlSerializerNamespaces` and adding the namespace pairs to the object, you can specify the prefixes used in an XML document.</span></span>  
  
### <a name="to-create-qualified-names-in-an-xml-document"></a><span data-ttu-id="af33b-110">So erstellen Sie qualifizierte Namen in einem XML-Dokument</span><span class="sxs-lookup"><span data-stu-id="af33b-110">To create qualified names in an XML document</span></span>  
  
1.  <span data-ttu-id="af33b-111">Erstellen Sie eine Instanz der `XmlSerializerNamespaces`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="af33b-111">Create an instance of the `XmlSerializerNamespaces` class.</span></span>  
  
2.  <span data-ttu-id="af33b-112">Fügen Sie alle Präfixe und Namespacepaare zu `XmlSerializerNamespaces` hinzu.</span><span class="sxs-lookup"><span data-stu-id="af33b-112">Add all prefixes and namespace pairs to the `XmlSerializerNamespaces`.</span></span>  
  
3.  <span data-ttu-id="af33b-113">Wenden Sie das geeignete `System.Xml.Serialization`-Attribut auf jeden Member oder jede Klasse an, die von <xref:System.Xml.Serialization.XmlSerializer> in ein XML-Dokument serialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="af33b-113">Apply the appropriate `System.Xml.Serialization` attribute to each member or class that the <xref:System.Xml.Serialization.XmlSerializer> is to serialize into an XML document.</span></span>  
  
     <span data-ttu-id="af33b-114">Folgende Attribute sind verfügbar: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute> und <xref:System.Xml.Serialization.XmlTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="af33b-114">The available attributes are: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span>  
  
4.  <span data-ttu-id="af33b-115">Legen Sie die `Namespace`-Eigenschaft jedes Attributs auf einen der Namespacewerte aus dem `XmlSerializerNamespaces`-Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="af33b-115">Set the `Namespace` property of each attribute to one of the namespace values from the `XmlSerializerNamespaces`.</span></span>  
  
5.  <span data-ttu-id="af33b-116">Übergeben Sie `XmlSerializerNamespaces` an die `Serialize`-Methode von `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="af33b-116">Pass the `XmlSerializerNamespaces` to the `Serialize` method of the `XmlSerializer`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af33b-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af33b-117">Example</span></span>  
 <span data-ttu-id="af33b-118">Im folgenden Beispiel wird ein `XmlSerializerNamespaces`-Objekt erstellt, dem zwei Paare aus Präfix und Namespace hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="af33b-118">The following example creates an `XmlSerializerNamespaces`, and adds two prefix and namespace pairs to the object.</span></span> <span data-ttu-id="af33b-119">Durch den Code wird ein `XmlSerializer`-Objekt erstellt, das verwendet wird, um eine Instanz der `Books`-Klasse zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="af33b-119">The code creates an `XmlSerializer` that is used to serialize an instance of the `Books` class.</span></span> <span data-ttu-id="af33b-120">Im Code wird die `Serialize`-Methode mit `XmlSerializerNamespaces` aufgerufen. Der XML-Stream kann daher Namespaces mit Präfixen enthalten.</span><span class="sxs-lookup"><span data-stu-id="af33b-120">The code calls the `Serialize` method with the `XmlSerializerNamespaces`, allowing the XML to contain prefixed namespaces.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="af33b-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af33b-121">See Also</span></span>  
 <xref:System.Xml.Serialization.XmlSerializer>  
 [<span data-ttu-id="af33b-122">Das XML Schema Definition-Tool und die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="af33b-122">The XML Schema Definition Tool and XML Serialization</span></span>](../../../docs/standard/serialization/the-xml-schema-definition-tool-and-xml-serialization.md)  
 [<span data-ttu-id="af33b-123">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="af33b-123">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="af33b-124">XmlSerializer-Klasse</span><span class="sxs-lookup"><span data-stu-id="af33b-124">XmlSerializer Class</span></span>](xref:System.Xml.Serialization.XmlSerializer)  
 [<span data-ttu-id="af33b-125">Attribute zur Steuerung der XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="af33b-125">Attributes That Control XML Serialization</span></span>](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md)  
 [<span data-ttu-id="af33b-126">Vorgehensweise: Angeben eines alternativen Elementnamens für einen XML-Stream</span><span class="sxs-lookup"><span data-stu-id="af33b-126">How to: Specify an Alternate Element Name for an XML Stream</span></span>](../../../docs/standard/serialization/how-to-specify-an-alternate-element-name-for-an-xml-stream.md)  
 [<span data-ttu-id="af33b-127">Vorgehensweise: Serialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="af33b-127">How to: Serialize an Object</span></span>](../../../docs/standard/serialization/how-to-serialize-an-object.md)  
 [<span data-ttu-id="af33b-128">Vorgehensweise: Deserialisieren eines Objekts</span><span class="sxs-lookup"><span data-stu-id="af33b-128">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
