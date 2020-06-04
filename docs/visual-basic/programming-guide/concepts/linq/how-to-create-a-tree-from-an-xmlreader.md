---
title: 'Vorgehensweise: Erstellen einer Struktur aus einem XmlReader'
ms.date: 07/20/2015
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
ms.openlocfilehash: 25c15ff08563b12b26041a536dfbca1c9cce260a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414607"
---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a><span data-ttu-id="eb3df-102">Vorgehensweise: Erstellen einer Struktur aus einem XmlReader (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb3df-102">How to: Create a Tree from an XmlReader (Visual Basic)</span></span>

<span data-ttu-id="eb3df-103">In diesem Thema wird erläutert, wie Sie direkt aus einem <xref:System.Xml.XmlReader> eine XML-Struktur erstellen können.</span><span class="sxs-lookup"><span data-stu-id="eb3df-103">This topic shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="eb3df-104">Um aus einem <xref:System.Xml.Linq.XElement> ein <xref:System.Xml.XmlReader> zu erstellen, müssen Sie den <xref:System.Xml.XmlReader> in einem Elementknoten positionieren.</span><span class="sxs-lookup"><span data-stu-id="eb3df-104">To create an <xref:System.Xml.Linq.XElement> from an <xref:System.Xml.XmlReader>, you must position the <xref:System.Xml.XmlReader> on an element node.</span></span> <span data-ttu-id="eb3df-105">Der <xref:System.Xml.XmlReader> überspringt Kommentare und Verarbeitungsanweisungen, aber wenn der <xref:System.Xml.XmlReader> in einem Textknoten positioniert wird, wird eine Fehlermeldung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="eb3df-105">The <xref:System.Xml.XmlReader> will skip comments and processing instructions, but if the <xref:System.Xml.XmlReader> is positioned on a text node, an error will be thrown.</span></span> <span data-ttu-id="eb3df-106">Diese Fehlermeldung können Sie vermeiden, indem Sie den <xref:System.Xml.XmlReader> immer in einem Element platzieren, bevor Sie ihn als Grundlage für das Erstellen einer XML-Struktur verwenden aus der <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="eb3df-106">To avoid such errors, always position the <xref:System.Xml.XmlReader> on an element before you create an XML tree from the <xref:System.Xml.XmlReader>.</span></span>

## <a name="example"></a><span data-ttu-id="eb3df-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eb3df-107">Example</span></span>

<span data-ttu-id="eb3df-108">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="eb3df-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](sample-xml-file-books-linq-to-xml.md).</span></span>

<span data-ttu-id="eb3df-109">Der folgende Code erstellt ein `T:System.Xml.XmlReader`-Objekt und liest dann so lange Knoten, bis er den ersten Elementknoten findet.</span><span class="sxs-lookup"><span data-stu-id="eb3df-109">The following code creates an `T:System.Xml.XmlReader` object, and then reads nodes until it finds the first element node.</span></span> <span data-ttu-id="eb3df-110">Daraufhin lädt er das <xref:System.Xml.Linq.XElement>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="eb3df-110">It then loads the <xref:System.Xml.Linq.XElement> object.</span></span>

```vb
Dim r As XmlReader = XmlReader.Create("books.xml")
Do While r.NodeType <> XmlNodeType.Element
    r.Read()
Loop
Dim e As XElement = XElement.Load(r)
Console.WriteLine(e)
```

<span data-ttu-id="eb3df-111">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="eb3df-111">This example produces the following output:</span></span>

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

## <a name="see-also"></a><span data-ttu-id="eb3df-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eb3df-112">See also</span></span>

- [<span data-ttu-id="eb3df-113">XML-Datei (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="eb3df-113">Parsing XML (Visual Basic)</span></span>](parsing-xml.md)
