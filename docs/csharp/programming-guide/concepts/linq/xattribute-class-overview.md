---
title: Übersicht der XAttribute-Klasse (C#)
description: Attribute sind Name/Wert-Paare, die einem Element zugeordnet sind. Das XAttribute repräsentiert XML-Attribute. Hier erfahren Sie, wie Sie in LINQ to XML in C# mit Attributen arbeiten.
ms.date: 07/20/2015
ms.assetid: 5a630f24-f9ad-400e-831e-c14ebfc9e142
ms.openlocfilehash: 8a19de601041bbb20241c959e909483b97bcf797
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302229"
---
# <a name="xattribute-class-overview-c"></a><span data-ttu-id="bec9b-105">Übersicht der XAttribute-Klasse (C#)</span><span class="sxs-lookup"><span data-stu-id="bec9b-105">XAttribute Class Overview (C#)</span></span>
<span data-ttu-id="bec9b-106">Attribute sind Name/Wert-Paare, die einem Element zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bec9b-106">Attributes are name/value pairs that are associated with an element.</span></span> <span data-ttu-id="bec9b-107">Die <xref:System.Xml.Linq.XAttribute>-Klasse stellt XML-Attribute dar.</span><span class="sxs-lookup"><span data-stu-id="bec9b-107">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="bec9b-108">Übersicht</span><span class="sxs-lookup"><span data-stu-id="bec9b-108">Overview</span></span>  
 <span data-ttu-id="bec9b-109">Das Arbeiten mit Attributen in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] ist vergleichbar mit dem Arbeiten mit Elementen.</span><span class="sxs-lookup"><span data-stu-id="bec9b-109">Working with attributes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is similar to working with elements.</span></span> <span data-ttu-id="bec9b-110">Ihre Konstruktoren ähneln sich,</span><span class="sxs-lookup"><span data-stu-id="bec9b-110">Their constructors are similar.</span></span> <span data-ttu-id="bec9b-111">und auch die Methoden zum Aufrufen von Auflistungen sind ähnlich.</span><span class="sxs-lookup"><span data-stu-id="bec9b-111">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="bec9b-112">Ein LINQ-Abfrageausdruck für eine Sammlung von Attributen sieht einem LINQ-Abfrageausdruck für eine Sammlung von Elementen sehr ähnlich.</span><span class="sxs-lookup"><span data-stu-id="bec9b-112">A LINQ query expression for a collection of attributes looks very similar to a LINQ query expression for a collection of elements.</span></span>  
  
 <span data-ttu-id="bec9b-113">Die Reihenfolge, in der einem Element Attribute hinzugefügt wurden, wird beibehalten.</span><span class="sxs-lookup"><span data-stu-id="bec9b-113">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="bec9b-114">Das heißt, wenn Sie die Attribute durchlaufen, sehen Sie die Attribute genau in der Reihenfolge, in der sie hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="bec9b-114">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>  
  
## <a name="the-xattribute-constructor"></a><span data-ttu-id="bec9b-115">Der "XAttribute"-Konstruktor</span><span class="sxs-lookup"><span data-stu-id="bec9b-115">The XAttribute Constructor</span></span>  
 <span data-ttu-id="bec9b-116">Der folgende Konstruktor der <xref:System.Xml.Linq.XAttribute>-Klasse ist der Konstruktor, den Sie am häufigsten verwenden werden:</span><span class="sxs-lookup"><span data-stu-id="bec9b-116">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you will most commonly use:</span></span>  
  
|<span data-ttu-id="bec9b-117">Konstruktor</span><span class="sxs-lookup"><span data-stu-id="bec9b-117">Constructor</span></span>|<span data-ttu-id="bec9b-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="bec9b-118">Description</span></span>|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<span data-ttu-id="bec9b-119">Sie erstellt ein <xref:System.Xml.Linq.XAttribute>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="bec9b-119">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="bec9b-120">Das `name`-Argument gibt den Namen des Attributs an, während `content` den Inhalt des Attributs angibt.</span><span class="sxs-lookup"><span data-stu-id="bec9b-120">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|  
  
