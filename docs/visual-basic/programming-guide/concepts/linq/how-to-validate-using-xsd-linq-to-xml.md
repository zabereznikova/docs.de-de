---
title: "Gewusst wie: Überprüfen mit XSD (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: a0fe88d4-4e77-49e7-90de-8953feeccc21
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d791bcb47243f1b9b2580617c7881d77b11aef1d
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="how-to-validate-using-xsd-linq-to-xml-visual-basic"></a><span data-ttu-id="19585-102">Gewusst wie: Überprüfen mit XSD (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="19585-102">How to: Validate Using XSD (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="19585-103">Der <xref:System.Xml.Schema>-Namespace enthält Erweiterungsmethoden, die eine XML-Struktur mit einer XML-Schema Definition Language (XSD) überprüft erleichtern.</xref:System.Xml.Schema></span><span class="sxs-lookup"><span data-stu-id="19585-103">The <xref:System.Xml.Schema> namespace contains extension methods that make it easy to validate an XML tree against an XML Schema Definition Language (XSD) file.</span></span> <span data-ttu-id="19585-104">Weitere Informationen finden Sie unter der <xref:System.Xml.Schema.Extensions.Validate%2A>Dokumentation.</xref:System.Xml.Schema.Extensions.Validate%2A></span><span class="sxs-lookup"><span data-stu-id="19585-104">For more information, see the <xref:System.Xml.Schema.Extensions.Validate%2A> method documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="19585-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19585-105">Example</span></span>  
 <span data-ttu-id="19585-106">Das folgende Beispiel erstellt eine <xref:System.Xml.Schema.XmlSchemaSet>, überprüft dann zwei <xref:System.Xml.Linq.XDocument>Objekte anhand des Schemasatzes.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Schema.XmlSchemaSet></span><span class="sxs-lookup"><span data-stu-id="19585-106">The following example creates an <xref:System.Xml.Schema.XmlSchemaSet>, then validates two <xref:System.Xml.Linq.XDocument> objects against the schema set.</span></span> <span data-ttu-id="19585-107">Eines der Dokumente ist gültig, das andere nicht.</span><span class="sxs-lookup"><span data-stu-id="19585-107">One of the documents is valid, the other is not.</span></span>  
  
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
  
 <span data-ttu-id="19585-108">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="19585-108">This example produces the following output:</span></span>  
  
```  
Validating doc1  
doc1 validated  
  
Validating doc2  
The element 'Root' has invalid child element 'Child3'. List of possible elements expected: 'Child2'.  
doc2 did not validate  
```  
  
## <a name="example"></a><span data-ttu-id="19585-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="19585-109">Example</span></span>  
 <span data-ttu-id="19585-110">Im folgenden Beispiel wird überprüft, dass das XML-Dokument aus [XML-Beispieldatei: Kunden und Bestellungen (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md) ist gemäß dem Schema aus [XSD-Beispieldatei: Customers und Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span><span class="sxs-lookup"><span data-stu-id="19585-110">The following example validates that the XML document from [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md) is valid per the schema from [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span></span> <span data-ttu-id="19585-111">Anschließend ändert das Beispiel das XML-Quelldokument.</span><span class="sxs-lookup"><span data-stu-id="19585-111">It then modifies the source XML document.</span></span> <span data-ttu-id="19585-112">Dabei wird das `CustomerID`-Attribut für den ersten Kunden geändert.</span><span class="sxs-lookup"><span data-stu-id="19585-112">It changes the `CustomerID` attribute on the first customer.</span></span> <span data-ttu-id="19585-113">Nach der Änderung verweisen die Aufträge auf einen Kunden, der nicht existiert, sodass das XML-Dokument nicht mehr als gültig angesehen wird.</span><span class="sxs-lookup"><span data-stu-id="19585-113">After the change, orders will then refer to a customer that does not exist, so the XML document will no longer validate.</span></span>  
  
 <span data-ttu-id="19585-114">Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Kunden und Bestellungen (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="19585-114">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="19585-115">Dieses Beispiel verwendet die folgende XSD-Schema: [XSD-Beispieldatei: Customers und Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span><span class="sxs-lookup"><span data-stu-id="19585-115">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](../../../../visual-basic/programming-guide/concepts/linq/sample-xsd-file-customers-and-orders.md).</span></span>  
  
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
  
 <span data-ttu-id="19585-116">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="19585-116">This example produces the following output:</span></span>  
  
```  
Attempting to validate  
custOrdDoc validated  
  
Attempting to validate after modification  
The key sequence 'AAAAA' in Keyref fails to refer to some key.  
custOrdDoc did not validate  
```  
  
## <a name="see-also"></a><span data-ttu-id="19585-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19585-117">See Also</span></span>  
 <span data-ttu-id="19585-118"><xref:System.Xml.Schema.Extensions.Validate%2A></xref:System.Xml.Schema.Extensions.Validate%2A></span><span class="sxs-lookup"><span data-stu-id="19585-118"><xref:System.Xml.Schema.Extensions.Validate%2A></span></span>   
<span data-ttu-id="19585-119"> [Erstellen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)</span><span class="sxs-lookup"><span data-stu-id="19585-119"> [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)</span></span>
