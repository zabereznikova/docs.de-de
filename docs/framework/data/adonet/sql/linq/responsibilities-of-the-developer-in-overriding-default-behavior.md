---
title: "Aufgaben der Entwickler beim Überschreiben von Standardverhalten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6909ddd-e053-46a8-980c-0e12a9797be1
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 232f57890e70e5be0ec60408587a622fafd1ba7e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="responsibilities-of-the-developer-in-overriding-default-behavior"></a>Aufgaben der Entwickler beim Überschreiben von Standardverhalten
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]Erzwingt die folgenden Anforderungen, nicht aber das Verhalten nicht definiert ist, diese Anforderungen nicht erfüllt sind.  
  
-   Die überschreibende Methode darf <xref:System.Data.Linq.DataContext.SubmitChanges%2A> oder <xref:System.Data.Linq.Table%601.Attach%2A> nicht aufrufen. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]löst eine Ausnahme aus, wenn diese Methoden in einer Überschreibungsmethode aufgerufen werden.  
  
-   Überschreibungsmethoden können nicht verwendet werden, um eine Transaktion zu beginnen, zu bestätigen oder zu stoppen. Die <xref:System.Data.Linq.DataContext.SubmitChanges%2A>-Operation wird im Rahmen einer Transaktion durchgeführt. Eine innere verschachtelte Transaktion kann die äußere Transaktion behindern. Methoden zum Überschreiben eines Ladevorgangs können eine Transaktion nur starten, wenn ermittelt wurde, dass die Operation nicht in einer <xref:System.Transactions.Transaction> erfolgt.  
  
-   Von Methoden zum Überschreiben wird erwartet, dass sie die jeweilige Zuordnung vollständiger Parallelität einhalten. Es wird erwartet, dass die Überschreibungsmethode eine <xref:System.Data.Linq.ChangeConflictException> auslöst, wenn ein Konflikt mit der vollständigen Parallelität auftritt. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]fängt diese Ausnahme ausgelöst, damit Sie ordnungsgemäß verarbeiten können die <xref:System.Data.Linq.DataContext.SubmitChanges%2A> -Option <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.  
  
-   Die Erstellungsmethode (`Insert`) und die `Update`-Überschreibungsmethode müssen die Werte für in der Datenbank erzeugte Spalten wieder an die entsprechenden Objektmember zurückgeben, wenn die Operation erfolgreich abgeschlossen wird.  
  
     Z. B. wenn `Order.OrderID` eine Identity-Spalte zugeordnet ist (*Autoincrement* Primärschlüssel), die `InsertOrder()` Überschreibungsmethode muss der Datenbank erzeugte ID abrufen und Festlegen der `Order.OrderID` Member dieser ID an. In gleicher Weise müssen Timestampmember mit den in der Datenbank erzeugten Timestampwerten aktualisiert werden, um sicherzustellen, dass die aktualisierten Objekte konsistent sind. Ein Fehler bei der Weiterleitung der in der Datenbank erstellten Werte kann zu einer Inkonsistenz zwischen der Datenbank und den vom <xref:System.Data.Linq.DataContext> verfolgten Objekten führen.  
  
-   Es ist Aufgabe des Benutzers, die richtige dynamische API aufzurufen. Beispielsweise kann in der Update-Überschreibungsmethode nur das <xref:System.Data.Linq.DataContext.ExecuteDynamicUpdate%2A> aufgerufen werden. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erkennt oder überprüft nicht, ob die aufgerufene dynamische Methode für den jeweiligen Vorgang gültig ist. Wird eine nicht anwendbare Methode aufgerufen (beispielsweise <xref:System.Data.Linq.DataContext.ExecuteDynamicDelete%2A> für ein zu aktualisierendes Objekt), sind die Ergebnisse undefiniert.  
  
-   Schließlich wird von der überschreibenden Methode erwartet, dass die festgestellte Operation ausgeführt wird. Die Semantik von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Operationen (direktes Laden, verzögertes Laden und <xref:System.Data.Linq.DataContext.SubmitChanges%2A>) setzt voraus, dass der angegebene Dienst bereitgestellt wird. Wird beispielsweise beim Überschreiben eines Ladevorgangs nur eine leere Auflistung zurückgegeben, ohne den Inhalt der Datenbank zu prüfen, kann dies zu inkonsistenten Daten führen.  
  
## <a name="see-also"></a>Siehe auch  
 [Anpassen von Insert-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)
