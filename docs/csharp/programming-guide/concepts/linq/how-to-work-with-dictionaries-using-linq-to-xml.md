---
title: 'Vorgehensweise: Arbeiten mit Wörterbüchern unter Verwendung von LINQ to XML (C#)'
ms.date: 07/20/2015
ms.assetid: 57bcefe3-8433-4d3b-935a-511c9bcbdfa8
ms.openlocfilehash: 1a98293f208e80e969362fca27014ecd2e5c4183
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347224"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-c"></a><span data-ttu-id="05a6f-102">Vorgehensweise: Arbeiten mit Wörterbüchern unter Verwendung von LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="05a6f-102">How to work with dictionaries using LINQ to XML (C#)</span></span>
<span data-ttu-id="05a6f-103">Es ist häufig sinnvoll, verschiedene Datenstrukturen in XML und aus XML in andere Datenstrukturen umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="05a6f-103">It is often convenient to convert varieties of data structures to XML, and XML back to other data structures.</span></span> <span data-ttu-id="05a6f-104">In diesem Thema wird eine konkrete Implementierung dieser allgemeinen Herangehensweise gezeigt, bei der ein <xref:System.Collections.Generic.Dictionary%602> in XML umgewandelt und dann wieder zurückgewandelt wird.</span><span class="sxs-lookup"><span data-stu-id="05a6f-104">This topic shows a specific implementation of this general approach by converting a <xref:System.Collections.Generic.Dictionary%602> to XML and back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05a6f-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="05a6f-105">Example</span></span>  
 <span data-ttu-id="05a6f-106">In diesem Beispiel kommt eine Form einer funktionalen Konstruktion zum Einsatz, bei der eine Abfrage neue <xref:System.Xml.Linq.XElement>-Objekte projiziert, woraufhin die sich dabei ergebende Auflistung als Argument an den Konstruktor des <xref:System.Xml.Linq.XElement>-Objekts übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="05a6f-106">This example uses a form of functional construction in which a query projects new <xref:System.Xml.Linq.XElement> objects, and the resulting collection is passed as an argument to the constructor of the Root <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```csharp  
Dictionary<string, string> dict = new Dictionary<string, string>();  
dict.Add("Child1", "Value1");  
dict.Add("Child2", "Value2");  
dict.Add("Child3", "Value3");  
dict.Add("Child4", "Value4");  
XElement root = new XElement("Root",  
    from keyValue in dict  
    select new XElement(keyValue.Key, keyValue.Value)  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="05a6f-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="05a6f-107">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="05a6f-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="05a6f-108">Example</span></span>  
 <span data-ttu-id="05a6f-109">Der folgende Code erstellt aus dem XML-Code ein Wörterbuch:</span><span class="sxs-lookup"><span data-stu-id="05a6f-109">The following code creates a dictionary from XML.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "Value1"),  
    new XElement("Child2", "Value2"),  
    new XElement("Child3", "Value3"),  
    new XElement("Child4", "Value4")  
);  
  
Dictionary<string, string> dict = new Dictionary<string, string>();  
foreach (XElement el in root.Elements())  
    dict.Add(el.Name.LocalName, el.Value);  
foreach (string str in dict.Keys)  
    Console.WriteLine("{0}:{1}", str, dict[str]);  
```  
  
 <span data-ttu-id="05a6f-110">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="05a6f-110">This code produces the following output:</span></span>  
  
```output  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
