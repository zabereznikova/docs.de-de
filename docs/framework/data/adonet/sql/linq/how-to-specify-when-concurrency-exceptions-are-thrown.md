---
title: "Gewusst wie: Angeben, wann Parallelitätsausnahmen ausgelöst werden"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 8af833574544410977b9f881f9b2db4e6d88aa73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a>Gewusst wie: Angeben, wann Parallelitätsausnahmen ausgelöst werden
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird eine <xref:System.Data.Linq.ChangeConflictException>-Ausnahme ausgelöst, wenn Objekte aufgrund von Konflikten bei der vollständigen Parallelität nicht aktualisiert werden. Weitere Informationen finden Sie unter [vollständige Parallelität: Übersicht über](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
 Bevor Sie die Änderungen an die Datenbank übergeben, können Sie angeben, wann Parallelitätsausnahmen ausgelöst werden sollen:  
  
-   Auslösen der Ausnahme beim ersten Fehler (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).  
  
-   Beenden aller Updateversuche, Sammeln aller Fehler und Melden aller Fehler in der Ausnahme (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).  
  
 Bei Auslösung ermöglicht die <xref:System.Data.Linq.ChangeConflictException>-Ausnahme den Zugriff auf eine <xref:System.Data.Linq.ChangeConflictCollection>-Auflistung. Diese Auflistung enthält Details zu jedem Konflikt (mit Zuweisung zu einem bestimmten fehlgeschlagenen Updateversuch), einschließlich des Zugriffs auf die <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>-Auflistung. Jeder Memberkonflikt im Update wird einem Member zugewiesen, der die Parallelitätsprüfung nicht bestanden hat.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt Beispiele für beide Werte.  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)  
 [Vornehmen und übergeben von Datenänderungen](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
