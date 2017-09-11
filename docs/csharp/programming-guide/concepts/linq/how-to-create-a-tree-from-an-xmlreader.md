---
title: 'Vorgehensweise: Erstellen einer Struktur aus XmlReader (C#)'
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
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 61685e93e6886b3101d6b30c7f8eb04d026ea55a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a><span data-ttu-id="718f2-102">Vorgehensweise: Erstellen einer Struktur aus XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="718f2-102">How to: Create a Tree from an XmlReader (C#)</span></span>
<span data-ttu-id="718f2-103">In diesem Thema wird erläutert, wie Sie direkt aus einem <xref:System.Xml.XmlReader> eine XML-Struktur erstellen können.</span><span class="sxs-lookup"><span data-stu-id="718f2-103">This topic shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="718f2-104">Um aus einem <xref:System.Xml.Linq.XElement> ein <xref:System.Xml.XmlReader> zu erstellen, müssen Sie den <xref:System.Xml.XmlReader> in einem Elementknoten positionieren.</span><span class="sxs-lookup"><span data-stu-id="718f2-104">To create an <xref:System.Xml.Linq.XElement> from an <xref:System.Xml.XmlReader>, you must position the <xref:System.Xml.XmlReader> on an element node.</span></span> <span data-ttu-id="718f2-105">Der <xref:System.Xml.XmlReader> überspringt Kommentare und Verarbeitungsanweisungen, aber wenn der <xref:System.Xml.XmlReader> in einem Textknoten positioniert wird, wird eine Fehlermeldung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="718f2-105">The <xref:System.Xml.XmlReader> will skip comments and processing instructions, but if the <xref:System.Xml.XmlReader> is positioned on a text node, an error will be thrown.</span></span> <span data-ttu-id="718f2-106">Diese Fehlermeldung können Sie vermeiden, indem Sie den <xref:System.Xml.XmlReader> immer in einem Element platzieren, bevor Sie ihn als Grundlage für das Erstellen einer XML-Struktur verwenden aus der <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="718f2-106">To avoid such errors, always position the <xref:System.Xml.XmlReader> on an element before you create an XML tree from the <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="718f2-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="718f2-107">Example</span></span>  
 <span data-ttu-id="718f2-108">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="718f2-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="718f2-109">Der folgende Code erstellt ein `T:System.Xml.XmlReader`-Objekt und liest dann so lange Knoten, bis er den ersten Elementknoten findet.</span><span class="sxs-lookup"><span data-stu-id="718f2-109">The following code creates an `T:System.Xml.XmlReader` object, and then reads nodes until it finds the first element node.</span></span> <span data-ttu-id="718f2-110">Daraufhin lädt er das <xref:System.Xml.Linq.XElement>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="718f2-110">It then loads the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```csharp  
XmlReader r = XmlReader.Create("books.xml");  
while (r.NodeType != XmlNodeType.Element)  
    r.Read();  
XElement e = XElement.Load(r);  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="718f2-111">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="718f2-111">This example produces the following output:</span></span>  
  
```xml  
<Catalog>  
   <Book id="bk101">  
      <Author>Garghentini, Davide</Author>  
      <Title>XML Developer's Guide</Title>  
      <Genre>Computer</Genre>  
      <Price>44.95</Price>  
      <PublishDate>2000-10-01</PublishDate>  
      <Description>An in-depth look at creating applications   
      with XML.</Description>  
   </Book>  
   <Book id="bk102">  
      <Author>Garcia, Debra</Author>  
      <Title>Midnight Rain</Title>  
      <Genre>Fantasy</Genre>  
      <Price>5.95</Price>  
      <PublishDate>2000-12-16</PublishDate>  
      <Description>A former architect battles corporate zombies,   
      an evil sorceress, and her own childhood to become queen   
      of the world.</Description>  
   </Book>  
</Catalog>  
```  
  
## <a name="see-also"></a><span data-ttu-id="718f2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="718f2-112">See Also</span></span>  
 [<span data-ttu-id="718f2-113">Analysieren von XML (C#)</span><span class="sxs-lookup"><span data-stu-id="718f2-113">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)

