---
title: "Vorgehensweise: Angeben des Zeitpunkts, zu dem Parallelit&#228;tsausnahmen ausgel&#246;st werden | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vorgehensweise: Angeben des Zeitpunkts, zu dem Parallelit&#228;tsausnahmen ausgel&#246;st werden
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird eine <xref:System.Data.Linq.ChangeConflictException>\-Ausnahme ausgelöst, wenn Objekte aufgrund von Konflikten bei der vollständigen Parallelität nicht aktualisiert werden.  Weitere Informationen finden Sie unter [Vollständige Parallelität: Übersicht](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
 Bevor Sie die Änderungen an die Datenbank übergeben, können Sie angeben, wann Parallelitätsausnahmen ausgelöst werden sollen:  
  
-   Auslösen der Ausnahme beim ersten Fehler \(<xref:System.Data.Linq.ConflictMode>\).  
  
-   Beenden aller Updateversuche, Sammeln aller Fehler und Melden aller Fehler in der Ausnahme \(<xref:System.Data.Linq.ConflictMode>\).  
  
 Bei Auslösung ermöglicht die <xref:System.Data.Linq.ChangeConflictException>\-Ausnahme den Zugriff auf eine <xref:System.Data.Linq.ChangeConflictCollection>\-Auflistung.  Diese Auflistung enthält Details zu jedem Konflikt \(mit Zuweisung zu einem bestimmten fehlgeschlagenen Updateversuch\), einschließlich des Zugriffs auf die <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>\-Auflistung.  Jeder Memberkonflikt im Update wird einem Member zugewiesen, der die Parallelitätsprüfung nicht bestanden hat.  
  
## Beispiel  
 Der folgende Code zeigt Beispiele für beide Werte.  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## Siehe auch  
 [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)   
 [Vornehmen und Übergeben von Datenänderungen](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)