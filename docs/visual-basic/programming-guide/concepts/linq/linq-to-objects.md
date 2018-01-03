---
title: LINQ to Objects (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dd4c30bc-1c9b-4781-a482-b5eada38deb2
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c2a48e792c656a84c07730b67f734f6b539ab97d
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linq-to-objects-visual-basic"></a>LINQ to Objects (Visual Basic)
Die Bezeichnung „LINQ to Objects“ bezieht sich auf die direkte Verwendung von LINQ-Abfragen mit einer beliebigen <xref:System.Collections.IEnumerable>- oder <xref:System.Collections.Generic.IEnumerable%601>-Auflistung, ohne einen LINQ-Zwischenanbieter oder eine API wie [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) oder [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) zu verwenden. Sie können LINQ zur Abfrage beliebiger aufzählbarer Auflistungen wie <xref:System.Collections.Generic.List%601>, <xref:System.Array> oder <xref:System.Collections.Generic.Dictionary%602> verwenden. Die Auflistung kann entweder benutzerdefiniert sein oder von einer .NET Framework-API zurückgegeben werden.  
  
 Im Grunde stellt LINQ to Objects einen neuen Ansatz für Auflistungen dar. Bisher mussten Sie komplexe `For Each`-Schleifen erstellen, die angegeben haben, wie Daten aus einer Auflistung abgerufen werden. Im LINQ-Ansatz verfassen Sie einen deklarativen Code, in dem beschrieben wird, was Sie abrufen möchten.  
  
 Zudem bieten LINQ-Abfragen drei wesentliche Vorteile gegenüber herkömmlichen `For Each`-Schleifen:  
  
1.  Sie sind präziser und lesbarer, insbesondere beim Filtern mehrerer Bedingungen.  
  
2.  Sie bieten mit minimalem Anwendungscode leistungsstarke Filter-, Sortier- und Gruppierungsfunktionen.  
  
3.  Sie können mit geringfügigen oder ohne Änderungen zu anderen Datenquellen portiert werden.  
  
 Je komplexer die für die Daten durchzuführende Operation, desto größer ist im Allgemeinen der Vorteil, den Sie durch die Verwendung von LINQ anstelle der herkömmlichen Iterationsverfahren haben.  
  
 Der Zweck dieses Abschnitts ist es, den LINQ-Ansatz anhand einiger Beispiele zu veranschaulichen. Er ist bei weitem nicht als vollständig zu betrachten.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [LINQ und Zeichenfolgen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)  
 Erläutert, wie LINQ zum Abfragen und Transformieren von Zeichenfolgen und Auflistungen von Zeichenfolgen verwendet werden kann. Dieser Abschnitt umfasst auch Links zu Themen, die diese Prinzipien veranschaulichen.  
  
 [LINQ und Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-reflection.md)  
 Verweist auf ein Beispiel, das darstellt, wie LINQ die Reflektion verwendet.  
  
 [LINQ and File Directories (Visual Basic) (LINQ und Dateiverzeichnisse (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)  
 Erläutert, wie LINQ für die Interaktion mit Dateisystemen verwendet werden kann. Dieser Abschnitt umfasst auch Links zu Themen, die diese Konzepte veranschaulichen.  
  
 [Vorgehensweise: Abfragen von ArrayList mit LINQ (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 Veranschaulicht die Abfrage einer ArrayList in Visual Basic und C#.  
  
 [Vorgehensweise: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 Erläutert die Erweiterung des Methodensatzes, den Sie durch Hinzufügen von Erweiterungsmethoden zur <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle verwenden können.  
  
 [Language-Integrated Query (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 Stellt Links zu Themen bereit, die LINQ erläutern. Zudem werden Codebeispiele bereitgestellt, die Abfragen durchführen.
