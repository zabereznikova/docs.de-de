---
title: 'Vorgehensweise: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (C#)'
description: In diesem Artikel erfahren Sie, wie Sie mit LINQ to XML ein einzelnes untergeordnetes Element als Namen abrufen. In diesem C#-Beispiel gibt die Element-Methode das erste angegebene untergeordnete Element zurück.
ms.date: 07/20/2015
ms.assetid: ce37db9e-76fa-46eb-b4cc-e8f32d22ad90
ms.openlocfilehash: c3a044f30cf2e411bdff52586c7a370b626f41bc
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103279"
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-c"></a><span data-ttu-id="17efd-104">Vorgehensweise: Abrufen eines einzelnen untergeordneten Elements (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="17efd-104">How to retrieve a single child element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="17efd-105">In diesem Thema wird die Vorgehensweise beim Abrufen eines einzelnen untergeordneten Elements nach dessen Namen erläutert.</span><span class="sxs-lookup"><span data-stu-id="17efd-105">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="17efd-106">Wenn Sie den Namen des untergeordneten Elements kennen und wissen, dass es nur ein Element mit diesem Namen gibt, ist es möglicherweise sinnvoll, statt einer ganzen Auflistung nur ein einzelnes Element abzurufen.</span><span class="sxs-lookup"><span data-stu-id="17efd-106">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="17efd-107">Die <xref:System.Xml.Linq.XContainer.Element%2A>-Methode gibt das erste untergeordnete <xref:System.Xml.Linq.XElement> mit dem angegebenen <xref:System.Xml.Linq.XName> zurück.</span><span class="sxs-lookup"><span data-stu-id="17efd-107">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="17efd-108">Zum Abrufen eines einzelnen untergeordneten Elements in Visual Basic wird häufig die XML-Eigenschaft verwendet und dann das erste Element mittels der Arrayindexernotation abgerufen.</span><span class="sxs-lookup"><span data-stu-id="17efd-108">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17efd-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="17efd-109">Example</span></span>  
 <span data-ttu-id="17efd-110">Im folgenden Beispiel wird die Verwendung der <xref:System.Xml.Linq.XContainer.Element%2A>-Methode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="17efd-110">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="17efd-111">In diesem Beispiel wird die XML-Struktur mit dem Namen `po` genommen und nach dem ersten Element mit dem Namen `Comment` gesucht.</span><span class="sxs-lookup"><span data-stu-id="17efd-111">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="17efd-112">Das Visual Basic-Beispiel zeigt die Verwendung der Arrayindexernotation, um ein einzelnes Element abzurufen.</span><span class="sxs-lookup"><span data-stu-id="17efd-112">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="17efd-113">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Typische Bestellung (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="17efd-113">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
XElement e = po.Element("DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="17efd-114">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="17efd-114">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="17efd-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="17efd-115">Example</span></span>  
 <span data-ttu-id="17efd-116">Im folgenden Beispiel wird der gleiche Code für XML in einem Namespace gezeigt.</span><span class="sxs-lookup"><span data-stu-id="17efd-116">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="17efd-117">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="17efd-117">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="17efd-118">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Typische Bestellung in einem Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="17efd-118">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement e = po.Element(aw + "DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="17efd-119">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="17efd-119">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="17efd-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17efd-120">See also</span></span>

- [<span data-ttu-id="17efd-121">LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))</span><span class="sxs-lookup"><span data-stu-id="17efd-121">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
