---
title: LINQ to Objects (C#) | Microsoft-Dokumentation
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
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
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
ms.openlocfilehash: 33402b552672fa79925fd1264444f39b19c02cd9
ms.lasthandoff: 03/13/2017

---
# <a name="linq-to-objects-c"></a>LINQ to Objects (C#)
Der Begriff „LINQ to Objects“ verweist direkt auf die Verwendung von LINQ-Abfragen mit einer beliebigen <xref:System.Collections.IEnumerable>- oder <xref:System.Collections.Generic.IEnumerable%601>-Aufzählung, ohne einen zwischengeschalteten LINQ-Anbieter oder eine API wie [LINQ to SQL](https://msdn.microsoft.com/library/bb386976) oder [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) zu verwenden. Sie können LINQ verwenden, um aufzählbare Auflistungen wie <xref:System.Collections.Generic.List%601>, <xref:System.Array> oder <xref:System.Collections.Generic.Dictionary%602> abzufragen. Die Auflistung kann entweder benutzerdefiniert sein oder von einer .NET Framework-API zurückgegeben werden.  
  
 Im Grunde stellt LINQ to Objects einen neuen Ansatz für Auflistungen dar. Bisher mussten Sie komplexe `foreach`-Schleifen erstellen, die angegeben haben, wie Daten aus einer Auflistung abgerufen werden. Im LINQ-Ansatz verfassen Sie einen deklarativen Code, in dem beschrieben wird, was Sie abrufen möchten.  
  
 Zudem bieten LINQ-Abfragen drei wesentliche Vorteile gegenüber herkömmlichen `foreach`-Schleifen:  
  
1.  Sie sind präziser und lesbarer, insbesondere beim Filtern mehrerer Bedingungen.  
  
2.  Sie bieten mit minimalem Anwendungscode leistungsstarke Filter-, Sortier- und Gruppierungsfunktionen.  
  
3.  Sie können mit geringfügigen oder ohne Änderungen zu anderen Datenquellen portiert werden.  
  
 Je komplexer die für die Daten durchzuführende Operation, desto größer ist im Allgemeinen der Vorteil, den Sie durch die Verwendung von LINQ anstelle der herkömmlichen Iterationsverfahren haben.  
  
 Der Zweck dieses Abschnitts ist es, den LINQ-Ansatz anhand einiger Beispiele zu veranschaulichen. Er ist bei weitem nicht als vollständig zu betrachten.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [LINQ and Strings (C#) (LINQ und Zeichenfolgen (C#))](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)  
 Erläutert, wie LINQ zum Abfragen und Transformieren von Zeichenfolgen und Auflistungen von Zeichenfolgen verwendet werden kann. Dieser Abschnitt umfasst auch Links zu Themen, die diese Prinzipien veranschaulichen.  
  
 [LINQ and Reflection (C#) (LINQ und Reflektion (C#))](../../../../csharp/programming-guide/concepts/linq/linq-and-reflection.md)  
 Verweist auf ein Beispiel, das darstellt, wie LINQ die Reflektion verwendet.  
  
 [LINQ and File Directories (C#) (LINQ und Dateiverzeichnisse (C#))](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)  
 Erläutert, wie LINQ für die Interaktion mit Dateisystemen verwendet werden kann. Dieser Abschnitt umfasst auch Links zu Themen, die diese Konzepte veranschaulichen.  
  
 [How to: Query an ArrayList with LINQ (C#) (Vorgehensweise: Abfragen von ArrayList mit LINQ (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)  
 Veranschaulicht die Abfrage einer ArrayList in Visual Basic und C#.  
  
 [How to: Add Custom Methods for LINQ Queries (C#) (Vorgehensweise: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (C#))](../../../../csharp/programming-guide/concepts/linq/how-to-add-custom-methods-for-linq-queries.md)  
 Erläutert die Erweiterung des Methodensatzes, den Sie durch Hinzufügen von Erweiterungsmethoden zur <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle verwenden können.  
  
 [Language-Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)  
 Stellt Links zu Themen bereit, die LINQ erläutern. Zudem werden Codebeispiele bereitgestellt, die Abfragen durchführen.
