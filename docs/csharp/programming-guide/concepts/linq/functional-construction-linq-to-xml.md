---
title: Funktionale Konstruktion (LINQ to XML) (C#)
description: Hier erfahren Sie, wie die LINQ to XML-Programmierschnittstelle funktionale Konstruktion ermöglicht, also die Möglichkeit, einen XML-Baum in einer einzelnen Anweisung in C# zu erstellen.
ms.date: 07/20/2015
ms.assetid: 57a82bcf-de03-4f1c-a0c8-9a76e989d542
ms.openlocfilehash: f209a7ef2a4597ec8eeccb3083b77223a27e7a65
ms.sourcegitcommit: 04022ca5d00b2074e1b1ffdbd76bec4950697c4c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2020
ms.locfileid: "87103770"
---
# <a name="functional-construction-linq-to-xml-c"></a><span data-ttu-id="3e5f3-103">Funktionale Konstruktion (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="3e5f3-103">Functional Construction (LINQ to XML) (C#)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="3e5f3-104">bietet mit der *funktionalen Konstruktion* eine leistungsfähige Möglichkeit zur Erstellung von XML-Elementen.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-104">provides a powerful way to create XML elements called *functional construction*.</span></span> <span data-ttu-id="3e5f3-105">Funktionale Konstruktion ist die Fähigkeit, eine XML-Struktur in einer einzelnen Anweisung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-105">Functional construction is the ability to create an XML tree in a single statement.</span></span>  
  
 <span data-ttu-id="3e5f3-106">Es gibt mehrere wichtige Features der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Programmierschnittstelle, die für die funktionale Konstruktion verantwortlich sind:</span><span class="sxs-lookup"><span data-stu-id="3e5f3-106">There are several key features of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] programming interface that enable functional construction:</span></span>  
  
- <span data-ttu-id="3e5f3-107">Der <xref:System.Xml.Linq.XElement>-Konstruktor akzeptiert verschiedene Argumentarten als Inhalt.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-107">The <xref:System.Xml.Linq.XElement> constructor takes various types of arguments for content.</span></span> <span data-ttu-id="3e5f3-108">So können Sie z. B. ein anderes <xref:System.Xml.Linq.XElement>-Objekt übergeben, das zu einem untergeordneten Element wird.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-108">For example, you can pass another <xref:System.Xml.Linq.XElement> object, which becomes a child element.</span></span> <span data-ttu-id="3e5f3-109">Sie können auch ein <xref:System.Xml.Linq.XAttribute>-Objekt übergeben, das zu einem Attribut des Elements wird.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-109">You can pass an <xref:System.Xml.Linq.XAttribute> object, which becomes an attribute of the element.</span></span> <span data-ttu-id="3e5f3-110">Oder Sie übergeben ein beliebiges anderes Objekt, das in eine Zeichenfolge konvertiert wird und zum Textinhalt des Elements wird.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-110">Or you can pass any other type of object, which is converted to a string and becomes the text content of the element.</span></span>  
  
- <span data-ttu-id="3e5f3-111">Der <xref:System.Xml.Linq.XElement>-Konstruktor verwendet ein `params`-Array vom Typ <xref:System.Object>, sodass Sie beliebig viele Objekte an den Konstruktor übergeben können.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-111">The <xref:System.Xml.Linq.XElement> constructor takes a `params` array of type <xref:System.Object>, so that you can pass any number of objects to the constructor.</span></span> <span data-ttu-id="3e5f3-112">Auf diese Weise können Sie ein Element erstellen, das über komplexen Inhalt verfügt.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-112">This enables you to create an element that has complex content.</span></span>  
  
- <span data-ttu-id="3e5f3-113">Wenn ein Objekt eine <xref:System.Collections.Generic.IEnumerable%601> implementiert, wird die Auflistung im Objekt aufgezählt, und alle Elemente in der Auflistung werden hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-113">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="3e5f3-114">Wenn die Auflistung <xref:System.Xml.Linq.XElement>-Objekte oder <xref:System.Xml.Linq.XAttribute>-Objekte enthält, wird jedes Element in der Auflistung getrennt hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-114">If the collection contains <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="3e5f3-115">Dies ist wichtig, da Sie auf diese Weise die Ergebnisse einer LINQ-Abfrage an den Konstruktor übergeben können.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-115">This is important because it lets you pass the results of a LINQ query to the constructor.</span></span>  
  
 <span data-ttu-id="3e5f3-116">Diese Funktionen ermöglichen es Ihnen, Code zu schreiben, um eine XML-Struktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3e5f3-116">These features enable you to write code to create an XML tree.</span></span> <span data-ttu-id="3e5f3-117">Im Folgenden finden Sie ein Beispiel dazu:</span><span class="sxs-lookup"><span data-stu-id="3e5f3-117">The following is an example:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),  
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="3e5f3-118">Diese Funktionen ermöglichen es Ihnen auch, Code zu schreiben, der die Ergebnisse von LINQ-Abfragen verwendet, wenn Sie wie folgt eine XML-Struktur erstellen:</span><span class="sxs-lookup"><span data-stu-id="3e5f3-118">These features also enable you to write code that uses the results of LINQ queries when you create an XML tree, as follows:</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 <span data-ttu-id="3e5f3-119">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3e5f3-119">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  