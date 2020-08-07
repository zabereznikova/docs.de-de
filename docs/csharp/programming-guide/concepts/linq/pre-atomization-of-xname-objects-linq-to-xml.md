---
title: Voratomisierung von XName-Objekten (LINQ to XML) (C#)
description: Erfahren Sie mehr über die Voratomisierung von XName-Objekten. Die Voratomisierung von Objekten verbessert die Leistung beim Erstellen von großen XML-Strukturen, in denen bestimmte Namen wiederholt werden.
ms.date: 07/20/2015
ms.assetid: e84fbbe7-f072-4771-bfbb-059d18e1ad15
ms.openlocfilehash: 4d217f6c78dc5d83ce424fb3ba95785f2dac0b73
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302827"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-c"></a><span data-ttu-id="b3e9b-104">Voratomisierung von XName-Objekten (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b3e9b-104">Pre-Atomization of XName Objects (LINQ to XML) (C#)</span></span>
<span data-ttu-id="b3e9b-105">Eine Möglichkeit zum Verbessern der Leistung in LINQ to XML ist, <xref:System.Xml.Linq.XName>-Objekte vorab zu atomisieren.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-105">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="b3e9b-106">Voratomisierung bedeutet, dass einem <xref:System.Xml.Linq.XName>-Objekt eine Zeichenfolge zugeordnet wird, bevor Sie mithilfe der Konstruktoren der <xref:System.Xml.Linq.XElement>-Klasse und der <xref:System.Xml.Linq.XAttribute>-Klasse die XML-Struktur erstellen.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-106">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and  <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="b3e9b-107">Anschließend wird anstelle der Übergabe einer Zeichenfolge an den Konstruktor, der die implizite Konvertierung von Zeichenfolge in <xref:System.Xml.Linq.XName> verwenden würde, das initialisierte <xref:System.Xml.Linq.XName>-Objekt übergeben.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-107">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>  
  
 <span data-ttu-id="b3e9b-108">Dies verbessert die Leistung beim Erstellen von großen XML-Strukturen, in denen bestimmte Namen wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-108">This improves performance when you create a large XML tree in which specific names are repeated.</span></span> <span data-ttu-id="b3e9b-109">Deklarieren und initialisieren Sie hierzu <xref:System.Xml.Linq.XName>-Objekte, bevor Sie die XML-Struktur erstellen, und verwenden Sie dann die <xref:System.Xml.Linq.XName>-Objekte, anstatt für die Element- und Attributnamen Zeichenfolgen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-109">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="b3e9b-110">Mit dieser Vorgehensweise können beim Erstellen einer großen Anzahl von Elementen (oder Attributen) wesentliche Leistungsverbesserungen erzielt werden.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-110">This technique can yield significant performance gains if you are creating a large number of elements (or attributes) with the same name.</span></span>  
  
 <span data-ttu-id="b3e9b-111">Sie sollten Voratomisierung innerhalb Ihres Szenarios testen, um eine Entscheidung über die Anwendbarkeit dieses Verfahrens zu treffen.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-111">You should test pre-atomization with your scenario to decide if you should use it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b3e9b-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3e9b-112">Example</span></span>  
 <span data-ttu-id="b3e9b-113">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b3e9b-113">The following example demonstrates this.</span></span>  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="b3e9b-114">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="b3e9b-114">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 <span data-ttu-id="b3e9b-115">Im folgenden Beispiel wird dieselbe Vorgehensweise für ein XML-Dokument in einem Namespace erläutert.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-115">The following example shows the same technique where the XML document is in a namespace:</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XName Root = aw + "Root";  
XName Data = aw + "Data";  
XName ID = "ID";  
  
XElement root = new XElement(Root,  
    new XAttribute(XNamespace.Xmlns + "aw", aw),  
    new XElement(Data,  
        new XAttribute(ID, "1"),  
        "4,100,000"),  
    new XElement(Data,  
        new XAttribute(ID, "2"),  
        "3,700,000"),  
    new XElement(Data,  
        new XAttribute(ID, "3"),  
        "1,150,000")  
);  
  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="b3e9b-116">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="b3e9b-116">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 <span data-ttu-id="b3e9b-117">Das folgende Beispiel entspricht eher realen Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="b3e9b-117">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="b3e9b-118">In diesem Beispiel wird der Inhalt des Elements durch eine Abfrage bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="b3e9b-118">In this example, the content of the element is supplied by a query:</span></span>  
  
```csharp  
XName Root = "Root";  
XName Data = "Data";  
XName ID = "ID";  
  
DateTime t1 = DateTime.Now;  
XElement root = new XElement(Root,  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement(Data,  
        new XAttribute(ID, i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
 <span data-ttu-id="b3e9b-119">Im vorherigen Beispiel wird eine bessere Leistung als im folgenden Beispiel erzielt, in dem Namen nicht voratomisiert werden:</span><span class="sxs-lookup"><span data-stu-id="b3e9b-119">The previous example performs better than the following example, in which names are not pre-atomized:</span></span>  
  
```csharp  
DateTime t1 = DateTime.Now;  
XElement root = new XElement("Root",  
    from i in System.Linq.Enumerable.Range(1, 100000)  
    select new XElement("Data",  
        new XAttribute("ID", i),  
        i * 5)  
);  
DateTime t2 = DateTime.Now;  
  
Console.WriteLine("Time to construct:{0}", t2 - t1);  
```  
  
## <a name="see-also"></a><span data-ttu-id="b3e9b-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b3e9b-120">See also</span></span>

- [<span data-ttu-id="b3e9b-121">Atomized XName and XNamespace Objects (LINQ to XML) (C#) (Atomisierte XName- und XNamespace-Objekte (LINQ to XML) (C#))</span><span class="sxs-lookup"><span data-stu-id="b3e9b-121">Atomized XName and XNamespace Objects (LINQ to XML) (C#)</span></span>](./atomized-xname-and-xnamespace-objects-linq-to-xml.md)
