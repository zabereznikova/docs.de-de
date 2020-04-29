---
title: 'Gewusst wie: Qualifizieren von XML-Element- und XML-Attributnamen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- qualifying XML names
- qualifying XML elements
- XML namespaces, qualifying elements and names in
ms.assetid: 44719f90-7e15-42e8-a9e2-282287e2b5bf
ms.openlocfilehash: db0795dd83cc96aba49dd435c875e98a9a6c18cb
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159870"
---
# <a name="how-to-qualify-xml-element-and-xml-attribute-names"></a><span data-ttu-id="79c8b-102">Gewusst wie: Qualifizieren von XML-Element- und XML-Attributnamen</span><span class="sxs-lookup"><span data-stu-id="79c8b-102">How to qualify XML element and XML attribute names</span></span>

<span data-ttu-id="79c8b-103">In Instanzen der <xref:System.Xml.Serialization.XmlSerializerNamespaces>-Klasse enthaltene XML-Namespaces müssen der Spezifikation [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/) des World Wide Web Consortium (W3C) entsprechen.</span><span class="sxs-lookup"><span data-stu-id="79c8b-103">XML namespaces contained by instances of the <xref:System.Xml.Serialization.XmlSerializerNamespaces> class must conform to the World Wide Web Consortium (W3C) specification called [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/).</span></span>

<span data-ttu-id="79c8b-104">XML-Namespaces stellen eine Methode zur Qualifizierung der Namen von XML-Elementen und XML-Attributen in XML-Dokumenten bereit.</span><span class="sxs-lookup"><span data-stu-id="79c8b-104">XML namespaces provide a method for qualifying the names of XML elements and XML attributes in XML documents.</span></span> <span data-ttu-id="79c8b-105">Ein qualifizierter Name besteht aus einem Präfix und einem lokalen Namen, die durch einen Doppelpunkt voneinander getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="79c8b-105">A qualified name consists of a prefix and a local name, separated by a colon.</span></span> <span data-ttu-id="79c8b-106">Das Präfix wird nur als Platzhalter verwendet und ist einem URI zugeordnet, der den Namespace angibt.</span><span class="sxs-lookup"><span data-stu-id="79c8b-106">The prefix functions only as a placeholder; it is mapped to a URI that specifies a namespace.</span></span> <span data-ttu-id="79c8b-107">Die Kombination aus dem global verwalteten URI-Namespace und dem lokalen Namen bildet einen weltweit garantiert eindeutigen Namen.</span><span class="sxs-lookup"><span data-stu-id="79c8b-107">The combination of the universally managed URI namespace and the local name produces a name that is guaranteed to be universally unique.</span></span>

<span data-ttu-id="79c8b-108">Sie können die in einem XML-Dokument verwendeten Präfixe festlegen, indem Sie eine Instanz von `XmlSerializerNamespaces` erstellen und die Namespacepaare dem Objekt hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="79c8b-108">By creating an instance of `XmlSerializerNamespaces` and adding the namespace pairs to the object, you can specify the prefixes used in an XML document.</span></span>

## <a name="to-create-qualified-names-in-an-xml-document"></a><span data-ttu-id="79c8b-109">So erstellen Sie qualifizierte Namen in einem XML-Dokument</span><span class="sxs-lookup"><span data-stu-id="79c8b-109">To create qualified names in an XML document</span></span>

1. <span data-ttu-id="79c8b-110">Erstellen Sie eine Instanz der `XmlSerializerNamespaces`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="79c8b-110">Create an instance of the `XmlSerializerNamespaces` class.</span></span>

2. <span data-ttu-id="79c8b-111">Fügen Sie alle Präfixe und Namespacepaare zu `XmlSerializerNamespaces` hinzu.</span><span class="sxs-lookup"><span data-stu-id="79c8b-111">Add all prefixes and namespace pairs to the `XmlSerializerNamespaces`.</span></span>

3. <span data-ttu-id="79c8b-112">Wenden Sie das geeignete `System.Xml.Serialization`-Attribut auf jeden Member oder jede Klasse an, die von <xref:System.Xml.Serialization.XmlSerializer> in ein XML-Dokument serialisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="79c8b-112">Apply the appropriate `System.Xml.Serialization` attribute to each member or class that the <xref:System.Xml.Serialization.XmlSerializer> is to serialize into an XML document.</span></span>

    <span data-ttu-id="79c8b-113">Folgende Attribute sind verfügbar: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute> und <xref:System.Xml.Serialization.XmlTypeAttribute>.</span><span class="sxs-lookup"><span data-stu-id="79c8b-113">The available attributes are: <xref:System.Xml.Serialization.XmlAnyElementAttribute>, <xref:System.Xml.Serialization.XmlArrayAttribute>, <xref:System.Xml.Serialization.XmlArrayItemAttribute>, <xref:System.Xml.Serialization.XmlAttributeAttribute>, <xref:System.Xml.Serialization.XmlElementAttribute>, <xref:System.Xml.Serialization.XmlRootAttribute>, and <xref:System.Xml.Serialization.XmlTypeAttribute>.</span></span>

