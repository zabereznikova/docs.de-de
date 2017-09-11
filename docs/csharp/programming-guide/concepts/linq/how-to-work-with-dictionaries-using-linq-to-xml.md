---
title: "Vorgehensweise: Arbeiten mit Wörterbüchern unter Verwendung von LINQ to XML (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 57bcefe3-8433-4d3b-935a-511c9bcbdfa8
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 66668c14c472f68dd3da365bd7c7cbc64ccd4365
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-c"></a><span data-ttu-id="93a74-102">Vorgehensweise: Arbeiten mit Wörterbüchern unter Verwendung von LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="93a74-102">How to: Work with Dictionaries Using LINQ to XML (C#)</span></span>
<span data-ttu-id="93a74-103">Es ist häufig sinnvoll, verschiedene Datenstrukturen in XML und aus XML in andere Datenstrukturen umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="93a74-103">It is often convenient to convert varieties of data structures to XML, and XML back to other data structures.</span></span> <span data-ttu-id="93a74-104">In diesem Thema wird eine konkrete Implementierung dieser allgemeinen Herangehensweise gezeigt, bei der ein <xref:System.Collections.Generic.Dictionary%602> in XML umgewandelt und dann wieder zurückgewandelt wird.</span><span class="sxs-lookup"><span data-stu-id="93a74-104">This topic shows a specific implementation of this general approach by converting a <xref:System.Collections.Generic.Dictionary%602> to XML and back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93a74-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93a74-105">Example</span></span>  
 <span data-ttu-id="93a74-106">In diesem Beispiel kommt eine Form einer funktionalen Konstruktion zum Einsatz, bei der eine Abfrage neue <xref:System.Xml.Linq.XElement>-Objekte projiziert, woraufhin die sich dabei ergebende Auflistung als Argument an den Konstruktor des <xref:System.Xml.Linq.XElement>-Objekts übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="93a74-106">This example uses a form of functional construction in which a query projects new <xref:System.Xml.Linq.XElement> objects, and the resulting collection is passed as an argument to the constructor of the Root <xref:System.Xml.Linq.XElement> object.</span></span>  
  
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
  
 <span data-ttu-id="93a74-107">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="93a74-107">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="93a74-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="93a74-108">Example</span></span>  
 <span data-ttu-id="93a74-109">Der folgende Code erstellt aus dem XML-Code ein Wörterbuch:</span><span class="sxs-lookup"><span data-stu-id="93a74-109">The following code creates a dictionary from XML.</span></span>  
  
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
  
 <span data-ttu-id="93a74-110">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="93a74-110">This code produces the following output:</span></span>  
  
```  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
  
## <a name="see-also"></a><span data-ttu-id="93a74-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93a74-111">See Also</span></span>  
 [<span data-ttu-id="93a74-112">Projektionen und Transformationen (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="93a74-112">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)

