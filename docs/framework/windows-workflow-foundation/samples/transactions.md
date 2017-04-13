---
title: "Transaktionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 51212219-a39e-448e-bff3-10064ff5de64
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# Transaktionen
Dieser Abschnitt enthält Beispiele mit Szenarien, in denen Workflowtransaktionen in [!INCLUDE[wf](../../../../includes/wf-md.md)] verwendet werden.  
  
## In diesem Abschnitt  
 [Ausführen eines Workflows in einem imperativen TransactionScope](../../../../docs/framework/windows-workflow-foundation/samples/execute-a-workflow-in-an-imperative-transactionscope.md)  
 Veranschaulicht, wie ein Workflow mit <xref:System.Activities.WorkflowInvoker> unter einem <xref:System.Transactions.Transaction> von obligatorischem C\#\-Code ausgeführt wird.  
  
 [Transaktions\-Konvoi\-Bereich](../../../../docs/framework/windows-workflow-foundation/samples/transaction-convoy-scope.md)  
 Veranschaulicht, wie ein paralleles Konvoi\-Meldungsaktivitätsmuster zusammen mit einem <xref:System.ServiceModel.Activities.TransactedReceiveScope> verwendet wird, um ein Protokoll zu modellieren, bei dem in derselben Transaktion mehrere Vorgänge in beliebiger Reihenfolge auftreten können.  
  
 [Transaktionsrollback](../../../../docs/framework/windows-workflow-foundation/samples/transaction-rollback.md)  
 Veranschaulicht, wie eine benutzerdefinierte <xref:System.Activities.NativeActivity> erstellt wird, die auf den Ambient\-<xref:System.Activities.RuntimeTransactionHandle> zugreift, um die Ambient\-Transaktion abzurufen und sie explizit zurückzusetzen.  
  
 [SuppressTransactionScope\-Aktivität](../../../../docs/framework/windows-workflow-foundation/samples/suppress-transaction-scope.md)  
 Veranschaulicht, wie eine benutzerdefinierte `SuppressTransactionScope`\-Aktivität erstellt wird, um die Ambient\-Laufzeittransaktion zu unterdrücken, falls vorhanden.  
  
 [Transaktive Warteschlangen](../../../../docs/framework/windows-workflow-foundation/samples/transacted-queues.md)  
 Veranschaulicht, wie Warteschlangen und Transaktionen in [!INCLUDE[wf1](../../../../includes/wf1-md.md)] integriert werden, um zuverlässige und skalierbare Dienste zu erstellen.