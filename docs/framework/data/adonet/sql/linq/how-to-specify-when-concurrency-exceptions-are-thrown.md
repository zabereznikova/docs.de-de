---
title: 'Vorgehensweise: Angeben, wann Parallelitätsausnahmen ausgelöst werden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: 30dd83c68472ecd3244cfc87b6df97b948b9a84f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182987"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a>Vorgehensweise: Angeben, wann Parallelitätsausnahmen ausgelöst werden
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird eine <xref:System.Data.Linq.ChangeConflictException>-Ausnahme ausgelöst, wenn Objekte aufgrund von Konflikten bei der vollständigen Parallelität nicht aktualisiert werden. Weitere Informationen finden Sie unter [optimistische Parallelität: Übersicht über die](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
 Bevor Sie die Änderungen an die Datenbank übergeben, können Sie angeben, wann Parallelitätsausnahmen ausgelöst werden sollen:  
  
-   Auslösen der Ausnahme beim ersten Fehler (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).  
  
-   Beenden aller Updateversuche, Sammeln aller Fehler und Melden aller Fehler in der Ausnahme (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).  
  
 Bei Auslösung ermöglicht die <xref:System.Data.Linq.ChangeConflictException>-Ausnahme den Zugriff auf eine <xref:System.Data.Linq.ChangeConflictCollection>-Auflistung. Diese Auflistung enthält Details zu jedem Konflikt (mit Zuweisung zu einem bestimmten fehlgeschlagenen Updateversuch), einschließlich des Zugriffs auf die <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>-Auflistung. Jeder Memberkonflikt im Update wird einem Member zugewiesen, der die Parallelitätsprüfung nicht bestanden hat.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt Beispiele für beide Werte.  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [Vornehmen und Übergeben von Datenänderungen](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
