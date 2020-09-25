---
title: 'Vorgehensweise: Angeben, wann Parallelitätsausnahmen ausgelöst werden'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 344ae068-ff63-4a2e-8b00-af22e143675f
ms.openlocfilehash: 9d71ca82c3fe1abd23a82d952d38c3ea23a7f1c0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91197110"
---
# <a name="how-to-specify-when-concurrency-exceptions-are-thrown"></a>Vorgehensweise: Angeben, wann Parallelitätsausnahmen ausgelöst werden

In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird eine <xref:System.Data.Linq.ChangeConflictException>-Ausnahme ausgelöst, wenn Objekte aufgrund von Konflikten bei der vollständigen Parallelität nicht aktualisiert werden. Weitere Informationen finden Sie unter vollständige Parallelität [: Übersicht](optimistic-concurrency-overview.md).  
  
 Bevor Sie die Änderungen an die Datenbank übergeben, können Sie angeben, wann Parallelitätsausnahmen ausgelöst werden sollen:  
  
- Auslösen der Ausnahme beim ersten Fehler (<xref:System.Data.Linq.ConflictMode.FailOnFirstConflict>).  
  
- Beenden aller Updateversuche, Sammeln aller Fehler und Melden aller Fehler in der Ausnahme (<xref:System.Data.Linq.ConflictMode.ContinueOnConflict>).  
  
 Bei Auslösung ermöglicht die <xref:System.Data.Linq.ChangeConflictException>-Ausnahme den Zugriff auf eine <xref:System.Data.Linq.ChangeConflictCollection>-Auflistung. Diese Auflistung enthält Details zu jedem Konflikt (mit Zuweisung zu einem bestimmten fehlgeschlagenen Updateversuch), einschließlich des Zugriffs auf die <xref:System.Data.Linq.ObjectChangeConflict.MemberConflicts%2A>-Auflistung. Jeder Memberkonflikt im Update wird einem Member zugewiesen, der die Parallelitätsprüfung nicht bestanden hat.  
  
## <a name="example"></a>Beispiel  

 Der folgende Code zeigt Beispiele für beide Werte.  
  
 [!code-csharp[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.ConflictModeEnumeration#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.conflictmodeenumeration/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Verwalten von Änderungskonflikten](how-to-manage-change-conflicts.md)
- [Vornehmen und Übergeben von Datenänderungen](making-and-submitting-data-changes.md)
