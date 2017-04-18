---
title: LINQ to Objects (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d2bc048fea9affd4998430783d20b978317f3897
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-objects-visual-basic"></a>LINQ to Objects (Visual Basic)
Der Begriff "LINQ to Objects" bezieht sich auf die Verwendung von LINQ-Abfragen mit einem <xref:System.Collections.IEnumerable>oder <xref:System.Collections.Generic.IEnumerable%601>Auflistung direkt verwenden, ohne die Verwendung eines intermediate LINQ-Anbieter oder einer API wie [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) oder [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable> Sie können LINQ zur Abfrage beliebiger aufzählbaren Auflistungen wie <xref:System.Collections.Generic.List%601>, <xref:System.Array>, oder <xref:System.Collections.Generic.Dictionary%602>.</xref:System.Collections.Generic.Dictionary%602> </xref:System.Array> </xref:System.Collections.Generic.List%601> Die Auflistung kann benutzerdefiniert sein oder von einer .NET Framework-API zurückgegeben werden.  
  
 Im Grunde stellt LINQ to Objects einen neuen Ansatz für Auflistungen dar. Bisher mussten Sie komplexe `For Each`-Schleifen erstellen, die angegeben haben, wie Daten aus einer Auflistung abgerufen werden. In der LINQ-Ansatz schreiben Sie deklarativen Code, der beschreibt, was Sie abrufen möchten.  
  
 Darüber hinaus LINQ-Abfragen bieten drei wesentliche Vorteile gegenüber herkömmlichen `For Each` Schleifen:  
  
1.  Sie sind präziser und lesbarer, insbesondere beim Filtern mehrerer Bedingungen.  
  
2.  Sie bieten mit minimalem Anwendungscode leistungsstarke Filter-, Sortier- und Gruppierungsfunktionen.  
  
3.  Sie können mit geringfügigen oder ohne Änderungen zu anderen Datenquellen portiert werden.  
  
 Im Allgemeinen gilt: Je komplexer die Operation, die für die Daten ausgeführt werden soll, die mehr Vorteile Sie erkennen mithilfe von LINQ anstelle der herkömmlichen Iterationsverfahren erreichen.  
  
 Dieser Abschnitt dient, den LINQ--Ansatz anhand einiger Beispiele veranschaulichen. Er ist bei weitem nicht als vollständig zu betrachten.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [LINQ und Zeichenfolgen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 Erläutert, wie LINQ zum Abfragen und Transformieren von Zeichenfolgen und Auflistungen von Zeichenfolgen verwendet werden kann. Dieser Abschnitt umfasst auch Links zu Themen, die diese Prinzipien veranschaulichen.  
  
 [LINQ und Reflektion (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-reflection.md)  
 Verweist auf ein Beispiel, das veranschaulicht, wie LINQ Reflektion verwendet.  
  
 [LINQ und Dateiverzeichnisse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 Erläutert, wie LINQ für die Interaktion mit Dateisystemen verwendet werden kann. Dieser Abschnitt umfasst auch Links zu Themen, die diese Konzepte veranschaulichen.  
  
 [Gewusst wie: Abfragen von ArrayList mit LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 Abfragen von ArrayList in c# veranschaulicht.  
  
 [Gewusst wie: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 Erläutert, wie das Erweitern der Methoden für LINQ-Abfragen durch Hinzufügen von Erweiterungsmethoden, die <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle.</xref:System.Collections.Generic.IEnumerable%601>  
  
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 Enthält Links zu Themen, die erklären LINQ und Beispiele von Codes, die Abfragen durchführen.
