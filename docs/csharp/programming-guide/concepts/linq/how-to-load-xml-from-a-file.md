---
title: 'Vorgehensweise: Laden von XML aus einer Datei (C#)'
ms.date: 07/20/2015
ms.assetid: 3ed38487-8028-4209-9872-c8dce0ed4dfe
ms.openlocfilehash: f57d7a8375d04d1d7eda6d09aef81f42dd3e4b51
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345834"
---
# <a name="how-to-load-xml-from-a-file-c"></a><span data-ttu-id="97fa5-102">Vorgehensweise: Laden von XML aus einer Datei (C#)</span><span class="sxs-lookup"><span data-stu-id="97fa5-102">How to load XML from a file (C#)</span></span>
<span data-ttu-id="97fa5-103">In diesem Thema wird gezeigt, wie mit der <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>-Methode XML aus einem URI geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="97fa5-103">This topic shows how to load XML from a URI by using the <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="97fa5-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="97fa5-104">Example</span></span>  
 <span data-ttu-id="97fa5-105">Im folgenden Beispiel wird gezeigt, wie ein XML-Dokument aus einer Datei geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="97fa5-105">The following example shows how to load an XML document from a file.</span></span> <span data-ttu-id="97fa5-106">Dabei wird <legacyBold>books.xml</legacyBold> geladen und die XML-Struktur auf der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="97fa5-106">The following example loads books.xml and outputs the XML tree to the console.</span></span>  
  
 <span data-ttu-id="97fa5-107">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="97fa5-107">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XElement booksFromFile = XElement.Load(@"books.xml");  
Console.WriteLine(booksFromFile);  
```  
  
 <span data-ttu-id="97fa5-108">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="97fa5-108">This code produces the following output:</span></span>  
  
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
  