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
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-c"></a>Vorgehensweise: Suchen eines Attributs eines übergeordneten Elements (XPath-LINQ to XML) (C#)

In diesem Thema wird gezeigt, wie Sie zum übergeordneten Element navigieren und nach einem Attribut dieses übergeordneten Elements suchen können.

Der XPath-Ausdruck lautet:

`../@id`

## <a name="example"></a>Beispiel

Dieses Beispiel sucht zuerst nach einem `Author`-Element. Anschließend wird das `id`-Attribut des übergeordneten Elements ermittelt.

In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](./sample-xml-file-books-linq-to-xml.md).

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

Dieses Beispiel erzeugt die folgende Ausgabe:

```output
Results are identical
id="bk101"
```
