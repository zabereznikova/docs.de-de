---
title: Übersicht über die XAttribute-Klasse (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
ms.openlocfilehash: 08b8ebf31a39325c98023d4bb333f8e06bbdeb3f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2018
ms.locfileid: "43406427"
---
# <a name="xattribute-class-overview-visual-basic"></a><span data-ttu-id="c7806-102">Übersicht über die XAttribute-Klasse (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7806-102">XAttribute Class Overview (Visual Basic)</span></span>
<span data-ttu-id="c7806-103">Attribute sind Name/Wert-Paare, die einem Element zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c7806-103">Attributes are name/value pairs that are associated with an element.</span></span> <span data-ttu-id="c7806-104">Die <xref:System.Xml.Linq.XAttribute>-Klasse stellt XML-Attribute dar.</span><span class="sxs-lookup"><span data-stu-id="c7806-104">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="c7806-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="c7806-105">Overview</span></span>  
 <span data-ttu-id="c7806-106">Das Arbeiten mit Attributen in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist vergleichbar mit dem Arbeiten mit Elementen.</span><span class="sxs-lookup"><span data-stu-id="c7806-106">Working with attributes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is similar to working with elements.</span></span> <span data-ttu-id="c7806-107">Ihre Konstruktoren ähneln sich,</span><span class="sxs-lookup"><span data-stu-id="c7806-107">Their constructors are similar.</span></span> <span data-ttu-id="c7806-108">und auch die Methoden zum Aufrufen von Auflistungen sind ähnlich.</span><span class="sxs-lookup"><span data-stu-id="c7806-108">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="c7806-109">Ein [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageausdruck für eine Auflistung von Attributen sieht einem [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageausdruck für eine Auflistung von Elementen sehr ähnlich.</span><span class="sxs-lookup"><span data-stu-id="c7806-109">A [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression for a collection of attributes looks very similar to a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression for a collection of elements.</span></span>  
  
 <span data-ttu-id="c7806-110">Die Reihenfolge, in der einem Element Attribute hinzugefügt wurden, wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="c7806-110">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="c7806-111">Das heißt, wenn Sie die Attribute durchlaufen, sehen Sie die Attribute genau in der Reihenfolge, in der sie hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="c7806-111">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>  
  
## <a name="the-xattribute-constructor"></a><span data-ttu-id="c7806-112">Der "XAttribute"-Konstruktor</span><span class="sxs-lookup"><span data-stu-id="c7806-112">The XAttribute Constructor</span></span>  
 <span data-ttu-id="c7806-113">Der folgende Konstruktor der <xref:System.Xml.Linq.XAttribute>-Klasse ist der Konstruktor, den Sie am häufigsten verwenden werden:</span><span class="sxs-lookup"><span data-stu-id="c7806-113">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you will most commonly use:</span></span>  
  
|<span data-ttu-id="c7806-114">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="c7806-114">Constructor</span></span>|<span data-ttu-id="c7806-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c7806-115">Description</span></span>|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<span data-ttu-id="c7806-116">Sie erstellt ein <xref:System.Xml.Linq.XAttribute>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="c7806-116">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="c7806-117">Das `name`-Argument gibt den Namen des Attributs an, während `content` den Inhalt des Attributs angibt.</span><span class="sxs-lookup"><span data-stu-id="c7806-117">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|  
  
### <a name="creating-an-element-with-an-attribute"></a><span data-ttu-id="c7806-118">Erstellen eines Elements mit einem Attribut</span><span class="sxs-lookup"><span data-stu-id="c7806-118">Creating an Element with an Attribute</span></span>  
 <span data-ttu-id="c7806-119">Der folgende Code zeigt ein Element, das ein Attribut mit der XML-Literale in Visual Basic enthält:</span><span class="sxs-lookup"><span data-stu-id="c7806-119">The following code shows an element that contains an attribute using XML literals in Visual Basic:</span></span>  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 <span data-ttu-id="c7806-120">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c7806-120">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a><span data-ttu-id="c7806-121">Funktionale Konstruktion von Attributen</span><span class="sxs-lookup"><span data-stu-id="c7806-121">Functional Construction of Attributes</span></span>  
 <span data-ttu-id="c7806-122">Mit der Konstruktion von <xref:System.Xml.Linq.XAttribute>-Objekten können Sie <xref:System.Xml.Linq.XElement>-Objekte "inline" erstellen, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="c7806-122">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as follows:</span></span>  
  
```vb  
Dim c As XElement = _  
    <Customers>  
        <Customer>  
            <Name>John Doe</Name>  
            <PhoneNumbers>  
                <Phone type="home">555-555-5555</Phone>  
                <Phone type="work">666-666-6666</Phone>  
            </PhoneNumbers>  
        </Customer>  
    </Customers>  
Console.WriteLine(c)  
```  
  
 <span data-ttu-id="c7806-123">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="c7806-123">This example produces the following output:</span></span>  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a><span data-ttu-id="c7806-124">Attribute sind keine Knoten</span><span class="sxs-lookup"><span data-stu-id="c7806-124">Attributes Are Not Nodes</span></span>  
 <span data-ttu-id="c7806-125">Es gibt einige Unterschiede zwischen Attributen und Elementen.</span><span class="sxs-lookup"><span data-stu-id="c7806-125">There are some differences between attributes and elements.</span></span> <span data-ttu-id="c7806-126"><xref:System.Xml.Linq.XAttribute>-Objekte sind keine Knoten in der XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="c7806-126"><xref:System.Xml.Linq.XAttribute> objects are not nodes in the XML tree.</span></span> <span data-ttu-id="c7806-127">Sie sind Name/Wert-Paare, die einem XML-Element zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c7806-127">They are name/value pairs associated with an XML element.</span></span> <span data-ttu-id="c7806-128">Im Unterschied zum Dokumentobjektmodell (DOM) reflektiert dies die Struktur des XML genauer.</span><span class="sxs-lookup"><span data-stu-id="c7806-128">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="c7806-129">Auch wenn <xref:System.Xml.Linq.XAttribute>-Objekte keine Knoten in der XML-Struktur im eigentlichen Sinne sind, ist das Arbeiten mit <xref:System.Xml.Linq.XAttribute>-Objekten vergleichbar mit dem Arbeiten mit <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="c7806-129">Although <xref:System.Xml.Linq.XAttribute> objects are not actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is very similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="c7806-130">Diese Unterscheidung ist im Wesentlichen nur für Entwickler von Bedeutung, die Code schreiben, der mit XML-Strukturen auf Knotenebene arbeitet.</span><span class="sxs-lookup"><span data-stu-id="c7806-130">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="c7806-131">Für die meisten Entwickler dürfte dieser Unterschied ohne praktische Bedeutung sein.</span><span class="sxs-lookup"><span data-stu-id="c7806-131">Many developers will not be concerned with this distinction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7806-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7806-132">See Also</span></span>  
 [<span data-ttu-id="c7806-133">LINQ to XML Programming Overview (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7806-133">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
