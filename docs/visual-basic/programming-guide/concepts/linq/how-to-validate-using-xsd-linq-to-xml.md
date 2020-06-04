---
title: 'Vorgehensweise: Überprüfen mit XSD (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: a0fe88d4-4e77-49e7-90de-8953feeccc21
ms.openlocfilehash: fd9931530bde2c47dcc8c7b7363a0d5ffae85b8a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84383091"
---
# <a name="how-to-validate-using-xsd-linq-to-xml-visual-basic"></a><span data-ttu-id="a4729-102">Vorgehensweise: Überprüfen mithilfe von XSD (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4729-102">How to: Validate Using XSD (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="a4729-103">Der <xref:System.Xml.Schema>-Namespace enthält Erweiterungsmethoden, die ein einfaches Validieren von XML-Strukturen anhand von XSD-Dateien ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a4729-103">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XML Schema Definition Language (XSD) file.</span></span> <span data-ttu-id="a4729-104">Weitere Informationen finden Sie in der Dokumentation zur <xref:System.Xml.Schema.Extensions.Validate%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="a4729-104">For more information, see the <xref:System.Xml.Schema.Extensions.Validate%2A> method documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4729-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a4729-105">Example</span></span>  
 <span data-ttu-id="a4729-106">Das folgende Beispiel erstellt ein <xref:System.Xml.Schema.XmlSchemaSet> und validiert dann anhand des Schemasatzes die beiden <xref:System.Xml.Linq.XDocument>-Objekte.</span><span class="sxs-lookup"><span data-stu-id="a4729-106">The following example creates an <xref:System.Xml.Schema.XmlSchemaSet>, then validates two <xref:System.Xml.Linq.XDocument> objects against the schema set.</span></span> <span data-ttu-id="a4729-107">Eines der Dokumente ist gültig, das andere nicht.</span><span class="sxs-lookup"><span data-stu-id="a4729-107">One of the documents is valid, the other is not.</span></span>  
  
```vb  
Dim errors As Boolean = False  
  
Private Sub XSDErrors(ByVal o As Object, ByVal e As ValidationEventArgs)  
    Console.WriteLine("{0}", e.Message)  
    errors = True  
End Sub  
  
Sub Main()  
    Dim xsdMarkup As XElement = _  
        <xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'>  
            <xsd:element name='Root'>  
                <xsd:complexType>  
                    <xsd:sequence>  
                        <xsd:element name='Child1' minOccurs='1' maxOccurs='1'/>  
                        <xsd:element name='Child2' minOccurs='1' maxOccurs='1'/>  
                    </xsd:sequence>  
                </xsd:complexType>  
            </xsd:element>  
        </xsd:schema>  
    Dim schemas As XmlSchemaSet = New XmlSchemaSet()  
    schemas.Add("", xsdMarkup.CreateReader)  
  
    Dim doc1 As XDocument = _  
        <?xml version='1.0'?>  
        <Root>  
            <Child1>content1</Child1>  
            <Child2>content1</Child2>  
        </Root>  
  
    Dim doc2 As XDocument = _  
        <?xml version='1.0'?>  
        <Root>  
            <Child1>content1</Child1>  
            <Child3>content1</Child3>  
        </Root>  
  
    Console.WriteLine("Validating doc1")  
    errors = False  
    doc1.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("doc1 {0}", IIf(errors = True, "did not validate", "validated"))  
  
    Console.WriteLine()  
    Console.WriteLine("Validating doc2")  
    errors = False  
    doc2.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("doc2 {0}", IIf(errors = True, "did not validate", "validated"))  
End Sub  
```  
  
 <span data-ttu-id="a4729-108">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a4729-108">This example produces the following output:</span></span>  
  
```console  
Validating doc1  
doc1 validated  
  
Validating doc2  
The element 'Root' has invalid child element 'Child3'. List of possible elements expected: 'Child2'.  
doc2 did not validate  
```  
  
## <a name="example"></a><span data-ttu-id="a4729-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a4729-109">Example</span></span>  
 <span data-ttu-id="a4729-110">In dem folgenden Beispiel wird überprüft, ob das XML-Dokument aus [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md) laut dem Schema aus [Beispiel-XSD-Datei: Kunden und Bestellungen](sample-xsd-file-customers-and-orders.md) gültig ist.</span><span class="sxs-lookup"><span data-stu-id="a4729-110">The following example validates that the XML document from [Sample XML File: Customers and Orders (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md) is valid per the schema from [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md).</span></span> <span data-ttu-id="a4729-111">Anschließend ändert das Beispiel das XML-Quelldokument.</span><span class="sxs-lookup"><span data-stu-id="a4729-111">It then modifies the source XML document.</span></span> <span data-ttu-id="a4729-112">Dabei wird das `CustomerID`-Attribut für den ersten Kunden geändert.</span><span class="sxs-lookup"><span data-stu-id="a4729-112">It changes the `CustomerID` attribute on the first customer.</span></span> <span data-ttu-id="a4729-113">Nach der Änderung verweisen die Aufträge auf einen Kunden, der nicht existiert, sodass das XML-Dokument nicht mehr als gültig angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="a4729-113">After the change, orders will then refer to a customer that does not exist, so the XML document will no longer validate.</span></span>  
  
 <span data-ttu-id="a4729-114">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="a4729-114">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="a4729-115">In diesem Beispiel wird das folgende XML-Schema verwendet: [Beispiel-XML-Datei: Kunden und Bestellungen (LINQ to XML)](sample-xsd-file-customers-and-orders.md).</span><span class="sxs-lookup"><span data-stu-id="a4729-115">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](sample-xsd-file-customers-and-orders.md).</span></span>  
  
```vb  
Dim errors As Boolean = False  
  
Private Sub XSDErrors(ByVal o As Object, ByVal e As ValidationEventArgs)  
    Console.WriteLine("{0}", e.Message)  
    errors = True  
End Sub  
  
Sub Main()  
    Dim schemas As XmlSchemaSet = New XmlSchemaSet()  
    schemas.Add("", "CustomersOrders.xsd")  
  
    Console.WriteLine("Attempting to validate")  
    Dim custOrdDoc As XDocument = XDocument.Load("CustomersOrders.xml")  
    errors = False  
    custOrdDoc.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("custOrdDoc {0}", IIf(errors, "did not validate", "validated"))  
  
    Console.WriteLine()  
    ' Modify the source document so that it will not validate.  
    custOrdDoc.<Root>.<Orders>.<Order>.<CustomerID>(0).Value = "AAAAA"  
    Console.WriteLine("Attempting to validate after modification")  
    errors = False  
    custOrdDoc.Validate(schemas, AddressOf XSDErrors)  
    Console.WriteLine("custOrdDoc {0}", IIf(errors, "did not validate", "validated"))  
End Sub  
```  
  
 <span data-ttu-id="a4729-116">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="a4729-116">This example produces the following output:</span></span>  
  
```console  
Attempting to validate  
custOrdDoc validated  
  
Attempting to validate after modification  
The key sequence 'AAAAA' in Keyref fails to refer to some key.  
custOrdDoc did not validate  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4729-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a4729-117">See also</span></span>

- <xref:System.Xml.Schema.Extensions.Validate%2A>
- [<span data-ttu-id="a4729-118">Erstellen von XML-Strukturen (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a4729-118">Creating XML Trees (Visual Basic)</span></span>](creating-xml-trees.md)
