---
title: Voratomisierung von XName-Objekten (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 06ea104b-f44c-4bb2-9c34-889ae025c80d
ms.openlocfilehash: a87a37c5fe2fc29ca980c77d9c775b2b1e909cc1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353118"
---
# <a name="pre-atomization-of-xname-objects-linq-to-xml-visual-basic"></a><span data-ttu-id="ef0de-102">Pre-Atomization of XName Objects (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef0de-102">Pre-Atomization of XName Objects (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="ef0de-103">Eine Möglichkeit zum Verbessern der Leistung in LINQ to XML ist, <xref:System.Xml.Linq.XName>-Objekte vorab zu atomisieren.</span><span class="sxs-lookup"><span data-stu-id="ef0de-103">One way to improve performance in LINQ to XML is to pre-atomize <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="ef0de-104">Voratomisierung bedeutet, dass einem <xref:System.Xml.Linq.XName>-Objekt eine Zeichenfolge zugeordnet wird, bevor Sie mithilfe der Konstruktoren der <xref:System.Xml.Linq.XElement>-Klasse und der <xref:System.Xml.Linq.XAttribute>-Klasse die XML-Struktur erstellen.</span><span class="sxs-lookup"><span data-stu-id="ef0de-104">Pre-atomization means that you assign a string to an <xref:System.Xml.Linq.XName> object before you create the XML tree by using the constructors of the <xref:System.Xml.Linq.XElement> and  <xref:System.Xml.Linq.XAttribute> classes.</span></span> <span data-ttu-id="ef0de-105">Anschließend wird anstelle der Übergabe einer Zeichenfolge an den Konstruktor, der die implizite Konvertierung von Zeichenfolge in <xref:System.Xml.Linq.XName> verwenden würde, das initialisierte <xref:System.Xml.Linq.XName>-Objekt übergeben.</span><span class="sxs-lookup"><span data-stu-id="ef0de-105">Then, instead of passing a string to the constructor, which would use the implicit conversion from string to <xref:System.Xml.Linq.XName>, you pass the initialized <xref:System.Xml.Linq.XName> object.</span></span>  
  
 <span data-ttu-id="ef0de-106">Dies verbessert die Leistung beim Erstellen von großen XML-Strukturen, in denen bestimmte Namen wiederholt werden.</span><span class="sxs-lookup"><span data-stu-id="ef0de-106">This improves performance when you create a large XML tree in which specific names are repeated.</span></span> <span data-ttu-id="ef0de-107">Deklarieren und initialisieren Sie hierzu <xref:System.Xml.Linq.XName>-Objekte, bevor Sie die XML-Struktur erstellen, und verwenden Sie dann die <xref:System.Xml.Linq.XName>-Objekte, anstatt für die Element- und Attributnamen Zeichenfolgen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="ef0de-107">To do this, you declare and initialize <xref:System.Xml.Linq.XName> objects before you construct the XML tree, and then use the <xref:System.Xml.Linq.XName> objects instead of specifying strings for the element and attribute names.</span></span> <span data-ttu-id="ef0de-108">Mit dieser Vorgehensweise können beim Erstellen einer großen Anzahl von Elementen (oder Attributen) wesentliche Leistungsverbesserungen erzielt werden.</span><span class="sxs-lookup"><span data-stu-id="ef0de-108">This technique can yield significant performance gains if you are creating a large number of elements (or attributes) with the same name.</span></span>  
  
 <span data-ttu-id="ef0de-109">Sie sollten Voratomisierung innerhalb Ihres Szenarios testen, um eine Entscheidung über die Anwendbarkeit dieses Verfahrens zu treffen.</span><span class="sxs-lookup"><span data-stu-id="ef0de-109">You should test pre-atomization with your scenario to decide if you should use it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ef0de-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef0de-110">Example</span></span>  
 <span data-ttu-id="ef0de-111">Dies wird im folgenden Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="ef0de-111">The following example demonstrates this.</span></span>  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 <span data-ttu-id="ef0de-112">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ef0de-112">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Data ID="1">4,100,000</Data>  
  <Data ID="2">3,700,000</Data>  
  <Data ID="3">1,150,000</Data>  
</Root>  
```  
  
 <span data-ttu-id="ef0de-113">Im folgenden Beispiel wird dieselbe Vorgehensweise für ein XML-Dokument in einem Namespace erläutert.</span><span class="sxs-lookup"><span data-stu-id="ef0de-113">The following example shows the same technique where the XML document is in a namespace:</span></span>  
  
```vb  
Dim aw As XNamespace = "http://www.adventure-works.com"  
Dim Root__1 As XName = aw + "Root"  
Dim Data As XName = aw + "Data"  
Dim ID As XName = "ID"  
  
Dim root__2 As New XElement(Root__1, New XAttribute(XNamespace.Xmlns + "aw", aw), New XElement(Data, New XAttribute(ID, "1"), "4,100,000"), New XElement(Data, New XAttribute(ID, "2"), "3,700,000"), New XElement(Data, New XAttribute(ID, "3"), "1,150,000"))  
  
Console.WriteLine(root__2)  
```  
  
 <span data-ttu-id="ef0de-114">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ef0de-114">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Data ID="1">4,100,000</aw:Data>  
  <aw:Data ID="2">3,700,000</aw:Data>  
  <aw:Data ID="3">1,150,000</aw:Data>  
</aw:Root>  
```  
  
 <span data-ttu-id="ef0de-115">Das folgende Beispiel entspricht eher realen Bedingungen.</span><span class="sxs-lookup"><span data-stu-id="ef0de-115">The following example is more similar to what you will likely encounter in the real world.</span></span> <span data-ttu-id="ef0de-116">In diesem Beispiel wird der Inhalt des Elements durch eine Abfrage bereitgestellt:</span><span class="sxs-lookup"><span data-stu-id="ef0de-116">In this example, the content of the element is supplied by a query:</span></span>  
  
```vb  
Dim Root__1 As XName = "Root"  
Dim Data As XName = "Data"  
Dim ID As XName = "ID"  
  
Dim t1 As DateTime = DateTime.Now  
Dim root__2 As New XElement(Root__1, From i In System.Linq.Enumerable.Range(1, 100000)New XElement(Data, New XAttribute(ID, i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
 <span data-ttu-id="ef0de-117">Im vorherigen Beispiel wird eine bessere Leistung als im folgenden Beispiel erzielt, in dem Namen nicht voratomisiert werden:</span><span class="sxs-lookup"><span data-stu-id="ef0de-117">The previous example performs better than the following example, in which names are not pre-atomized:</span></span>  
  
```vb  
Dim t1 As DateTime = DateTime.Now  
Dim root As New XElement("Root", From i In System.Linq.Enumerable.Range(1, 100000)New XElement("Data", New XAttribute("ID", i), i * 5))  
Dim t2 As DateTime = DateTime.Now  
  
Console.WriteLine("Time to construct:{0}", t2 - t1)  
```  
  
## <a name="see-also"></a><span data-ttu-id="ef0de-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef0de-118">See also</span></span>

- [<span data-ttu-id="ef0de-119">Performance (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef0de-119">Performance (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)
- [<span data-ttu-id="ef0de-120">Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ef0de-120">Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/atomized-xname-and-xnamespace-objects-linq-to-xml.md)
