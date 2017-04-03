---
title: Beibehalten von Leerzeichen beim Laden oder Analysieren von XML | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: f3ff58c4-55aa-4fcd-b933-e3a2ee6e706c
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 1b2ec9b5b1bbc343fde5c9527c1e4f4ad7f14796
ms.lasthandoff: 03/13/2017

---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a>Beibehalten von Leerzeichen beim Laden oder Parsen von XML
In diesem Thema wird beschrieben, wie das Leerraumverhalten von [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] gesteuert werden kann.  
  
 Es kommt häufig vor, dass XML mit Einzügen gelesen und dann im Arbeitsspeicher eine XML-Struktur ohne Leerraumtextknoten erstellt wird (Leerräume bleiben also nicht erhalten). Anschließend wird der XML-Code geändert und dann mit Einzügen gespeichert. Wenn Sie den XML-Code mit Formatierung serialisieren, bleibt nur signifikanter Leerraum in der XML-Struktur erhalten. Dies ist das Standardverhalten bei [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
 Aber auch dieses Szenario ist häufig anzutreffen: XML-Code, der bereits absichtlich mit Einzügen versehen wurde, wird gelesen und geändert. Sie möchten nicht, dass diese Einzüge irgendwie geändert werden. In [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie dies erreichen, indem Sie den Leerraum beim Laden oder Analysieren des XML-Codes beibehalten und dann beim Serialisieren des XML-Codes die Formatierung deaktivieren.  
  
 In diesem Thema wird das Leerraumverhalten von Methoden beschrieben, die XML-Strukturen auffüllen. Informationen zum Steuern des Leerraumverhaltens beim Serialisieren von XML-Strukturen finden Sie unter [Beibehalten von Leerzeichen beim Serialisieren](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a>Verhalten von Methoden, die XML-Strukturen auffüllen  
 Die folgenden Methoden der Klassen <xref:System.Xml.Linq.XElement> und <xref:System.Xml.Linq.XDocument> füllen eine XML-Struktur auf. Sie können eine XML-Struktur über eine Datei, eine <xref:System.IO.TextReader>, eine <xref:System.Xml.XmlReader> oder eine Zeichenfolge füllen.  
  
-   <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>  
  
-   <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName>  
  
 Wenn die Methode nicht <xref:System.Xml.Linq.LoadOptions> als Argument akzeptiert, bleibt nicht signifikanter Leerraum nicht erhalten.  
  
 In den meisten Fällen können Sie nicht signifikanten Leerraum optional als Textknoten in der XML-Struktur erhalten, sofern die Methode <xref:System.Xml.Linq.LoadOptions> als Argument akzeptiert. Wenn die Methode den XML-Code aber aus einem <xref:System.Xml.XmlReader> lädt, bestimmt dieser, ob Leerraum beibehalten wird. Das Festlegen von <xref:System.Xml.Linq.LoadOptions> hat keine Auswirkung.  
  
 Bei diesen Methoden wird nicht signifikanter Leerraum als <xref:System.Xml.Linq.XText>-Knoten in die XML-Struktur eingefügt, sofern Leerraum beibehalten wird. Wenn Leerraum nicht beibehalten wird, erfolgt keine Einfügung von Textknoten.  
  
 Sie können eine XML-Struktur mit <xref:System.Xml.XmlWriter> auffüllen. Knoten, die in den <xref:System.Xml.XmlWriter> geschrieben werden, werden in der Struktur aufgefüllt. Wenn Sie jedoch eine XML-Struktur mit dieser Methode erstellen, bleiben alle Knoten unabhängig davon erhalten, ob der Knoten Leerraum ist und ob er signifikant ist.  
  
## <a name="see-also"></a>Siehe auch  
 [Analysieren von XML (C#)](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)
