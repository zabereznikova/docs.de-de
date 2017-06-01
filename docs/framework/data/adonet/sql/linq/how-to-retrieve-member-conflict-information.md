---
title: "Vorgehensweise: Abrufen von Memberkonfliktinformationen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 7dd6829e-79a5-4480-9023-9e588cb0bf2e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Abrufen von Memberkonfliktinformationen
Sie können die <xref:System.Data.Linq.MemberChangeConflict>\-Klasse verwenden, um Informationen über einzelne kollidierende Member abzurufen.  In diesem gleichen Kontext können Sie für jeden Member für eine benutzerdefinierte Behandlung des Konflikts sorgen.  Weitere Informationen finden Sie unter [Vollständige Parallelität: Übersicht](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
## Beispiel  
 Der folgende Code wechselt durch die <xref:System.Data.Linq.ObjectChangeConflict>\-Objekte.  Für jedes Objekt durchläuft er dann die <xref:System.Data.Linq.MemberChangeConflict>\-Objekte.  
  
> [!NOTE]
>  Schließen Sie <xref:System.Reflection> ein, um <xref:System.Data.Linq.MemberChangeConflict.Member%2A>\-Informationen bereitzustellen.  
  
 [!code-csharp[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.memberchangeconflict/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.MemberChangeConflict#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.memberchangeconflict/vb/module1.vb#1)]  
  
## Siehe auch  
 [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)