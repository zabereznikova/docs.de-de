---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Persistenzteilnehmers'
ms.date: 03/30/2017
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
ms.openlocfilehash: 1de2abb8ababd794cd644733b6e4ab0ed42b1810
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59770008"
---
# <a name="how-to-create-a-custom-persistence-participant"></a>Vorgehensweise: Erstellen eines benutzerdefinierten Persistenzteilnehmers
Die folgende Prozedur enthält die Schritte zur Erstellung eines Persistenzteilnehmers. Finden Sie unter den [Persistenz Teilnahme](https://go.microsoft.com/fwlink/?LinkID=177735) Beispiel und [Store Erweiterbarkeit](store-extensibility.md) Thema beispielimplementierungen von persistenzteilnehmern.  
  
1. Erstellen Sie eine von der <xref:System.Activities.Persistence.PersistenceParticipant>-Klasse oder von der <xref:System.Activities.Persistence.PersistenceIOParticipant>-Klasse abgeleitete Klasse. Die PersistenceIOParticipant-Klasse bietet die gleichen Erweiterbarkeitspunkte wie die PersistenceParticipant-Klasse, sondern auch zur Teilnahme an e/a-Vorgänge. Führen Sie mindestens einen der folgenden Schritte aus.  
  
2. Implementieren Sie die <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>-Methode. Die **CollectValues** Methode verfügt über zwei Wörterbuchparameter, einen zum Speichern von Lese-/schreibwerten und einen zum Speichern von lesegeschützten Werten (später in Abfragen verwendet). In dieser Methode müssen Sie diese Wörterbücher mit Daten auffüllen, die für einen Persistenzteilnehmer spezifisch sind. Jedes Wörterbuch enthält den Namen des Werts als Schlüssel und den Wert selbst als <xref:System.Runtime.DurableInstancing.InstanceValue>-Objekt.  
  
     Die Werte im ReadWriteValues-Wörterbuch werden als verpackt **InstanceValue** Objekte. Die Werte im lesegeschützten Wörterbuch werden als verpackt **InstanceValue** Objekte mit InstanceValueOptions.Optional und InstanceValueOption.WriteOnly festgelegt. Jede **InstanceValue** gebotenen die **CollectValues** Implementierungen für alle dauerhaftigkeitsteilnehmer müssen einen eindeutigen Namen haben.  
  
    ```  
    protected virtual void CollectValues (out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
3. Implementieren Sie die <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>-Methode. Die **MapValues** Methode akzeptiert zwei Parameter, die an die Parameter ähneln, die die **CollectValues** -Methode empfängt. Alle Werte erfasst werden, der **CollectValues** Phase werden über diese Wörterbuchparameter übergeben. Die neuen Werte hinzugefügt, indem die **MapValues** Phase werden die lesegeschützten Werten hinzugefügt.  Das lesegeschützte Wörterbuch wird verwendet, um Daten für eine externe Quelle bereitzustellen, die nicht direkt den Instanzwerten zugeordnet ist. Jeder von Implementierungen der angegebene Wert der **MapValues** Methode für alle dauerhaftigkeitsteilnehmer muss einen eindeutigen Namen haben.  
  
    ```  
    protected virtual IDictionary<XName,Object> MapValues (IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
     Die <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>-Methode stellt Funktionen bereit, die von <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> nicht bereitgestellt werden, und zwar im Hinblick darauf, dass sie eine Abhängigkeit von einem anderen Wert zulässt, der von einem anderen Persistenzteilnehmer bereitgestellt wird, der noch nicht von <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> verarbeitet wurde.  
  
4. Implementieren der **PublishValues** Methode. Die **PublishValues** -Methode empfängt ein Wörterbuch mit allen Werten aus dem persistenten Speicher geladen.  
  
    ```  
    protected virtual void PublishValues (IDictionary<XName,Object> readWriteValues)  
    ```  
  
5. Implementieren der **BeginOnSave** Methode, wenn der Teilnehmer ein e/a-persistenzteilnehmer ist. Diese Methode wird während eines Save-Vorgangs aufgerufen. Bei dieser Methode sollten Sie die e/a-Ergänzung für die persistente (Workflowinstanzen Speichern) durchführen.  Wenn der Host eine Transaktion für den entsprechenden Persistenzbefehl verwendet, wird die gleiche Transaktion in Transaction.Current bereitgestellt.  Darüber hinaus zeigen PersistenceIOParticipants möglicherweise eine Transaktionskonsistenzanforderung an. In diesem Fall erstellt der Host gegebenenfalls eine Transaktion für den Persistenzabschnitt.  
  
    ```  
    protected virtual IAsyncResult BeginOnSave (IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```  
  
6. Implementieren der **BeginOnLoad** Methode, wenn der Teilnehmer ein e/a-persistenzteilnehmer ist. Diese Methode wird während eines Load-Vorgangs aufgerufen. Bei dieser Methode sollten Sie die e/a-Ergänzung zum Laden von Workflowinstanzen ausführen. Wenn der Host eine Transaktion für den entsprechenden Persistenzbefehl verwendet, wird die gleiche Transaktion in Transaction.Current bereitgestellt. Darüber hinaus können Persistenz e/a-Teilnehmer Transaktionskonsistenz zwingend erforderlich, ankündigen, in dem Fall erstellt der Host eine Transaktion für den persistenzabschnitt, wenn eine andernfalls nicht verwendet werden.  
  
    ```  
    protected virtual IAsyncResult BeginOnLoad (IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```
