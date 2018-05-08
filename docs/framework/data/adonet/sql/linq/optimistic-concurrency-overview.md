---
title: 'Vollständige Parallelität: Übersicht'
ms.date: 03/30/2017
ms.assetid: c2e38512-d0c8-4807-b30a-cb7e30338694
ms.openlocfilehash: 5b4603526896364285cb3c85d12568ed9031ed47
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="optimistic-concurrency-overview"></a>Vollständige Parallelität: Übersicht
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die Steuerung der vollständigen Parallelität. Die folgende Tabelle beschreibt, die auf vollständige Parallelität in gelten [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Dokumentation:  
  
|Begriffe|Beschreibung|  
|-----------|-----------------|  
|Parallelität|Die Situation, in der zwei oder mehr Benutzer gleichzeitig versuchen, die gleiche Datenbankzeile zu aktualisieren.|  
|Parallelitätskonflikt|Die Situation, in der zwei oder mehr Benutzer gleichzeitig versuchen, konkurrierende Werte an eine oder mehrere Datenbankzeilen zu übergeben.|  
|Parallelitätssteuerung|Die Technik zur Behebung von Parallelitätskonflikten.|  
|Steuerelement für vollständige Parallelität|Die Technik zur Prüfung, ob andere Transaktionen die Werte in einer Zeile geändert haben, bevor die Übergabe von Änderungen zugelassen wird.<br /><br /> Im Gegensatz dazu *Steuerung durch eingeschränkte Parallelität*, die den Datensatz, um Parallelitätskonflikte zu vermeiden sperrt.<br /><br /> *Optimistische* Steuerung verdankt Ihre dass ausgeht, dass sie die Wahrscheinlichkeit zu einem Konflikt zwischen Transaktionen unwahrscheinlich ist.|  
|Konfliktauflösung|Der Prozess des Aktualisierens eines problematischen Elements durch eine erneute Datenbankabfrage und Ausgleichen der Unterschiede.<br /><br /> Wenn ein Objekt aktualisiert wird, enthält der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Änderungsprotokollierer die folgenden Daten:<br /><br /> – Die Werte, die ursprünglich aus der Datenbank abgerufen und verwendet für das Update überprüfen.<br />-Die neuen Datenbankwerte aus der nachfolgenden Abfrage.<br /><br /> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ermittelt dann, ob ein Objektkonflikt vorliegt (d. h., ob sich die Werte von einem oder mehreren Membern geändert haben). Wenn das Objekt in Konflikt stehen, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] als Nächstes bestimmt, welche Member in Konflikt stehen.<br /><br /> Jeder von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erkannte Memberkonflikt wird einer Konfliktliste hinzugefügt.|  
  
 In der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Objektmodell ein *Konflikts der vollständigen Parallelität* tritt auf, wenn beide der folgenden Bedingungen zutreffen:  
  
-   Der Client versucht, Änderungen an die Datenbank zu übergeben.  
  
-   Ein oder mehrere Werte der Updateprüfung wurden in der Datenbank aktualisiert, seit der Client sie zuletzt gelesen hat.  
  
 Die Behebung dieses Konflikts umfasst die Erkennung der Member, bei deren Objekten der Konflikt auftritt. Anschließend wird entschieden, wie weiter vorgegangen wird.  
  
> [!NOTE]
>  Nur die als <xref:System.Data.Linq.Mapping.UpdateCheck.Always> oder <xref:System.Data.Linq.Mapping.UpdateCheck.WhenChanged> zugeordneten Member nehmen an Prüfungen der vollständigen Parallelität teil. Für die als <xref:System.Data.Linq.Mapping.UpdateCheck.Never> gekennzeichneten Member finden keine Prüfungen statt. Weitere Informationen finden Sie unter <xref:System.Data.Linq.Mapping.UpdateCheck>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Szenario bereitet beispielsweise User1 ein Update vor, indem er eine Zeile aus der Datenbank abruft. User1 empfängt eine Zeile mit Werten von Alfreds, Maria und Sales.  
  
 User1 möchte den Wert der Manager-Spalte in Alfred und den Wert der Department-Spalte in Marketing ändern. Bevor User1 diese Änderungen übergeben kann, hat User2 Änderungen an der Datenbank vorgenommen. Damit wurde der Wert der Assistant-Spalte in Mary und der Wert der Department-Spalte in Service geändert.  
  
 Wenn User1 jetzt versucht, Änderungen zu übergeben, schlägt die Übergabe fehl, und eine <xref:System.Data.Linq.ChangeConflictException>-Ausnahme wird ausgelöst. Dieser Fall tritt ein, weil die Datenbankwerte der Assistant-Spalte und der Department-Spalte nicht den Erwartungen entsprechen. Bei Membern, die die Assistant-Spalte und die Department-Spalte vertreten, tritt ein Konflikt auf. Die folgende Tabelle fasst diese Situation zusammen.  
  
