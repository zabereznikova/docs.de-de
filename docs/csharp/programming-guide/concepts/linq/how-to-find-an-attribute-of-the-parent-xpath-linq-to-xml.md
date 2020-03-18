---
title: 'Vorgehensweise: Suchen eines Attributs eines übergeordneten Elements (XPath-LINQ to XML) (C#)'
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: bfe7554a5c767adde5e7170c8e1ea0537155f6df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141173"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="370ae-102">Vorgehensweise: Suchen eines Attributs eines übergeordneten Elements (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="370ae-102">How to find an attribute of the parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="370ae-103">In diesem Thema wird gezeigt, wie Sie zum übergeordneten Element navigieren und nach einem Attribut dieses übergeordneten Elements suchen können.</span><span class="sxs-lookup"><span data-stu-id="370ae-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="370ae-104">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="370ae-104">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="370ae-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="370ae-105">Example</span></span>

<span data-ttu-id="370ae-106">Dieses Beispiel sucht zuerst nach einem `Author`-Element.</span><span class="sxs-lookup"><span data-stu-id="370ae-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="370ae-107">Anschließend wird das `id`-Attribut des übergeordneten Elements ermittelt.</span><span class="sxs-lookup"><span data-stu-id="370ae-107">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="370ae-108">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="370ae-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>

```csharp
XDocument books = XDocument.Load("Books.xml");

XElement author =
    books
    .Root
    .Element("Book")
    .Element("Author");

// LINQ to XML query
XAttribute att1 =
    author
    .Parent
    .Attribute("id");

// XPath expression
XAttribute att2 = ((IEnumerable)author.XPathEvaluate("../@id")).Cast<XAttribute>().First();

if (att1 == att2)
    Console.WriteLine("Results are identical");
else
    Console.WriteLine("Results differ");
Console.WriteLine(att1);
```

<span data-ttu-id="370ae-109">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="370ae-109">This example produces the following output:</span></span>

```output
Results are identical
id="bk101"
```
