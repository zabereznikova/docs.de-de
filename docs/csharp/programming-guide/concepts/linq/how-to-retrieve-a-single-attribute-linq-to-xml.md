---
title: 'Vorgehensweise: Abrufen eines einzelnen Attributs (LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: 1b6b07b9-933f-47e9-874e-e790cab49dc5
ms.openlocfilehash: 31b34bddc9e748b473641235402847991d444c39
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347493"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-c"></a><span data-ttu-id="63332-102">Vorgehensweise: Abrufen eines einzelnen Attributs (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="63332-102">How to retrieve a single attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="63332-103">In diesem Thema wird die Vorgehensweise beim Abrufen eines einzelnen Attributs eines Elements anhand des Attributsnamens erläutert.</span><span class="sxs-lookup"><span data-stu-id="63332-103">This topic explains how to retrieve a single attribute of an element, given the attribute name.</span></span> <span data-ttu-id="63332-104">Diese Vorgehensweise eignet sich für das Schreiben von Abfrageausdrücken, mit denen Sie nach einem Element mit einem bestimmten Attribut suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="63332-104">This is useful for writing query expressions where you want to find an element that has a particular attribute.</span></span>  
  
 <span data-ttu-id="63332-105">Die <xref:System.Xml.Linq.XElement.Attribute%2A>-Methode der <xref:System.Xml.Linq.XElement>-Klasse gibt das <xref:System.Xml.Linq.XAttribute> mit dem angegebenen Namen zurück.</span><span class="sxs-lookup"><span data-stu-id="63332-105">The <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement> class returns the <xref:System.Xml.Linq.XAttribute> with the specified name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63332-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="63332-106">Example</span></span>  
 <span data-ttu-id="63332-107">Im folgenden Beispiel wird die <xref:System.Xml.Linq.XElement.Attribute%2A>-Methode verwendet:</span><span class="sxs-lookup"><span data-stu-id="63332-107">The following example uses the <xref:System.Xml.Linq.XElement.Attribute%2A> method.</span></span>  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 <span data-ttu-id="63332-108">Dieses Beispiel ermittelt zuerst alle Nachfolger in der Struktur mit dem Namen `Phone` und dann das Attribut mit dem Namen `type`.</span><span class="sxs-lookup"><span data-stu-id="63332-108">This example finds all the descendants in the tree named `Phone`, and then finds the attribute named `type`.</span></span>  
  
 <span data-ttu-id="63332-109">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="63332-109">This code produces the following output:</span></span>  
  
```output  
home  
work  
```  
  
## <a name="example"></a><span data-ttu-id="63332-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="63332-110">Example</span></span>  
 <span data-ttu-id="63332-111">Wenn Sie den Wert des Attributs abrufen möchten, können Sie es einfach genauso umwandeln, wie Sie es bei <xref:System.Xml.Linq.XElement>-Objekten machen würden.</span><span class="sxs-lookup"><span data-stu-id="63332-111">If you want to retrieve the value of the attribute, you can cast it, just as you do for with <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="63332-112">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="63332-112">The following example demonstrates this.</span></span>  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =   
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 <span data-ttu-id="63332-113">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="63332-113">This code produces the following output:</span></span>  
  
```output  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="63332-114">bietet explizite Umwandlungsoperatoren für die Umwandlung der <xref:System.Xml.Linq.XAttribute>-Klasse in `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` und `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="63332-114">provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63332-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="63332-115">Example</span></span>  
 <span data-ttu-id="63332-116">Das folgende Beispiel enthält denselben Code für ein Attribut, das sich in einem Namespace befindet.</span><span class="sxs-lookup"><span data-stu-id="63332-116">The following example shows the same code for an attribute that is in a namespace.</span></span> <span data-ttu-id="63332-117">Weitere Informationen finden Sie unter [Namespaces: Übersicht (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="63332-117">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement cust = new XElement(aw + "PhoneNumbers",  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "home"),  
        "555-555-5555"),  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants(aw + "Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute(aw + "type"));  
```  
  
 <span data-ttu-id="63332-118">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="63332-118">This code produces the following output:</span></span>  
  
```output  
home  
work  
```  
  
## <a name="see-also"></a><span data-ttu-id="63332-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63332-119">See also</span></span>

- [<span data-ttu-id="63332-120">LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))</span><span class="sxs-lookup"><span data-stu-id="63332-120">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
