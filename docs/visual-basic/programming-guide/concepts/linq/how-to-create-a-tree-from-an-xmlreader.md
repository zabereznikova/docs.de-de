---
title: 'Vorgehensweise: Erstellen einer Struktur aus XmlReader (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4ceae7c2bee85e7b368322c8ba195dea9feff672
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a>Vorgehensweise: Erstellen einer Struktur aus XmlReader (Visual Basic)
In diesem Thema wird erläutert, wie Sie direkt aus einem <xref:System.Xml.XmlReader> eine XML-Struktur erstellen können. Um aus einem <xref:System.Xml.Linq.XElement> ein <xref:System.Xml.XmlReader> zu erstellen, müssen Sie den <xref:System.Xml.XmlReader> in einem Elementknoten positionieren. Der <xref:System.Xml.XmlReader> überspringt Kommentare und Verarbeitungsanweisungen, aber wenn der <xref:System.Xml.XmlReader> in einem Textknoten positioniert wird, wird eine Fehlermeldung ausgegeben. Diese Fehlermeldung können Sie vermeiden, indem Sie den <xref:System.Xml.XmlReader> immer in einem Element platzieren, bevor Sie ihn als Grundlage für das Erstellen einer XML-Struktur verwenden aus der <xref:System.Xml.XmlReader>.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird das folgende XML-Dokument verwendet: [Beispiel-XML-Datei: Bücher (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
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
  
## <a name="see-also"></a>Siehe auch  
 [Analysieren von XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
