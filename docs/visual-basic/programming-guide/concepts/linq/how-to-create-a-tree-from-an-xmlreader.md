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
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a>Vorgehensweise: Erstellen einer Struktur aus einem XmlReader (Visual Basic)

In diesem Thema wird erläutert, wie Sie direkt aus einem <xref:System.Xml.XmlReader> eine XML-Struktur erstellen können. Um aus einem <xref:System.Xml.Linq.XElement> ein <xref:System.Xml.XmlReader> zu erstellen, müssen Sie den <xref:System.Xml.XmlReader> in einem Elementknoten positionieren. Der <xref:System.Xml.XmlReader> überspringt Kommentare und Verarbeitungsanweisungen, aber wenn der <xref:System.Xml.XmlReader> in einem Textknoten positioniert wird, wird eine Fehlermeldung ausgegeben. Diese Fehlermeldung können Sie vermeiden, indem Sie den <xref:System.Xml.XmlReader> immer in einem Element platzieren, bevor Sie ihn als Grundlage für das Erstellen einer XML-Struktur verwenden aus der <xref:System.Xml.XmlReader>.

## <a name="example"></a>Beispiel

In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](sample-xml-file-books-linq-to-xml.md).

Der folgende Code erstellt ein `T:System.Xml.XmlReader`-Objekt und liest dann so lange Knoten, bis er den ersten Elementknoten findet. Daraufhin lädt er das <xref:System.Xml.Linq.XElement>-Objekt.

```vb
Dim r As XmlReader = XmlReader.Create("books.xml")
Do While r.NodeType <> XmlNodeType.Element
    r.Read()
Loop
Dim e As XElement = XElement.Load(r)
Console.WriteLine(e)
```

Dieses Beispiel erzeugt die folgende Ausgabe:

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

## <a name="see-also"></a>Weitere Informationen

- [XML-Datei (Visual Basic)](parsing-xml.md)
