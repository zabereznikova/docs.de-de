---
title: "Vorgehensweise: Einklammern von Daten&#252;bergaben durch das Verwenden von Transaktionen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 94044a31-de90-479b-935a-8159b4ae5c5a
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Einklammern von Daten&#252;bergaben durch das Verwenden von Transaktionen
Sie können <xref:System.Transactions.TransactionScope> verwenden, um die Übergaben zur Datenbank einzuklammern.  Weitere Informationen finden Sie unter [Unterstützung von Transaktionen](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md).  
  
## Beispiel  
 Im folgenden Code wird die Datenbankübergabe in einem <xref:System.Transactions.TransactionScope> eingeschlossen.  
  
 [!code-csharp[DLinqSubmittingChanges#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#3)]
 [!code-vb[DLinqSubmittingChanges#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#3)]  
  
## Siehe auch  
 [Herunterladen von Beispieldatenbanken](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)   
 [Vornehmen und Übergeben von Datenänderungen](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)   
 [Unterstützung von Transaktionen](../../../../../../docs/framework/data/adonet/sql/linq/transaction-support.md)