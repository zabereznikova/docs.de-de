---
title: Programmierhandbuch (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 4b1ffd10-ab81-4a0d-a0ca-e9876478d924
ms.openlocfilehash: d71fb2d0365199bf89b0cfbd05b614ebd7634219
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494001"
---
# <a name="programming-guide-linq-to-xml-c"></a>Programmierhandbuch (LINQ to XML) (C#)
Dieser Abschnitt enthält grundlegende Informationen und Anleitungen zum Programmieren mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].  
  
## <a name="who-should-read-this-documentation"></a>Zielgruppe  
 Diese Dokumentation wendet sich an Entwickler, die bereits über C#-Kenntnisse verfügen und sich mit einigen grundlegenden Aspekten von [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] auskennen.  
  
 Ziel dieser Dokumentation ist es, Entwicklern das Arbeiten mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] zu erleichtern. [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] vereinfacht die XML-Programmierung. und kann auch von Entwicklern verwendet werden, die keine ausgesprochenen Experten auf diesem Gebiet sind.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] basiert in weiten Teilen auf generischen Klassen. Es ist daher sehr wichtig, dass Sie die Verwendung von generischen Klassen verstehen. Außerdem ist es hilfreich, wenn Sie sich mit Delegaten auskennen, die als parametrisierte Typen deklariert sind. Wenn Sie sich zunächst mit den generischen Klassen von C# vertraut machen möchten, finden Sie entsprechende Informationen unter [Generische Klassen](../../../../csharp/programming-guide/generics/generic-classes.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
|Thema|Beschreibung|  
|-----------|-----------------|  
|[LINQ to XML Programming Overview (C#) (Übersicht der LINQ to XML-Programmierung (C#))](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)|Bietet eine Übersicht über die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Klassen sowie detaillierte Informationen zu drei der wichtigsten Klassen: <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute> und <xref:System.Xml.Linq.XDocument>.|  
|[Erstellen von XML-Bäumen (C#)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)|Enthält konzeptuelle und aufgabenbasierte Informationen zum Erstellen von XML-Strukturen. XML-Strukturen können mittels funktionaler Konstruktion oder durch Analysieren von XML-Text aus einer Zeichenfolge oder Datei erstellt werden. Sie können auch einen <xref:System.Xml.XmlReader> verwenden, um eine XML-Struktur aufzufüllen.|  
|[Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)|Enthält ausführliche Informationen zum Erstellen von XML-Strukturen, die Namespaces verwenden.|  
|[Serializing XML Trees (C#) (Serialisieren von XML-Strukturen (C#))](../../../../csharp/programming-guide/concepts/linq/serializing-xml-trees.md)|Beschreibt mehrere Ansätze für das Serialisieren einer XML-Struktur und enthält Hilfestellung bei der Auswahl des richtigen Ansatzes.|  
|[LINQ to XML Axes (C#) (LINQ to XML-Achsen (C#))](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)|Enthält eine Auflistung und Beschreibung der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Achsenmethoden, die Sie kennen müssen, bevor Sie [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]-Abfragen schreiben können.|  
|[Querying XML Trees (C#) (Abfragen von XML-Strukturen (C#))](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)|Enthält allgemeine Beispiele für das Abfragen von XML-Strukturen.|  
|[Modifying XML Trees (LINQ to XML) (C#) (Ändern von XML-Strukturen (LINQ to XML) (C#))](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)|Genau wie mit dem Dokumentobjektmodell (DOM) können Sie auch mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] XML-Strukturen an Ort und Stelle ändern.|  
|[Advanced LINQ to XML Programming (C#) (Erweiterte LINQ to XML-Programmierung (C#))](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)|Enthält Informationen zu Anmerkungen und Ereignissen, zum Streaming und zu anderen erweiterten Szenarios.|  
|[LINQ to XML Security (C#) (LINQ to XML-Sicherheit (C#))](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-security.md)|Beschreibt Sicherheitsprobleme im Zusammenhang mit LINQ to XML und enthält hilfreiche Informationen zur Minderung von Sicherheitsrisiken.|  
|[XML-Beispieldokumente (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-documents-linq-to-xml.md)|Enthält die XML-Beispieldokumente, die in vielen Beispielen in dieser Dokumentation verwendet werden.|  
  
## <a name="see-also"></a>Siehe auch

- [Erste Schritte (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/getting-started-linq-to-xml.md)
- [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)