### <a name="creating-an-element-with-an-attribute"></a><span data-ttu-id="bec9b-121">Erstellen eines Elements mit einem Attribut</span><span class="sxs-lookup"><span data-stu-id="bec9b-121">Creating an Element with an Attribute</span></span>  
 <span data-ttu-id="bec9b-122">Der folgende Code zeigt die häufige Aufgabe des Erstellens eines Elements mit einem Attribut:</span><span class="sxs-lookup"><span data-stu-id="bec9b-122">The following code shows the common task of creating an element that contains an attribute:</span></span>  
  
```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 <span data-ttu-id="bec9b-123">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="bec9b-123">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a><span data-ttu-id="bec9b-124">Funktionale Konstruktion von Attributen</span><span class="sxs-lookup"><span data-stu-id="bec9b-124">Functional Construction of Attributes</span></span>  
 <span data-ttu-id="bec9b-125">Mit der Konstruktion von <xref:System.Xml.Linq.XAttribute>-Objekten können Sie <xref:System.Xml.Linq.XElement>-Objekte "inline" erstellen, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="bec9b-125">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as follows:</span></span>  
  
```csharp  
XElement c = new XElement("Customers",  
    new XElement("Customer",  
        new XElement("Name", "John Doe"),  
        new XElement("PhoneNumbers",  
            new XElement("Phone",  
                new XAttribute("type", "home"),  
                "555-555-5555"),  
            new XElement("Phone",  
                new XAttribute("type", "work"),  
                "666-666-6666")  
        )  
    )  
);  
Console.WriteLine(c);  
```  
  
 <span data-ttu-id="bec9b-126">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="bec9b-126">This example produces the following output:</span></span>  
  
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
  
### <a name="attributes-are-not-nodes"></a><span data-ttu-id="bec9b-127">Attribute sind keine Knoten</span><span class="sxs-lookup"><span data-stu-id="bec9b-127">Attributes Are Not Nodes</span></span>  
 <span data-ttu-id="bec9b-128">Es gibt einige Unterschiede zwischen Attributen und Elementen.</span><span class="sxs-lookup"><span data-stu-id="bec9b-128">There are some differences between attributes and elements.</span></span> <span data-ttu-id="bec9b-129"><xref:System.Xml.Linq.XAttribute>-Objekte sind keine Knoten in der XML-Struktur.</span><span class="sxs-lookup"><span data-stu-id="bec9b-129"><xref:System.Xml.Linq.XAttribute> objects are not nodes in the XML tree.</span></span> <span data-ttu-id="bec9b-130">Sie sind Name/Wert-Paare, die einem XML-Element zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="bec9b-130">They are name/value pairs associated with an XML element.</span></span> <span data-ttu-id="bec9b-131">Im Unterschied zum Dokumentobjektmodell (DOM) reflektiert dies die Struktur des XML genauer.</span><span class="sxs-lookup"><span data-stu-id="bec9b-131">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="bec9b-132">Auch wenn <xref:System.Xml.Linq.XAttribute>-Objekte keine Knoten in der XML-Struktur im eigentlichen Sinne sind, ist das Arbeiten mit <xref:System.Xml.Linq.XAttribute>-Objekten vergleichbar mit dem Arbeiten mit <xref:System.Xml.Linq.XElement>-Objekten.</span><span class="sxs-lookup"><span data-stu-id="bec9b-132">Although <xref:System.Xml.Linq.XAttribute> objects are not actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is very similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="bec9b-133">Diese Unterscheidung ist im Wesentlichen nur für Entwickler von Bedeutung, die Code schreiben, der mit XML-Strukturen auf Knotenebene arbeitet.</span><span class="sxs-lookup"><span data-stu-id="bec9b-133">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="bec9b-134">Für die meisten Entwickler dürfte dieser Unterschied ohne praktische Bedeutung sein.</span><span class="sxs-lookup"><span data-stu-id="bec9b-134">Many developers will not be concerned with this distinction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bec9b-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bec9b-135">See also</span></span>

- [<span data-ttu-id="bec9b-136">LINQ to XML Programming Overview (C#) (Übersicht der LINQ to XML-Programmierung (C#))</span><span class="sxs-lookup"><span data-stu-id="bec9b-136">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
