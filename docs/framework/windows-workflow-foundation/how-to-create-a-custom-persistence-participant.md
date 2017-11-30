---
title: 'Gewusst wie: Erstellen eines benutzerdefinierten Persistenzteilnehmers'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4c690a0233a425a706ead7441447f589d8330bc0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-custom-persistence-participant"></a>Gewusst wie: Erstellen eines benutzerdefinierten Persistenzteilnehmers
Die folgende Prozedur enthält die Schritte zur Erstellung eines Persistenzteilnehmers. Finden Sie unter der [Persistenz Teilnahme](http://go.microsoft.com/fwlink/?LinkID=177735) Beispiel und [Store Erweiterbarkeit](../../../docs/framework/windows-workflow-foundation/store-extensibility.md) Thema für Beispiel Implementierungen der persistenzteilnehmer.  
  
1.  Erstellen Sie eine von der <xref:System.Activities.Persistence.PersistenceParticipant>-Klasse oder von der <xref:System.Activities.Persistence.PersistenceIOParticipant>-Klasse abgeleitete Klasse. Die PersistenceIOParticipant-Klasse bietet die gleichen Erweiterbarkeitspunkte wie die PersistenceParticipant-Klasse und kann zusätzlich dazu in E/A-Vorgänge eingebunden werden. Führen Sie mindestens einen der folgenden Schritte aus.  
  
2.  Implementieren Sie die <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>-Methode. Die **CollectValues** Methode verfügt über zwei Wörterbuchparameter, einen zum Speichern von Lese-/schreibwerten und einen zum Speichern von lesegeschützten Werten (wird später in Abfragen verwendet). In dieser Methode müssen Sie diese Wörterbücher mit Daten auffüllen, die für einen Persistenzteilnehmer spezifisch sind. Jedes Wörterbuch enthält den Namen des Werts als Schlüssel und den Wert selbst als <xref:System.Runtime.DurableInstancing.InstanceValue>-Objekt.  
  
     Die Werte im ReadWriteValues-Wörterbuch werden als verpackt **InstanceValue** Objekte. Die Werte im lesegeschützten Wörterbuch werden als verpackt **InstanceValue** Objekte mit InstanceValueOptions.Optional und InstanceValueOption.WriteOnly festgelegt. Jede **InstanceValue** gebotenen der **CollectValues** Implementierungen für alle dauerhaftigkeitsteilnehmer müssen einen eindeutigen Namen aufweisen.  
  
    ```  
    protected virtual void CollectValues (out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
3.  Implementieren Sie die <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>-Methode. Die **MapValues** Methode nimmt zwei Parameter, die die Parameter ähneln, die die **CollectValues** Methode empfängt. Alle Werte gesammelt werden, der **CollectValues** Phase werden über diese Wörterbuchparameter übergeben. Die neuen Werte hinzugefügt, indem die **MapValues** Phase der lesegeschützten Werten hinzugefügt werden.  Das lesegeschützte Wörterbuch wird verwendet, um Daten für eine externe Quelle bereitzustellen, die nicht direkt den Instanzwerten zugeordnet ist. Jeder von Implementierungen der angegebene Wert der **MapValues** Methode für alle dauerhaftigkeitsteilnehmer muss einen eindeutigen Namen aufweisen.  
  
    ```  
    protected virtual IDictionary<XName,Object> MapValues (IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
     Die <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>-Methode stellt Funktionen bereit, die von <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> nicht bereitgestellt werden, und zwar im Hinblick darauf, dass sie eine Abhängigkeit von einem anderen Wert zulässt, der von einem anderen Persistenzteilnehmer bereitgestellt wird, der noch nicht von <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> verarbeitet wurde.  
  
4.  Implementieren der **PublishValues** Methode. Die **PublishValues** -Methode empfängt ein Wörterbuch mit den Werten, die aus dem persistenten Speicher geladen.  
  
    ```  
    protected virtual void PublishValues (IDictionary<XName,Object> readWriteValues)  
    ```  
  
5.  Implementieren der **BeginOnSave** Methode, wenn der Teilnehmer ein e/a-persistenzteilnehmer ist. Diese Methode wird während eines Save-Vorgangs aufgerufen. In dieser Methode müssen Sie zusätzlich zu den Workflowinstanzen für die persistente Speicherung E/A-Vorgänge ausführen.  Wenn der Host eine Transaktion für den entsprechenden Persistenzbefehl verwendet, wird die gleiche Transaktion in Transaction.Current bereitgestellt.  Darüber hinaus zeigen PersistenceIOParticipants möglicherweise eine Transaktionskonsistenzanforderung an. In diesem Fall erstellt der Host gegebenenfalls eine Transaktion für den Persistenzabschnitt.  
  
    ```  
    protected virtual IAsyncResult BeginOnSave (IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```  
  
6.  Implementieren der **BeginOnLoad** Methode, wenn der Teilnehmer ein e/a-persistenzteilnehmer ist. Diese Methode wird während eines Load-Vorgangs aufgerufen. In dieser Methode müssen Sie zusätzlich zum Laden von Workflowinstanzen E/A-Vorgänge ausführen. Wenn der Host eine Transaktion für den entsprechenden Persistenzbefehl verwendet, wird die gleiche Transaktion in Transaction.Current bereitgestellt. Darüber hinaus zeigen E/A-Persistenzteilnehmer möglicherweise eine Transaktionskonsistenzanforderung an. In diesem Fall erstellt der Host gegebenenfalls eine Transaktion für den Persistenzabschnitt.  
  
    ```  
    protected virtual IAsyncResult BeginOnLoad (IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```
