---
title: LINQ to Objects (C#)
description: Hier erhalten Sie Informationen zu LINQ to Objects in C#. Dafür werden LINQ-Abfragen mit einer beliebigen IEnumerable- oder IEnumerable<T>-Sammlung ohne LINQ-Zwischenanbieter oder API verwendet.
ms.date: 07/20/2015
ms.assetid: c5c2c178-3529-4f6c-b3df-2d5267af7f22
ms.openlocfilehash: 575708f14487670a4371d470dcdcf650b03c3175
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91202525"
---
# <a name="linq-to-objects-c"></a>LINQ to Objects (C#)

Die Bezeichnung „LINQ to Objects“ bezieht sich auf die direkte Verwendung von LINQ-Abfragen mit einer beliebigen <xref:System.Collections.IEnumerable>- oder <xref:System.Collections.Generic.IEnumerable%601>-Auflistung, ohne einen LINQ-Zwischenanbieter oder eine API wie [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md) oder [LINQ to XML](../../../../standard/linq/linq-xml-overview.md) zu verwenden. Sie können LINQ zur Abfrage beliebiger aufzählbarer Auflistungen wie <xref:System.Collections.Generic.List%601>, <xref:System.Array> oder <xref:System.Collections.Generic.Dictionary%602> verwenden. Die Sammlung kann benutzerdefiniert sein oder von einer .NET-API zurückgegeben werden.  
  
 Im Grunde stellt LINQ to Objects einen neuen Ansatz für Auflistungen dar. Bisher mussten Sie komplexe `foreach`-Schleifen erstellen, die angegeben haben, wie Daten aus einer Auflistung abgerufen werden. Im LINQ-Ansatz verfassen Sie einen deklarativen Code, in dem beschrieben wird, was Sie abrufen möchten.  
  
 Zudem bieten LINQ-Abfragen drei wesentliche Vorteile gegenüber herkömmlichen `foreach`-Schleifen:  
  
- Sie sind präziser und lesbarer, insbesondere beim Filtern mehrerer Bedingungen.  
  
- Sie bieten mit minimalem Anwendungscode leistungsstarke Filter-, Sortier- und Gruppierungsfunktionen.  
  
- Sie können mit geringfügigen oder ohne Änderungen zu anderen Datenquellen portiert werden.  
  
 Je komplexer der für die Daten durchzuführende Vorgang, desto größer ist im Allgemeinen der Vorteil, den Sie durch die Verwendung von LINQ anstelle der herkömmlichen Iterationsverfahren haben.  
  
 Der Zweck dieses Abschnitts ist es, den LINQ-Ansatz anhand einiger Beispiele zu veranschaulichen. Er ist nicht als vollständig zu betrachten.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [LINQ and Strings (C#) (LINQ und Zeichenfolgen (C#))](./linq-and-strings.md)  
 Erläutert, wie LINQ zum Abfragen und Transformieren von Zeichenfolgen und Auflistungen von Zeichenfolgen verwendet werden kann. Dieser Abschnitt umfasst auch Links zu Artikeln, die diese Prinzipien veranschaulichen.  
  
 [LINQ and Reflection (C#) (LINQ und Reflektion (C#))](how-to-query-an-assembly-s-metadata-with-reflection-linq.md)  
 Verweist auf ein Beispiel, das darstellt, wie LINQ die Reflektion verwendet.  
  
 [LINQ and File Directories (C#) (LINQ und Dateiverzeichnisse (C#))](./linq-and-file-directories.md)  
 Erläutert, wie LINQ für die Interaktion mit Dateisystemen verwendet werden kann. Dieser Abschnitt umfasst auch Links zu Artikeln, die diese Konzepte veranschaulichen.  
  
 [Vorgehensweise: Abfragen von ArrayList mit LINQ (C#)](./how-to-query-an-arraylist-with-linq.md)  
 Veranschaulicht die Abfrage einer ArrayList in Visual Basic und C#.  
  
 [Vorgehensweise: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (C#)](./how-to-add-custom-methods-for-linq-queries.md)  
 Erläutert die Erweiterung des Methodensatzes, den Sie durch Hinzufügen von Erweiterungsmethoden zur <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle verwenden können.  
  
 [Language Integrated Query (LINQ) (C#)](./index.md)  
 In diesem Artikel werden Links zu Artikeln bereitgestellt, die LINQ erläutern und Codebeispiele enthalten, die Abfragen durchführen.
