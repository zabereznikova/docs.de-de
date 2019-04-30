---
title: Aufgaben der Entwickler beim Überschreiben von Standardverhalten
ms.date: 03/30/2017
ms.assetid: c6909ddd-e053-46a8-980c-0e12a9797be1
ms.openlocfilehash: 12ea526d71946cdc7ab821f5e38948fcbb57d158
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62033487"
---
# <a name="responsibilities-of-the-developer-in-overriding-default-behavior"></a>Aufgaben der Entwickler beim Überschreiben von Standardverhalten
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Erzwingt die folgenden Anforderungen, nicht jedoch das Verhalten ist undefiniert, wenn es sich bei diesen Anforderungen nicht erfüllt werden.  
  
- Die überschreibende Methode darf <xref:System.Data.Linq.DataContext.SubmitChanges%2A> oder <xref:System.Data.Linq.Table%601.Attach%2A> nicht aufrufen. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] löst eine Ausnahme aus, wenn diese Methoden in einer Überschreibungsmethode aufgerufen werden.  
  
- Überschreibungsmethoden können nicht verwendet werden, um eine Transaktion zu beginnen, zu bestätigen oder zu stoppen. Die <xref:System.Data.Linq.DataContext.SubmitChanges%2A>-Operation wird im Rahmen einer Transaktion durchgeführt. Eine innere verschachtelte Transaktion kann die äußere Transaktion behindern. Methoden zum Überschreiben eines Ladevorgangs können eine Transaktion nur starten, wenn ermittelt wurde, dass die Operation nicht in einer <xref:System.Transactions.Transaction> erfolgt.  
  
- Von Methoden zum Überschreiben wird erwartet, dass sie die jeweilige Zuordnung vollständiger Parallelität einhalten. Es wird erwartet, dass die Überschreibungsmethode eine <xref:System.Data.Linq.ChangeConflictException> auslöst, wenn ein Konflikt mit der vollständigen Parallelität auftritt. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fängt diese Ausnahme ab, damit Sie ordnungsgemäß verarbeiten können die <xref:System.Data.Linq.DataContext.SubmitChanges%2A> -Option von <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
- Die Erstellungsmethode (`Insert`) und die `Update`-Überschreibungsmethode müssen die Werte für in der Datenbank erzeugte Spalten wieder an die entsprechenden Objektmember zurückgeben, wenn die Operation erfolgreich abgeschlossen wird.  
  
     Z. B. wenn `Order.OrderID` eine Identity-Spalte zugeordnet ist (*Autoincrement* Primärschlüssel), und klicken Sie dann die `InsertOrder()` Überschreibungsmethode muss der Datenbank erzeugte ID abrufen und legen Sie die `Order.OrderID` Member dieser ID In gleicher Weise müssen Timestampmember mit den in der Datenbank erzeugten Timestampwerten aktualisiert werden, um sicherzustellen, dass die aktualisierten Objekte konsistent sind. Ein Fehler bei der Weiterleitung der in der Datenbank erstellten Werte kann zu einer Inkonsistenz zwischen der Datenbank und den vom <xref:System.Data.Linq.DataContext> verfolgten Objekten führen.  
  
- Es ist Aufgabe des Benutzers, die richtige dynamische API aufzurufen. Beispielsweise kann in der Update-Überschreibungsmethode nur das <xref:System.Data.Linq.DataContext.ExecuteDynamicUpdate%2A> aufgerufen werden. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erkennt oder überprüft nicht, ob die aufgerufene dynamische Methode für den jeweiligen Vorgang gültig ist. Wird eine nicht anwendbare Methode aufgerufen (beispielsweise <xref:System.Data.Linq.DataContext.ExecuteDynamicDelete%2A> für ein zu aktualisierendes Objekt), sind die Ergebnisse undefiniert.  
  
- Schließlich wird von der überschreibenden Methode erwartet, dass die festgestellte Operation ausgeführt wird. Die Semantik von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Operationen (direktes Laden, verzögertes Laden und <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) setzt voraus, dass der angegebene Dienst bereitgestellt wird. Wird beispielsweise beim Überschreiben eines Ladevorgangs nur eine leere Auflistung zurückgegeben, ohne den Inhalt der Datenbank zu prüfen, kann dies zu inkonsistenten Daten führen.  
  
## <a name="see-also"></a>Siehe auch

- [Anpassen von Insert-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