4. <span data-ttu-id="79c8b-114">Legen Sie die `Namespace`-Eigenschaft jedes Attributs auf einen der Namespacewerte aus dem `XmlSerializerNamespaces`-Objekt fest.</span><span class="sxs-lookup"><span data-stu-id="79c8b-114">Set the `Namespace` property of each attribute to one of the namespace values from the `XmlSerializerNamespaces`.</span></span>

5. <span data-ttu-id="79c8b-115">Übergeben Sie `XmlSerializerNamespaces` an die `Serialize`-Methode von `XmlSerializer`.</span><span class="sxs-lookup"><span data-stu-id="79c8b-115">Pass the `XmlSerializerNamespaces` to the `Serialize` method of the `XmlSerializer`.</span></span>

## <a name="example"></a><span data-ttu-id="79c8b-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79c8b-116">Example</span></span>

<span data-ttu-id="79c8b-117">Im folgenden Beispiel wird ein `XmlSerializerNamespaces`-Objekt erstellt, dem zwei Paare aus Präfix und Namespace hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="79c8b-117">The following example creates an `XmlSerializerNamespaces`, and adds two prefix and namespace pairs to the object.</span></span> <span data-ttu-id="79c8b-118">Durch den Code wird ein `XmlSerializer`-Objekt erstellt, das verwendet wird, um eine Instanz der `Books`-Klasse zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="79c8b-118">The code creates an `XmlSerializer` that is used to serialize an instance of the `Books` class.</span></span> <span data-ttu-id="79c8b-119">Im Code wird die `Serialize`-Methode mit `XmlSerializerNamespaces` aufgerufen. Der XML-Stream kann daher Namespaces mit Präfixen enthalten.</span><span class="sxs-lookup"><span data-stu-id="79c8b-119">The code calls the `Serialize` method with the `XmlSerializerNamespaces`, allowing the XML to contain prefixed namespaces.</span></span>

```vb
Imports System.IO
Imports System.Xml
Imports System.Xml.Serialization

Public Module Program

    Public Sub Main()
        SerializeObject("XmlNamespaces.xml")
    End Sub

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
End Module

Public Class Books
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public Book As Book
End Class

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
    <XmlElement([Namespace] := "http://www.cohowinery.com")> _
    Public price As Decimal
End Class
```

```csharp
using System;
using System.IO;
using System.Xml;
using System.Xml.Serialization;

public class Program
{
    public static void Main()
    {
        SerializeObject("XmlNamespaces.xml");
    }

    public static void SerializeObject(string filename)
    {
        var mySerializer = new XmlSerializer(typeof(Books));
        // Writing a file requires a TextWriter.
        TextWriter myWriter = new StreamWriter(filename);

        // Creates an XmlSerializerNamespaces and adds two
        // prefix-namespace pairs.
        var myNamespaces = new XmlSerializerNamespaces();
        myNamespaces.Add("books", "http://www.cpandl.com");
        myNamespaces.Add("money", "http://www.cohowinery.com");

        // Creates a Book.
        var myBook = new Book();
        myBook.TITLE = "A Book Title";
        var myPrice = new Price();
        myPrice.price = (decimal) 9.95;
        myPrice.currency = "US Dollar";
        myBook.PRICE = myPrice;
        var myBooks = new Books();
        myBooks.Book = myBook;
        mySerializer.Serialize(myWriter, myBooks, myNamespaces);
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

public class Price
{
    [XmlAttribute(Namespace = "http://www.cpandl.com")]
    public string currency;
    [XmlElement(Namespace = "http://www.cohowinery.com")]
    public decimal price;
}
```

## <a name="see-also"></a><span data-ttu-id="79c8b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79c8b-120">See also</span></span>

- <xref:System.Xml.Serialization.XmlSerializer>
- [<span data-ttu-id="79c8b-121">Das XML Schema Definition-Tool und die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="79c8b-121">The XML Schema Definition Tool and XML Serialization</span></span>](the-xml-schema-definition-tool-and-xml-serialization.md)
- [<span data-ttu-id="79c8b-122">Einführung in die XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="79c8b-122">Introducing XML Serialization</span></span>](introducing-xml-serialization.md)
- [<span data-ttu-id="79c8b-123">XmlSerializer-Klasse</span><span class="sxs-lookup"><span data-stu-id="79c8b-123">XmlSerializer Class</span></span>](xref:System.Xml.Serialization.XmlSerializer)
- [<span data-ttu-id="79c8b-124">Attribute zur Steuerung der XML-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="79c8b-124">Attributes That Control XML Serialization</span></span>](attributes-that-control-xml-serialization.md)
- <span data-ttu-id="79c8b-125">[How to: Angeben eines alternativen Elementnamens für einen XML-Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md).</span><span class="sxs-lookup"><span data-stu-id="79c8b-125">[How to: Specify an Alternate Element Name for an XML Stream](how-to-specify-an-alternate-element-name-for-an-xml-stream.md)</span></span>
- <span data-ttu-id="79c8b-126">[How to: Serialisieren eines Objekts](how-to-serialize-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="79c8b-126">[How to: Serialize an Object](how-to-serialize-an-object.md)</span></span>
- <span data-ttu-id="79c8b-127">[How to: Deserialisieren eines Objekts](how-to-deserialize-an-object.md).</span><span class="sxs-lookup"><span data-stu-id="79c8b-127">[How to: Deserialize an Object](how-to-deserialize-an-object.md)</span></span>
