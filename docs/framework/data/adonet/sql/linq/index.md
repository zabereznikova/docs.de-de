---
title: "LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ist eine Komponente von [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] Version 3.5, die eine Laufzeitinfrastruktur für die Verwaltung relationaler Daten als Objekte bereitstellt.  
  
> [!NOTE]
>  Relationale Daten erscheinen als Auflistung zweidimensionaler Tabellen \(*Beziehungen* oder *Flatfiles*\), bei denen gemeinsame Spalten Tabellen verbinden.  Zur effektiven Verwendung von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] müssen Sie mit den zugrunde liegenden Prinzipien relationaler Datenbanken vertraut sein.  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird das Datenmodell einer relationalen Datenbank einem Objektmodell zugeordnet, das in der Programmiersprache des Entwicklers ausgedrückt ist.  Wenn Sie die Anwendung ausführen, übersetzt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die sprachintegrierten Abfragen im Objektmodell in SQL und sendet sie zur Ausführung an die Datenbank. Wenn die Datenbank die Ergebnisse zurückgibt, übersetzt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] diese zurück in Objekte, die Sie mit Ihrer eigenen Programmiersprache bearbeiten können.  
  
 Entwickler, die mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] arbeiten, verwenden in der Regel [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], da diese Lösung eine Benutzerschnittstelle zur Implementierung zahlreicher Funktionen von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bietet.  
  
 Die Dokumentation zu dieser Version von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] beschreibt die grundlegenden Bausteine, Verfahren und Techniken zur Erstellung von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Anwendungen.  Sie können auch in der MSDN Library nach speziellen Themen suchen und sich vor allem am [LINQ\-Forum](http://go.microsoft.com/fwlink/?LinkId=76488) beteiligen. Hier können Sie komplexere Themen ausführlich mit Experten diskutieren.  Schließlich bietet das White Paper [LINQ to SQL: .NET Language\-Integrated Query for Relational Data](http://go.microsoft.com/fwlink/?LinkId=93205) ausführliche Informationen zur [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Technologie sowie [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\- und C\#\-Codebeispiele.  
  
## In diesem Abschnitt  
 [Erste Schritte](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 Bietet eine komprimierte Übersicht über [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] sowie Informationen zu den ersten Schritten mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
 [Programmierhandbuch](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 Bietet schrittweise Anleitungen für Zuordnung, Abfrage, Update, Debugging und ähnlichen Aufgaben.  
  
 [Verweis](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 Enthält Referenzinformationen zu verschiedenen Aspekten der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Programmierung.  Die Themen umfassen SQL\-CLR\-Typzuordnung, Übersetzung von Standardabfrageoperatoren und mehr.  
  
 [Beispiele](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 Bietet Links zu [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\-Beispielen und C\#\-Beispielen.  
  
## Verwandte Abschnitte  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)  
 Bietet eine Übersicht über [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]\-Technologien.  
  
 [LINQ](../Topic/LINQ%20in%20Visual%20Basic.md)  
 Beschreibt [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]\-Technologien für [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)]\-Benutzer.  
  
 [LINQ to ADO.NET](http://msdn.microsoft.com/de-de/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 Links zum [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]\-Portal.  
  
 [Exemplarische Vorgehensweisen für LINQ to SQL](http://msdn.microsoft.com/de-de/308e66ac-f704-4e00-9b4e-7af0045a2374)  
 Listet exemplarische Vorgehensweisen für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] auf.  
  
 [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 Beschreibt, wie die in der Dokumentation verwendeten Beispieldatenbanken heruntergeladen werden.  
  
 [LinqDataSource\-Technologie – Übersicht](http://msdn.microsoft.com/de-de/104cfc3f-7385-47d3-8a51-830dfa791136)  
 Erläutert, wie das <xref:System.Web.UI.WebControls.LinqDataSource>\-Steuerelement über die [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)]\-Datenquellen\-Steuerarchitektur [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] für Web\-Entwickler bereitstellt.