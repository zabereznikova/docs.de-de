---
title: 'Vorgehensweise: Auflösen von Parallelitätskonflikten durch Zusammenführen von Datenbankwerten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1988b79c-3bfc-4c5c-a08a-86cf638bbe17
ms.openlocfilehash: 2b6daa28c23c74eaea21f1f3d499a2e206252abd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744127"
---
# <a name="how-to-resolve-conflicts-by-merging-with-database-values"></a>Vorgehensweise: Auflösen von Parallelitätskonflikten durch Zusammenführen von Datenbankwerten
Wenn Sie vor dem erneuten Übergeben Ihrer Änderungen die Unterschiede zwischen erwarteten und tatsächlichen Datenbankwerten ausgleichen möchten, können Sie mit <xref:System.Data.Linq.RefreshMode.KeepChanges> Datenbankwerte mit den aktuellen Clientmemberwerten zusammenführen. Weitere Informationen finden Sie unter [optimistische Parallelität: Übersicht über die](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
> [!NOTE]
>  In allen Fällen wird der Datensatz auf dem Client erst durch Abrufen der geänderten Daten aus der Datenbank aktualisiert. Diese Aktion stellt sicher, dass der nächste Updateversuch nicht bei den gleichen Parallelitätsprüfungen fehlschlägt.  
  
## <a name="example"></a>Beispiel  
 In diesem Szenario wird eine <xref:System.Data.Linq.ChangeConflictException>-Ausnahme ausgelöst, wenn User1 versucht, Änderungen zu übergeben, da User2 zwischenzeitlich die Assistant-Spalte und die Department-Spalte geändert hat. Die folgende Tabelle zeigt die Situation.  
  
||Manager|Assistant|Department|  
|------|-------------|---------------|----------------|  
|Ursprünglicher Datenbankzustand bei Abfrage durch User1 und User2.|Alfreds|Maria|Sales|  
|User1 bereitet sich auf die Übergabe dieser Änderungen vor.|Alfred||Marketing|  
|User2 hat diese Änderungen bereits übergeben.||Mary|Dienst|  
  
 User1 entscheidet sich, diesen Konflikt durch das Zusammenführen von Datenbankwerten mit den aktuellen Clientmemberwerten zu lösen. Im Ergebnis werden die Datenbankwerte nur dann überschrieben, wenn der aktuelle Änderungssatz diese Werte ebenfalls verändert hat.  
  
 Wenn User1 den Konflikt durch Verwendung von <xref:System.Data.Linq.RefreshMode.KeepChanges> behebt, entspricht das Ergebnis in der Datenbank der folgenden Tabelle:  
  
||Manager|Assistant|Department|  
|------|-------------|---------------|----------------|  
|Neuer Zustand nach Konfliktlösung.|Alfred<br /><br /> (von User1)|Mary<br /><br /> (von User2)|Marketing<br /><br /> (von User1)|  
  
 Im folgenden Beispielcode wird gezeigt, wie Datenbankwerte mit den aktuellen Clientmemberwerten zusammengeführt werden (sofern der Client den Wert nicht ebenfalls geändert hat). Keine Inspektion oder benutzerdefinierte Behandlung einzelner Memberkonflikte.  
  
 [!code-csharp[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#3)]  
  
## <a name="see-also"></a>Siehe auch
- [Vorgehensweise: Auflösen von Parallelitätskonflikten durch Überschreiben von Datenbankwerten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)
- [Vorgehensweise: Auflösen von Parallelitätskonflikten durch Beibehalten von Datenbankwerten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)
- [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
