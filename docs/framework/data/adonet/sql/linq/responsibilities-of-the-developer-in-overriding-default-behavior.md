---
title: "Aufgaben des Entwicklers beim &#220;berschreiben des Standardverhaltens | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c6909ddd-e053-46a8-980c-0e12a9797be1
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Aufgaben des Entwicklers beim &#220;berschreiben des Standardverhaltens
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erzwingt die folgenden Anforderungen nicht, aber das Verhalten ist nicht definiert, wenn diese Anforderungen nicht erfüllt werden.  
  
-   Die überschreibende Methode darf <xref:System.Data.Linq.DataContext.SubmitChanges%2A> oder <xref:System.Data.Linq.Table%601.Attach%2A> nicht aufrufen.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] löst eine Ausnahme aus, wenn diese Methoden in einer Überschreibungsmethode aufgerufen werden.  
  
-   Überschreibungsmethoden können nicht verwendet werden, um eine Transaktion zu beginnen, zu bestätigen oder zu stoppen.  Die <xref:System.Data.Linq.DataContext.SubmitChanges%2A>\-Operation wird im Rahmen einer Transaktion durchgeführt.  Eine innere verschachtelte Transaktion kann die äußere Transaktion behindern.  Methoden zum Überschreiben eines Ladevorgangs können eine Transaktion nur starten, wenn ermittelt wurde, dass die Operation nicht in einer <xref:System.Transactions.Transaction> erfolgt.  
  
-   Von Methoden zum Überschreiben wird erwartet, dass sie die jeweilige Zuordnung vollständiger Parallelität einhalten.  Es wird erwartet, dass die Überschreibungsmethode eine <xref:System.Data.Linq.ChangeConflictException> auslöst, wenn ein Konflikt mit der vollständigen Parallelität auftritt.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fängt diese Ausnahme ab, damit Sie die <xref:System.Data.Linq.DataContext.SubmitChanges%2A>\-Option , die von <xref:System.Data.Linq.DataContext.SubmitChanges%2A> bereitgestellt wird, ordnungsgemäß verarbeiten können.  
  
-   Die Erstellungsmethode \(`Insert`\) und die `Update`\-Überschreibungsmethode müssen die Werte für in der Datenbank erzeugte Spalten wieder an die entsprechenden Objektmember zurückgeben, wenn die Operation erfolgreich abgeschlossen wird.  
  
     Wird beispielsweise `Order.OrderID` einer Identitätsspalte zugeordnet \(*autoincrement* für den primären Schlüssel\), muss die `InsertOrder()`\-Methode die in der Datenbank erzeugte ID abrufen und den `Order.OrderID`\-Member auf diese ID festlegen.  In gleicher Weise müssen Timestampmember mit den in der Datenbank erzeugten Timestampwerten aktualisiert werden, um sicherzustellen, dass die aktualisierten Objekte konsistent sind.  Ein Fehler bei der Weiterleitung der in der Datenbank erstellten Werte kann zu einer Inkonsistenz zwischen der Datenbank und den vom <xref:System.Data.Linq.DataContext> verfolgten Objekten führen.  
  
-   Es ist Aufgabe des Benutzers, die richtige dynamische API aufzurufen.  Beispielsweise kann in der Update\-Überschreibungsmethode nur das <xref:System.Data.Linq.DataContext.ExecuteDynamicUpdate%2A> aufgerufen werden.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] erkennt oder überprüft nicht, ob die aufgerufene dynamische Methode für den jeweiligen Vorgang gültig ist.  Wird eine nicht anwendbare Methode aufgerufen \(beispielsweise <xref:System.Data.Linq.DataContext.ExecuteDynamicDelete%2A> für ein zu aktualisierendes Objekt\), sind die Ergebnisse undefiniert.  
  
-   Schließlich wird von der überschreibenden Methode erwartet, dass die festgestellte Operation ausgeführt wird.  Die Semantik von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Vorgängen \(Eager Loading, verzögertes Laden und <xref:System.Data.Linq.DataContext.SubmitChanges%2A>\) setzt voraus, dass der angegebene Dienst von den Überschreibungen bereitgestellt wird. Wird beispielsweise beim Überschreiben eines Ladevorgangs nur eine leere Auflistung zurückgegeben, ohne den Inhalt der Datenbank zu prüfen, kann dies zu inkonsistenten Daten führen.  
  
## Siehe auch  
 [Anpassen von Insert\-, Update\- und Delete\-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md)