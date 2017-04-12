---
title: "Ändern von XML-Strukturen (LINQ to XML) (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 4ae511a5-4fc9-4178-9c8e-761357deae3f
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cf605973e68230e9e3e09f0abf6de49635cd5845
ms.lasthandoff: 03/13/2017


---
# <a name="modifying-xml-trees-linq-to-xml-visual-basic"></a>Ändern von XML-Strukturen (LINQ to XML) (Visual Basic)
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] ist ein Speicher im Arbeitsspeicher, der XML-Strukturen speichert. Nach dem Laden oder eine XML-Struktur aus einer Quelle analysieren [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] können Sie diese Struktur in ändern und anschließend serialisieren, möglicherweise in einer Datei speichern oder an einen Remoteserver senden.  
  
 Wenn Sie eine vorhandenen Struktur ändern, verwenden Sie bestimmte Methoden, z. B. <xref:System.Xml.Linq.XContainer.Add%2A>.</xref:System.Xml.Linq.XContainer.Add%2A>  
  
 Es gibt aber auch einen anderen Ansatz, nämlich die Verwendung der funktionalen Konstruktion, um eine neue Struktur mit einer anderen Form zu erzeugen. Je nach Art der Änderungen, die Sie an Ihrer XML-Struktur vornehmen müssen, und je nach Größe der Struktur kann sich dieser Ansatz als robuster und einfacher in der Handhabung erweisen. Das erste Thema in diesem Abschnitt enthält eine Gegenüberstellung dieser beiden Ansätze.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|[Änderung des XML-Baums im Arbeitsspeicher und Funktionale Konstruktion (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/in-memory-xml-tree-modification-vs-functional-construction.md)|Stellt das Ändern einer XML-Struktur im Arbeitsspeicher dem Ändern durch funktionale Konstruktion gegenüber.|  
|[Hinzufügen von Elementen, Attributen und Knoten zu einer XML-Struktur (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/adding-elements-attributes-and-nodes-to-an-xml-tree.md)|Enthält Informationen zum Hinzufügen von Elementen, Attributen oder Knoten zu einer XML-Struktur.|  
|[Ändern von Elementen, Attributen und Knoten in einem XML-Baum](../../../../visual-basic/programming-guide/concepts/linq/modifying-elements-attributes-and-nodes-in-an-xml-tree.md)|Enthält Informationen zum Ändern vorhandener Elemente, Attribute oder Knoten.|  
|[Entfernen von Elementen, Attributen und Knoten aus einer XML-Struktur (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/removing-elements-attributes-and-nodes-from-an-xml-tree.md)|Enthält Informationen zum Entfernen von Elementen, Attributen oder Knoten aus einer XML-Struktur.|  
|[Verwalten von Name/Wert-Paaren (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/maintaining-name-value-pairs.md)|Beschreibt das Verwalten von Anwendungsinformationen, die am besten als Name/Wert-Paare aufbewahrt werden, wie Konfigurationsinformationen oder globale Einstellungen.|  
|[Gewusst wie: Ändern Sie den Namespace für eine ganze XML-Struktur (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-change-the-namespace-for-an-entire-xml-tree.md)|Zeigt, wie eine XML-Struktur aus einem Namespace in einen anderen Namespace verschoben werden kann.|  
  
## <a name="see-also"></a>Siehe auch  
 [Programmierhandbuch (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
