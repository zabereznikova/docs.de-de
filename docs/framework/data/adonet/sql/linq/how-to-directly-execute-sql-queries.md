---
title: "Vorgehensweise: Direktes Ausf&#252;hren von SQL-Abfragen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e491b9bf-741a-4296-9f51-76c25ddf6a82
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Direktes Ausf&#252;hren von SQL-Abfragen
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt die Abfragen, die von Ihnen \(in Textform\) in parametrisierte SQL\-Abfragen geschrieben wurden, und sendet diese zur Verarbeitung an den SQL\-Server.  
  
 SQL kann nicht alle lokal für Ihre Anwendung verfügbaren Varianten ausführen.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] versucht, diese lokalen Methoden in äquivalente Operationen und Funktionen zu konvertieren, die in der SQL\-Umgebung verfügbar sind.  Die meisten Methoden und die Operatoren in [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)]\-internen Datentypen verfügen über direkte Übersetzungen zu SQL\-Befehlen.  Einige können von den verfügbaren Funktionen erzeugt werden.  Jene, die nicht erzeugt werden können, generieren Laufzeitausnahmen.  Weitere Informationen finden Sie unter [SQL CLR\-Typzuordnung](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 In Fällen, in denen eine [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Abfrage für spezielle Aufgaben nicht ausreicht, können Sie die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>\-Methode zur Ausführung einer SQL\-Abfrage verwenden und das Ergebnis anschließend direkt in Objekte konvertieren.  
  
## Beispiel  
 Nehmen Sie im folgenden Beispiel an, dass die Daten für die `Customer`\-Klasse auf zwei Tabellen \(Customer1 und Customer2\) verteilt sind.  Die Abfrage gibt eine Sequenz von `Customer`\-Objekten zurück.  
  
 [!code-csharp[DLinqQuerying#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#4)]
 [!code-vb[DLinqQuerying#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#4)]  
  
 Sofern die Spaltennamen im tabellarischen Ergebnis den Spalteneigenschaften Ihrer Entitätsklasse entsprechen, erzeugt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Ihre Objekte aus einer SQL\-Abfrage.  
  
## Beispiel  
 Die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>\-Methode berücksichtigt auch Parameter.  Verwenden Sie Code wie den folgenden, um eine parametrisierte Abfrage auszuführen.  
  
 [!code-csharp[DLinqQuerying#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#5)]
 [!code-vb[DLinqQuerying#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#5)]  
  
 Die Parameter werden im Abfragetext mithilfe der gleichen verschachtelten Schreibweise wie in `Console.WriteLine()` und `String.Format()` ausgedrückt.  Tatsächlich wird `String.Format()` in der von Ihnen übergebenen Abfrage aufgerufen. Hierbei werden die in Anführungszeichen aufgeführten Parameter durch erzeugte Parameternamen wie @p0, @p1 …, @p\(n\) ersetzt.  
  
## Siehe auch  
 [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)   
 [Abfragen der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)