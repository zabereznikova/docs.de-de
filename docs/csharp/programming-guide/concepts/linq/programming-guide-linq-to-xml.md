---
title: Programmierhandbuch (LINQ to XML) (C#) | Microsoft-Dokumentation
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
ms.assetid: 4b1ffd10-ab81-4a0d-a0ca-e9876478d924
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
ms.openlocfilehash: 5e1e95d92123b2874aace0c36005a8a07a6203fc
ms.lasthandoff: 03/13/2017

---
# <a name="programming-guide-linq-to-xml-c"></a>Programmierhandbuch (LINQ to XML) (C#)
Dieser Abschnitt enthält grundlegende Informationen und Anleitungen zum Programmieren mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].  
  
## <a name="who-should-read-this-documentation"></a>Zielgruppe  
 Diese Dokumentation wendet sich an Entwickler, die bereits über C#-Kenntnisse verfügen und sich mit einigen grundlegenden Aspekten von [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] auskennen.  
  
 Ziel dieser Dokumentation ist es, Entwicklern das Arbeiten mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] zu erleichtern. [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] vereinfacht die XML-Programmierung. und kann auch von Entwicklern verwendet werden, die keine ausgesprochenen Experten auf diesem Gebiet sind.  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] basiert in weiten Teilen auf generischen Klassen. Es ist daher sehr wichtig, dass Sie die Verwendung von generischen Klassen verstehen. Außerdem ist es hilfreich, wenn Sie sich mit Delegaten auskennen, die als parametrisierte Typen deklariert sind. Wenn Sie sich zunächst mit den generischen Klassen von C# vertraut machen möchten, finden Sie entsprechende Informationen unter [Generische Klassen](../../../../csharp/programming-guide/generics/generic-classes.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|[Working with XML Namespaces (C#) (Übersicht der LINQ to XML-Programmierung (C#))](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)|Bietet eine Übersicht über die [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Klassen und detaillierte Informationen zu drei der wichtigsten Klassen: <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute>, und <xref:System.Xml.Linq.XDocument>.|  
|[Creating XML Trees (C#) (Erstellen von XML-Strukturen (C#))](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)|Enthält konzeptuelle und aufgabenbasierte Informationen zum Erstellen von XML-Strukturen. XML-Strukturen können mittels funktionaler Konstruktion oder durch Analysieren von XML-Text aus einer Zeichenfolge oder Datei erstellt werden. Sie können auch <xref:System.Xml.XmlReader> verwenden, um eine XML-Struktur aufzufüllen.|  
|[Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)|Enthält ausführliche Informationen zum Erstellen von XML-Strukturen, die Namespaces verwenden.|  
|[Serializing XML Trees (C#) (Serialisieren von XML-Strukturen (C#))](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)|Beschreibt mehrere Ansätze für das Serialisieren einer XML-Struktur und enthält Hilfestellung bei der Auswahl des richtigen Ansatzes.|  
|[LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)|Enthält eine Auflistung und Beschreibung der [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Achsenmethoden, die Sie kennen müssen, bevor Sie [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]-Abfragen schreiben können.|  
|[Querying XML Trees (C#) (Abfragen von XML-Strukturen (C#))](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)|Enthält allgemeine Beispiele für das Abfragen von XML-Strukturen.|  
|[Modifying XML Trees (LINQ to XML) (C#) (Ändern von XML-Strukturen (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)|Genau wie mit dem Dokumentobjektmodell (DOM) können Sie auch mit [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] XML-Strukturen an Ort und Stelle ändern.|  
|[Advanced LINQ to XML Programming (C#) (Erweiterte LINQ to XML-Programmierung (C#))](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)|Enthält Informationen zu Anmerkungen und Ereignissen, zum Streaming und zu anderen erweiterten Szenarios.|  
|[LINQ to XML Security (C#) (LINQ to XML-Sicherheit (C#))](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-security.md)|Beschreibt Sicherheitsprobleme im Zusammenhang mit LINQ to XML und enthält hilfreiche Informationen zur Minderung von Sicherheitsrisiken.|  
|[XML-Beispieldokumente (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)|Enthält die XML-Beispieldokumente, die in vielen Beispielen in dieser Dokumentation verwendet werden.|  
  
## <a name="see-also"></a>Siehe auch  
 [Getting Started (LINQ to XML) (Erste Schritte (LINQ to XML))](../../../../csharp/programming-guide/concepts/linq/getting-started-linq-to-xml.md)   
 [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)
