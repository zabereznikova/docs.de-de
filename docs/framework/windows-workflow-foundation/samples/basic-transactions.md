---
title: "Transaktionen | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
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
---
# Transaktionen
Dieser Abschnitt enthält Beispiele, in denen Workflowtransaktionen in [!INCLUDE[wf](../../../../includes/wf-md.md)] veranschaulicht werden.  
  
## In diesem Abschnitt  
 [Grundlegender TransactionScope](../../../../docs/framework/windows-workflow-foundation/samples/basic-transactionscope.md)  
 Besteht aus vier Szenarien, die zeigen, wie <xref:System.Activities.Statements.TransactionScope>\-Instanzen geschachtelt werden.  
  
 [Verwendung von TransactedReceiveScope](../../../../docs/framework/windows-workflow-foundation/samples/use-of-transactedreceivescope.md)  
 Veranschaulicht, wie eine Transaktion mit <xref:System.Activities.Statements.TransactionScope> von einem Client auf einen Server übertragen wird, um eine neue Transaktion auf dem Client und ein <xref:System.ServiceModel.Activities.TransactedReceiveScope>\-Element zu erstellen, sodass eine Meldung mit einem Transaktionsfluss empfangen und die Lebensdauer der Transaktion auf dem Server mit einem Bereich versehen werden kann.  
  
 [Schachteln von TransactionScope innerhalb eines Diensts](../../../../docs/framework/windows-workflow-foundation/samples/nesting-of-transactionscope-within-a-service.md)  
 Besteht aus zwei Szenarien, die zeigen, wie <xref:System.Activities.Statements.TransactionScope>\-Aktivitätsinstanzen innerhalb eines Diensts behandelt werden.