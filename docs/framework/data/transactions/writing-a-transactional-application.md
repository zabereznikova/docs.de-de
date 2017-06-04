---
title: "Schreiben einer Transaktionsanwendung  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a4d891f2-6fc8-4395-93c6-6819492406e0
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Schreiben einer Transaktionsanwendung 
Als Programmierer von Transaktionsanwendungen können Sie die beiden Programmiermodelle nutzen, die der <xref:System.Transactions>\-Namespace zum Erstellen von Transaktionen zur Verfügung stellt.Sie können das explizite Programmiermodell einsetzen, indem Sie die <xref:System.Transactions.Transaction>\-Klasse verwenden, oder das implizite Programmmiermodell, in dem Transaktionen automatisch von der Infrastruktur verwaltet werden, indem Sie die <xref:System.Transactions.TransactionScope>\-Klasse verwenden.Es wird dringend empfohlen, das implizite Transaktionsmodell für die Entwicklung zu nutzen.Weitere Informationen zum Verwenden eines Transaktionsbereichs finden Sie im Thema [Implementieren einer impliziten Transaktion mit Transaktionsbereich ](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md).  
  
 Beide Modelle unterstützen die Ausführung eines Commits für eine Transaktion, wenn das Programm einen konsistenten Zustand erreicht.Wenn der Commitvorgang erfolgreich ausgeführt wurde, ist die Transaktion abgeschlossen.Wenn der Commitvorgang fehlschlägt, wird die Transaktion abgebrochen.Wenn das Anwendungsprogramm die Transaktion nicht erfolgreich abschließen kann, versucht es, die Transaktion abzubrechen und deren Auswirkungen rückgängig zu machen.  
  
## In diesem Abschnitt  
  
### Erstellen einer Transaktion  
 Der <xref:System.Transactions>\-Namespace stellt zwei Modelle zum Erstellen einer Transaktion bereit.Diese Modelle werden in den folgenden Themen behandelt.  
  
 [Implementieren einer impliziten Transaktion mit Transaktionsbereich ](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md)  
  
 Hier wird beschrieben, wie der <xref:System.Transactions>\-Namespace die Erstellung impliziter Transaktionen mithilfe der <xref:System.Transactions.TransactionScope>\-Klasse unterstützt.  
  
 [Implementieren einer expliziten Transaktion mit CommittableTransaction ](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md)  
  
 Hier wird beschrieben, wie der <xref:System.Transactions>\-Namespace die Erstellung expliziter Transaktionen mithilfe der <xref:System.Transactions.CommittableTransaction>\-Klasse unterstützt.  
  
### Eskalieren der Transaktionsverwaltung  
 Wenn eine Transaktion auf eine Ressource aus einer anderen Anwendungsdomäne zugreifen muss oder wenn Sie einen anderen stabilen Ressourcen\-Manager eintragen möchten, wird die Verwaltung der Transaktion automatisch MSDTC übertragen.Die Transaktionseskalation wird im Thema [Eskalation der Transaktionsverwaltung ](../../../../docs/framework/data/transactions/transaction-management-escalation.md) behandelt.  
  
### Parallelität  
 Im Thema [Verwalten von Parallelität mit DependentTransaction ](../../../../docs/framework/data/transactions/managing-concurrency-with-dependenttransaction.md) wird gezeigt, wie mithilfe der <xref:System.Transactions.DependentTransaction>\-Klasse Parallelität zwischen asynchronen Aufgaben erreicht werden kann.  
  
### COM\+\-Interop  
 Im Thema [Interoperabilität mit Enterprise Services und COM\+\-Transaktionen ](../../../../docs/framework/data/transactions/interoperability-with-enterprise-services-and-com-transactions.md) wird veranschaulicht, wie erreicht wird, dass verteilte Transaktionen mit COM\+\-Transaktionen zusammenarbeiten.  
  
### Diagnose  
 Im Thema [Diagnoseablaufverfolgungen ](../../../../docs/framework/data/transactions/diagnostic-traces.md) wird beschrieben, wie mithilfe der von der <xref:System.Transactions>\-Infrastruktur erzeugten Ablaufverfolgungscodes Anwendungsfehler behandelt werden können.  
  
### Arbeiten in ASP.NET  
 In diesem Thema wird beschrieben, wie Sie [Verwenden von System.Transactions in ASP.NET](../../../../docs/framework/data/transactions/using-system-transactions-in-aspnet.md) in einer <xref:System.Transactions>\-Anwendung erfolgreich verwenden können.