---
title: 'Vorgehensweise: Suchen eines Attributs eines übergeordneten Elements (XPath-LINQ to XML) (C#)'
description: Erfahren Sie, wie Sie nach einem Attribut eines übergeordneten Elements suchen. Hier finden Sie ein Codebeispiel, das ein XML-Beispieldokument verwendet.
ms.date: 07/20/2015
ms.assetid: dbef9d89-a5c4-431f-80cc-7a2ebf323f86
ms.openlocfilehash: 03344bb66f617970d9598c91366eb7d69514397a
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "87303295"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a><span data-ttu-id="ef69c-104">Vorgehensweise: Suchen eines Attributs eines übergeordneten Elements (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="ef69c-104">How to find an attribute of the parent (XPath-LINQ to XML) (C#)</span></span>

<span data-ttu-id="ef69c-105">In diesem Thema wird gezeigt, wie Sie zum übergeordneten Element navigieren und nach einem Attribut dieses übergeordneten Elements suchen können.</span><span class="sxs-lookup"><span data-stu-id="ef69c-105">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>

<span data-ttu-id="ef69c-106">Der XPath-Ausdruck lautet:</span><span class="sxs-lookup"><span data-stu-id="ef69c-106">The XPath expression is:</span></span>

`../@id`

## <a name="example"></a><span data-ttu-id="ef69c-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ef69c-107">Example</span></span>

<span data-ttu-id="ef69c-108">Dieses Beispiel sucht zuerst nach einem `Author`-Element.</span><span class="sxs-lookup"><span data-stu-id="ef69c-108">This example first finds an `Author` element.</span></span> <span data-ttu-id="ef69c-109">Anschließend wird das `id`-Attribut des übergeordneten Elements ermittelt.</span><span class="sxs-lookup"><span data-stu-id="ef69c-109">It then finds the `id` attribute of the parent element.</span></span>

<span data-ttu-id="ef69c-110">In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="ef69c-110">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).</span></span>

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

<span data-ttu-id="ef69c-111">Dieses Beispiel erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ef69c-111">This example produces the following output:</span></span>

```output
Results are identical
id="bk101"
```
