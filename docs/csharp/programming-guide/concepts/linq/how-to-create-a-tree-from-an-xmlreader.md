---
title: 'Vorgehensweise: Erstellen einer Struktur aus XmlReader (C#)'
description: Erfahren Sie, wie Sie eine XML-Struktur direkt aus einem XmlReader erstellen. Sehen Sie sich ein Beispiel an, das zeigt, wie ein T:System.Xml.XmlReader-Objekt erstellt wird.
ms.date: 07/20/2015
ms.assetid: 60951c9c-7087-406c-b5bb-c60e58609b21
ms.openlocfilehash: 3801177e664d142652d38748d44eaf3f274239dd
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302658"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-c"></a><span data-ttu-id="3bda8-104">Vorgehensweise: Erstellen einer Struktur aus XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="3bda8-104">How to create a tree from an XmlReader (C#)</span></span>
<span data-ttu-id="3bda8-105">In diesem Thema wird erläutert, wie Sie direkt aus einem <xref:System.Xml.XmlReader> eine XML-Struktur erstellen können.</span><span class="sxs-lookup"><span data-stu-id="3bda8-105">This topic shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="3bda8-106">Um aus einem <xref:System.Xml.Linq.XElement> ein <xref:System.Xml.XmlReader> zu erstellen, müssen Sie den <xref:System.Xml.XmlReader> in einem Elementknoten positionieren.</span><span class="sxs-lookup"><span data-stu-id="3bda8-106">To create an <xref:System.Xml.Linq.XElement> from an <xref:System.Xml.XmlReader>, you must position the <xref:System.Xml.XmlReader> on an element node.</span></span> <span data-ttu-id="3bda8-107">Der <xref:System.Xml.XmlReader> überspringt Kommentare und Verarbeitungsanweisungen, aber wenn der <xref:System.Xml.XmlReader> in einem Textknoten positioniert wird, wird eine Fehlermeldung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="3bda8-107">The <xref:System.Xml.XmlReader> will skip comments and processing instructions, but if the <xref:System.Xml.XmlReader> is positioned on a text node, an error will be thrown.</span></span> <span data-ttu-id="3bda8-108">Diese Fehlermeldung können Sie vermeiden, indem Sie den <xref:System.Xml.XmlReader> immer in einem Element platzieren, bevor Sie ihn als Grundlage für das Erstellen einer XML-Struktur verwenden aus der <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="3bda8-108">To avoid such errors, always position the <xref:System.Xml.XmlReader> on an element before you create an XML tree from the <xref:System.Xml.XmlReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3bda8-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3bda8-109">Example</span></span>  
 <span data-ttu-id="3bda8-110">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3bda8-110">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="3bda8-111">Der folgende Code erstellt ein `T:System.Xml.XmlReader`-Objekt und liest dann so lange Knoten, bis er den ersten Elementknoten findet.</span><span class="sxs-lookup"><span data-stu-id="3bda8-111">The following code creates an `T:System.Xml.XmlReader` object, and then reads nodes until it finds the first element node.</span></span> <span data-ttu-id="3bda8-112">Daraufhin lädt er das <xref:System.Xml.Linq.XElement>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="3bda8-112">It then loads the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```csharp  
XmlReader r = XmlReader.Create("books.xml");  
while (r.NodeType != XmlNodeType.Element)  
    r.Read();  
XElement e = XElement.Load(r);  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="3bda8-113">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3bda8-113">This example produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3bda8-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bda8-114">See also</span></span>

- [<span data-ttu-id="3bda8-115">Analysieren von XML (C#)</span><span class="sxs-lookup"><span data-stu-id="3bda8-115">Parsing XML (C#)</span></span>](how-to-parse-a-string.md)
