---
title: "Vorgehensweise: Beheben von Konflikten durch Beibehalten von Datenbankwerten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Beheben von Konflikten durch Beibehalten von Datenbankwerten
Wenn Sie Unterschiede zwischen den erwarteten und den tatsächlichen Datenbankwerten ausgleichen möchten, bevor Sie versuchen, Ihre Änderungen erneut zu übergeben, können Sie die Datenbankwerte mithilfe von <xref:System.Data.Linq.RefreshMode> erhalten.  Die aktuellen Werte im Objektmodell werden dann überschrieben.  Weitere Informationen finden Sie unter [Vollständige Parallelität: Übersicht](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
> [!NOTE]
>  In allen Fällen wird der Datensatz auf dem Client erst durch Abrufen der geänderten Daten aus der Datenbank aktualisiert.  Diese Aktion stellt sicher, dass der nächste Updateversuch nicht bei den gleichen Parallelitätsprüfungen fehlschlägt.  
  
## Beispiel  
 In diesem Szenario wird eine <xref:System.Data.Linq.ChangeConflictException>\-Ausnahme ausgelöst, wenn User1 versucht, Änderungen zu übergeben, da User2 zwischenzeitlich die Assistant\-Spalte und die Department\-Spalte geändert hat.  Die folgende Tabelle zeigt die Situation.  
  
||Manager|Assistant|Department|  
|------|-------------|---------------|----------------|  
|Ursprünglicher Datenbankzustand bei Abfrage durch User1 und User2.|Alfreds|Maria|Sales|  
|User1 bereitet sich auf die Übergabe dieser Änderungen vor.|Alfred||Marketing|  
|User2 hat diese Änderungen bereits übergeben.||Mary|Dienst|  
  
 User1 entscheidet sich, diesen Konflikt zu beheben, indem die neueren Datenbankwerte die aktuellen Werte im Objektmodell überschreiben.  
  
 Wenn User1 den Konflikt durch Verwendung von <xref:System.Data.Linq.RefreshMode> behebt, entspricht das Ergebnis in der Datenbank der folgenden Tabelle:  
  
||Manager|Assistant|Department|  
|------|-------------|---------------|----------------|  
|Neuer Zustand nach Konfliktlösung.|Alfreds<br /><br /> \(Original\)|Mary<br /><br /> \(von User2\)|Dienst<br /><br /> \(von User2\)|  
  
 Im folgenden Beispielcode wird gezeigt, wie die aktuellen Werte im Objektmodell mit den Datenbankwerten überschrieben werden.  \(Keine Inspektion oder benutzerdefinierte Behandlung einzelner Memberkonflikte.\)  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## Siehe auch  
 [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)