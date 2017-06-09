---
title: "Unterst&#252;tzung von Transaktionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8cceb26e-8d36-4365-8967-58e2e89e0187
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Unterst&#252;tzung von Transaktionen
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt drei unterschiedliche Transaktionsmodelle.  Nachfolgend werden diese Modelle in der Reihenfolge der durchgeführten Prüfungen aufgelistet.  
  
## Explizite lokale Transaktion  
 Wird <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufgerufen und ist die <xref:System.Data.Linq.DataContext.Transaction%2A>\-Eigenschaft auf eine \(`IDbTransaction`\-\) Transaktion festgelegt, erfolgt der <xref:System.Data.Linq.DataContext.SubmitChanges%2A>\-Aufruf im Kontext der gleichen Transaktion.  
  
 Es ist Ihre Aufgabe, die Transaktion nach erfolgreicher Ausführung zu bestätigen oder rückgängig zu machen.  Die Verbindung, die der Transaktion entspricht, muss zur Verbindung passen, die zum Erstellen des <xref:System.Data.Linq.DataContext> verwendet wurde.  Eine Ausnahme wird ausgelöst, wenn eine andere Verbindung verwendet wird.  
  
## Explizit verteilbare Transaktion  
 Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-APIs \(einschließlich, jedoch nicht begrenzt auf <xref:System.Data.Linq.DataContext.SubmitChanges%2A>\) im Rahmen einer aktiven <xref:System.Transactions.Transaction> aufrufen.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erkennt, dass der Aufruf im Bereich einer Transaktion ist und keine neue Transaktion erstellt.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vermeidet auch, die Verbindung in diesem Fall zu schließen.  Sie können Abfragen und <xref:System.Data.Linq.DataContext.SubmitChanges%2A> im Kontext einer solchen Transaktion ausführen.  
  
## Implizite Transaktion  
 Wenn Sie <xref:System.Data.Linq.DataContext.SubmitChanges%2A> aufrufen, prüft [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], ob der Aufruf im Rahmen einer <xref:System.Transactions.Transaction> erfolgt oder ob die `Transaction`\-Eigenschaft \(`IDbTransaction`\) auf eine vom Benutzer gestartete lokale Transaktion festgelegt ist.  Wird keine Transaktion gefunden, startet [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eine lokale Transaktion \(`IDbTransaction`\) und verwendet diese zur Ausführung der erzeugten SQL\-Befehle.  Wurden alle SQL\-Befehle erfolgreich abgeschlossen, bestätigt [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] die lokale Transaktion und kehrt zurück.  
  
## Siehe auch  
 [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)   
 [Vorgehensweise: Einklammern von Datenübergaben durch das Verwenden von Transaktionen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-bracket-data-submissions-by-using-transactions.md)