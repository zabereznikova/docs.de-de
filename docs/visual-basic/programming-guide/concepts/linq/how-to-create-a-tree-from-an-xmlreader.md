---
title: 'Gewusst wie: Erstellen einer Struktur aus XmlReader (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 6de683d8-177d-402b-b0de-d0539f1ce5d8
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a8dff4e518d8850b4050389e5677ac81ecd1e074
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-a-tree-from-an-xmlreader-visual-basic"></a>Gewusst wie: Erstellen einer Struktur aus XmlReader (Visual Basic)
In diesem Thema veranschaulicht, wie eine XML-Struktur direkt in eine <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> erstellen Erstellen einer <xref:System.Xml.Linq.XElement>aus einer <xref:System.Xml.XmlReader>, müssen Sie Positionieren der <xref:System.Xml.XmlReader>auf einem Elementknoten.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> </xref:System.Xml.Linq.XElement> Die <xref:System.Xml.XmlReader>überspringt Kommentare und verarbeitungsanweisungen, aber wenn die <xref:System.Xml.XmlReader>befindet sich in einem Textknoten kann ein Fehler ausgelöst.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> Um solche Fehler zu vermeiden, immer die positionieren Sie <xref:System.Xml.XmlReader>auf ein Element vor dem Erstellen einer XML-Struktur aus der <xref:System.Xml.XmlReader>.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader>  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die folgende XML-Dokument: [XML-Beispieldatei: Bücher (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).  
  
 Der folgende Code erstellt ein `T:System.Xml.XmlReader`-Objekt und liest dann so lange Knoten, bis er den ersten Elementknoten findet. Daraufhin lädt er das <xref:System.Xml.Linq.XElement>Objekt.</xref:System.Xml.Linq.XElement>  
  
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
