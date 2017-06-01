---
title: "Von System.Transactions bereitgestellte Funktionen  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e458cef9-63b5-4401-b448-1536dcd9d9e5
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Von System.Transactions bereitgestellte Funktionen 
In diesem Abschnitt wird beschrieben, wie Sie anhand der Funktionen, die der <xref:System.Transactions>\-Namespace bereitstellt, Ihre eigene Transaktionsanwendung und Ihren eigenen Ressourcen\-Manager schreiben können.In diesem Abschnitt wird insbesondere darauf eingegangen, wie eine \(lokale oder verteilte\) Transaktion erstellt wird und ein oder mehrere Teilnehmer daran teilnehmen können.  
  
## Übersicht über System.Transactions  
 Die Infrastruktur, die von den Klassen im <xref:System.Transactions>\-Namespace bereitgestellt werden, erleichtern die Transaktionsprogrammierung und machen sie effizienter, da von SQL Server, ADO.NET, Message Queuing \(MSMQ\) und Microsoft Distributed Transaction Coordinator \(MSDTC\) gestartete Transaktionen unterstützt werden.Der <xref:System.Transactions>\-Namespace bietet sowohl ein explizites Programmiermodell, das auf der <xref:System.Transactions.Transaction>\-Klasse basiert, als auch ein implizites Programmiermodell, das die <xref:System.Transactions.TransactionScope>\-Klasse verwendet, in der Transaktionen automatisch von der Infrastruktur verwaltet werden.Weitere Informationen zum Erstellen einer Transaktionsanwendung mit diesen beiden Modellen finden Sie unter [Schreiben einer Transaktionsanwendung ](../../../../docs/framework/data/transactions/writing-a-transactional-application.md).  
  
 Der <xref:System.Transactions>\-Namespace stellt auch Typen zur Implementierung eines Ressourcen\-Managers bereit.Mit einem Ressourcen\-Manager werden dauerhafte oder flüchtige in einer Transaktion verwendete Daten verwaltet. Zusammen mit dem Transaktions\-Manager gewährleistet der Ressourcen\-Manager Unteilbarkeit und Isolation für die Anwendung.Der von der <xref:System.Transactions>\-Infrastruktur bereitgestellte Transaktions\-Manager unterstützt Transaktionen, die mehrere flüchtige Ressourcen oder eine einzelne dauerhafte Ressource umfassen.Weitere Informationen zum Implementieren eines Ressourcen\-Managers finden Sie unter [Implementieren eines Ressourcen\-Managers ](../../../../docs/framework/data/transactions/implementing-a-resource-manager.md).  
  
 Der Transaktions\-Manager eskaliert zudem lokale Transaktionen durch Koordination mit einem datenträgerbasierten Transaktions\-Manager wie DTC transparent zu verteilten Transaktionen, wenn sich ein zusätzlicher dauerhafter Ressourcen\-Manager bei der Transaktion einträgt.Es gibt zwei grundlegende Methoden, mit der <xref:System.Transactions>\-Infrastruktur eine verbesserte Leistung zu erreichen.  
  
-   Dynamische Eskalation: Sie stellt sicher, dass die <xref:System.Transactions>\-Infrastruktur nur MSDTC verwendet, wenn die Transaktion mehrere verteilte Ressourcen betrifft.Weitere Informationen zur dynamischen Eskalationfinden Sie im Thema [Eskalation der Transaktionsverwaltung ](../../../../docs/framework/data/transactions/transaction-management-escalation.md).  
  
-   Erweiterbare Eintragungen: Ermöglichen es einer Ressource \(z. B. einer Datenbank\), Eigentümer der Transaktion zu werden, wenn sie die einzige Entität ist, die an der Transaktion teilnimmt.Gegebenenfalls kann die <xref:System.Transactions>\-Infrastruktur die Verwaltung der Transaktion zu einem späteren Zeitpunkt an MSDTC eskalieren.Auch dies reduziert die Zahl der Fälle, in denen MSDTC verwendet wird.Erweiterbare Eintragungen werden ausführlich im Thema [Optimierung mit Einphasencommit und heraufstufbarer Einphasenbenachrichtigung ](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md) behandelt.  
  
 Der <xref:System.Transactions>\-Namespace definiert drei Vertrauensebenen – AllowPartiallyTrustedCallers \(APTCA\), DistributedTransactionPermission \(DTP\) und volle Vertrauenswürdigkeit –, die den Zugriff auf die verfügbar gemachten Ressourcentypen einschränken.Weitere Informationen zu den verschiedenen Vertrauensebenen finden Sie unter [Vertrauensebenen für Sicherheit beim Zugriff auf Ressourcen ](../../../../docs/framework/data/transactions/security-trust-levels-in-accessing-resources.md).  
  
## In diesem Abschnitt  
  
### Erstellen einer Transaktionsanwendung  
 Der <xref:System.Transactions>\-Namespace stellt zwei Modelle zum Erstellen von Transaktionsanwendungen bereit.[Implementieren einer impliziten Transaktion mit Transaktionsbereich ](../../../../docs/framework/data/transactions/implementing-an-implicit-transaction-using-transaction-scope.md) beschreibt, wie der <xref:System.Transactions>\-Namespace die Erstellung impliziter Transaktionen mithilfe der <xref:System.Transactions.TransactionScope>\-Klasse unterstützt.  
  
 [Implementieren einer expliziten Transaktion mit CommittableTransaction ](../../../../docs/framework/data/transactions/implementing-an-explicit-transaction-using-committabletransaction.md) beschreibt, wie der <xref:System.Transactions>\-Namespace die Erstellung expliziter Transaktionen mithilfe der <xref:System.Transactions.CommittableTransaction>\-Klasse unterstützt.  
  
 Weitere Themen zum Schreiben einer Transaktionsanwendung finden Sie unter [Schreiben einer Transaktionsanwendung ](../../../../docs/framework/data/transactions/writing-a-transactional-application.md).  
  
### Implementieren eines Ressourcen\-Managers  
 Informationen dazu, wie Sie einen Ressourcen\-Manager implementieren, der an einer Transaktion teilnehmen kann, finden Sie unter [Implementieren eines Ressourcen\-Managers ](../../../../docs/framework/data/transactions/implementing-a-resource-manager.md).In diesem Abschnitt werden das Eintragen einer Ressource, das Durchführen eines Transaktionscommits, die Wiederherstellung nach einem Fehler und bewährte Methoden für die Optimierung behandelt.