||Manager|Assistant|Department|  
|------|-------------|---------------|----------------|  
|Ursprünglicher Zustand|Alfreds|Maria|Sales|  
|User1|Alfred||Marketing|  
|User2||Mary|Dienst|  
  
 Sie können Konflikte wie diesen auf verschiedene Weise lösen. Weitere Informationen finden Sie unter [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).  
  
## <a name="conflict-detection-and-resolution-checklist"></a>Checkliste für Konflikterkennung und -auflösung  
 Sie können Konflikte auf jeder Detailebene erkennen und beheben. Einerseits können Sie alle Konflikte auf eine von drei Arten beheben (siehe <xref:System.Data.Linq.RefreshMode>). Hierbei müssen keine weiteren Aspekte berücksichtigt werden. Andererseits können Sie für jeden Konflikttyp bei jedem Member eine bestimmte Aktion zuweisen.  
  
-   Definieren oder überarbeiten Sie die <xref:System.Data.Linq.Mapping.UpdateCheck>-Optionen in Ihrem Objektmodell.  
  
     Weitere Informationen finden Sie unter [Vorgehensweise: die Elemente angeben Parallelitätskonflikte getestet werden](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).  
  
-   Im Try/Catch-Block Ihres Aufrufs für <xref:System.Data.Linq.DataContext.SubmitChanges%2A> können Sie angeben, zu welchem Zeitpunkt die Ausnahmen ausgelöst werden sollen.  
  
     Weitere Informationen finden Sie unter [Vorgehensweise: Geben Sie bei der Parallelitätsausnahmen ausgelöst werden](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md).  
  
-   Ermitteln Sie, wie viele Konfliktdetails Sie abrufen möchten, und gestalten Sie den Try/Catch-Block entsprechend.  
  
     Weitere Informationen finden Sie unter [Vorgehensweise: Abrufen von Entitätskonfliktinformationen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-entity-conflict-information.md) und [Vorgehensweise: Abrufen von Memberkonfliktinformationen](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-member-conflict-information.md).  
  
-   Schließen Sie in Ihrem `try` / `catch` code, wie Sie die verschiedenen Konflikte zu lösen Sie ermitteln möchten.  
  
     Weitere Informationen finden Sie unter [wie: Konflikte lösen, indem und Beibehalten von Datenbankwerten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md), [Vorgehensweise: Konflikte lösen, indem das Überschreiben von Datenbankwerten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md), und [wie: Auflösen von Konflikten durch Zusammenführen mit Datenbankwerten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-merging-with-database-values.md).  
  
## <a name="linq-to-sql-types-that-support-conflict-discovery-and-resolution"></a>LINQ an SQL-Typen, die Konfliktermittlung und -auflösung unterstützen  
 Zu den Klassen und Funktionen, die die Behebung von Konflikten bei der vollständigen Parallelität in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützen, zählen:  
  
-   <xref:System.Data.Linq.ObjectChangeConflict?displayProperty=nameWithType>  
  
-   <xref:System.Data.Linq.MemberChangeConflict?displayProperty=nameWithType>  
  
-   <xref:System.Data.Linq.ChangeConflictCollection?displayProperty=nameWithType>  
  
-   <xref:System.Data.Linq.ChangeConflictException?displayProperty=nameWithType>  
  
-   <xref:System.Data.Linq.DataContext.ChangeConflicts%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.Linq.DataContext.Refresh%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A?displayProperty=nameWithType>  
  
-   <xref:System.Data.Linq.Mapping.UpdateCheck?displayProperty=nameWithType>  
  
-   <xref:System.Data.Linq.RefreshMode?displayProperty=nameWithType>  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
