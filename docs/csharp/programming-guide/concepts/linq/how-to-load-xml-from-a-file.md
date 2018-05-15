---
title: 'Vorgehensweise: Laden von XML aus einer Datei (C#)'
ms.date: 07/20/2015
ms.assetid: 3ed38487-8028-4209-9872-c8dce0ed4dfe
ms.openlocfilehash: b276359c9bfd0a45775cf5ecf1e821f776825309
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-load-xml-from-a-file-c"></a><span data-ttu-id="8708e-102">Vorgehensweise: Laden von XML aus einer Datei (C#)</span><span class="sxs-lookup"><span data-stu-id="8708e-102">How to: Load XML from a File (C#)</span></span>
<span data-ttu-id="8708e-103">In diesem Thema wird gezeigt, wie mit der <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>-Methode XML aus einem URI geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8708e-103">This topic shows how to load XML from a URI by using the <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8708e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8708e-104">Example</span></span>  
 <span data-ttu-id="8708e-105">Im folgenden Beispiel wird gezeigt, wie ein XML-Dokument aus einer Datei geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="8708e-105">The following example shows how to load an XML document from a file.</span></span> <span data-ttu-id="8708e-106">Dabei wird <legacyBold>books.xml</legacyBold> geladen und die XML-Struktur auf der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="8708e-106">The following example loads books.xml and outputs the XML tree to the console.</span></span>  
  
 <span data-ttu-id="8708e-107">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="8708e-107">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XElement booksFromFile = XElement.Load(@"books.xml");  
Console.WriteLine(booksFromFile);  
```  
  
 <span data-ttu-id="8708e-108">Dieser Code erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="8708e-108">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8708e-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8708e-109">See Also</span></span>  
 [<span data-ttu-id="8708e-110">Analysieren von XML (C#)</span><span class="sxs-lookup"><span data-stu-id="8708e-110">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
