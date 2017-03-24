---
title: Beibehaltung von Leerraum beim Laden oder analysieren XML2 | Microsoft-Dokumentation
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
ms.assetid: ef6518e0-2c8d-462c-8b92-a16e9dc737ad
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
ms.openlocfilehash: 39e4270acc0e9a9df5c3855f8c087f41d9612197
ms.lasthandoff: 03/13/2017

---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a>Beibehalten von Leerzeichen beim Laden oder Parsen von XML
In diesem Thema wird beschrieben, wie das Leerraumverhalten von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] gesteuert werden kann.  
  
 Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert. Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten. Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert. Sie möchten nicht, dass diese Einzüge irgendwie geändert werden. In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.  
  
 In diesem Thema wird das Leerraumverhalten von Methoden beschrieben, die XML-Strukturen auffüllen. Informationen zum Steuern des Leerraumverhaltens beim Serialisieren von XML-Strukturen finden Sie unter [beibehalten Leerzeichen beim Serialisieren von](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a>Verhalten von Methoden, die XML-Strukturen auffüllen  
 Die folgenden Methoden in der <xref:System.Xml.Linq.XElement>und <xref:System.Xml.Linq.XDocument>Klassen eine XML-Struktur aufzufüllen.</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> Sie können eine XML-Struktur aus einer Datei, Auffüllen einer <xref:System.IO.TextReader>, <xref:System.Xml.XmlReader>, oder eine Zeichenfolge:</xref:System.Xml.XmlReader> </xref:System.IO.TextReader>  
  
-   <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>  
  
 Wenn die Methode nicht <xref:System.Xml.Linq.LoadOptions>als Argument wird die Methode nicht signifikanten Leerraum nicht beibehalten.</xref:System.Xml.Linq.LoadOptions>  
  
 In den meisten Fällen, wenn die Methode akzeptiert <xref:System.Xml.Linq.LoadOptions>als Argument können Sie optional nicht signifikanten Leerraum als Textknoten in der XML-Struktur erhalten.</xref:System.Xml.Linq.LoadOptions> Allerdings, wenn die Methode lädt das XML aus einer <xref:System.Xml.XmlReader>, die <xref:System.Xml.XmlReader>bestimmt, ob Leerraum oder nicht beibehalten wird.</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader> Festlegen von <xref:System.Xml.Linq.LoadOptions>hat keine Auswirkung.</xref:System.Xml.Linq.LoadOptions>  
  
 Mit diesen Methoden, sofern Leerraum beibehalten wird nicht signifikanter Leerraum eingefügt wird die XML-Struktur als <xref:System.Xml.Linq.XText>Knoten.</xref:System.Xml.Linq.XText> Wenn Leerraum nicht beibehalten wird, erfolgt keine Einfügung von Textknoten.  
  
 Sie können eine XML-Struktur erstellen, mit einer <xref:System.Xml.XmlWriter>.</xref:System.Xml.XmlWriter> Knoten, die geschrieben werden die <xref:System.Xml.XmlWriter>werden in der Struktur aufgefüllt.</xref:System.Xml.XmlWriter> Wenn Sie jedoch eine XML-Struktur mit dieser Methode erstellen, bleiben alle Knoten unabhängig davon erhalten, ob der Knoten Leerraum ist und ob er signifikant ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Analysieren von XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
