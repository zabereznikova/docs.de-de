---
title: "Vorgehensweise: Erkennen und Aufl&#246;sen von &#220;bergabekonflikten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 91e27206-01fb-4c7a-8afc-1383a6ac5067
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Erkennen und Aufl&#246;sen von &#220;bergabekonflikten
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] stellt viele Ressourcen zur Erkennung und Auflösung von Konflikten bereit, die von Mehrbenutzeränderungen an der Datenbank stammen.  Weitere Informationen finden Sie unter [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).  
  
## Beispiel  
 Das folgende Beispiel zeigt einen `try`\/`catch`\-Block, der eine <xref:System.Data.Linq.ChangeConflictException>\-Ausnahme abfängt.  Entitäts\- und Memberinformationen für jeden Konflikt werden im Konsolenfenster angezeigt.  
  
> [!NOTE]
>  Sie müssen die `using System.Reflection`\-Direktive \(`Imports System.Reflection` in Visual Basic\) einschließen, um das Abrufen von Informationen zu unterstützen.  Weitere Informationen finden Sie unter <xref:System.Reflection>.  
  
 [!code-csharp[DLinqSubmittingChanges#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqSubmittingChanges/cs/Program.cs#2)]
 [!code-vb[DLinqSubmittingChanges#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqSubmittingChanges/vb/Module1.vb#2)]  
  
## Siehe auch  
 [Vornehmen und Übergeben von Datenänderungen](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)   
 [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)