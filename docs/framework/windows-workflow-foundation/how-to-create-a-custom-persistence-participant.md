---
title: "Gewusst wie: Erstellen eines benutzerdefinierten Persistenzteilnehmers | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Gewusst wie: Erstellen eines benutzerdefinierten Persistenzteilnehmers
Die folgende Prozedur enthält die Schritte zur Erstellung eines Persistenzteilnehmers.Beispielimplementierungen von Persistenzteilnehmern finden Sie im Beispiel [Participating in Persistence](http://go.microsoft.com/fwlink/?LinkID=177735) und im Thema [Erweiterbarkeit des Speichers](../../../docs/framework/windows-workflow-foundation//store-extensibility.md).  
  
1.  Erstellen Sie eine von der <xref:System.Activities.Persistence.PersistenceParticipant>\-Klasse oder von der <xref:System.Activities.Persistence.PersistenceIOParticipant>\-Klasse abgeleitete Klasse.Die PersistenceIOParticipant\-Klasse bietet die gleichen Erweiterbarkeitspunkte wie die PersistenceParticipant\-Klasse und kann zusätzlich dazu in E\/A\-Vorgänge eingebunden werden.Führen Sie mindestens einen der folgenden Schritte aus.  
  
2.  Implementieren Sie die <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>\-Methode.Die **CollectValues**\-Methode verfügt über zwei Wörterbuchparameter, einen zum Speichern von Lese\-\/Schreibwerten und einen zum Speichern von lesegeschützten Werten \(wird später in Abfragen verwendet\).In dieser Methode müssen Sie diese Wörterbücher mit Daten auffüllen, die für einen Persistenzteilnehmer spezifisch sind.Jedes Wörterbuch enthält den Namen des Werts als Schlüssel und den Wert selbst als <xref:System.Runtime.DurableInstancing.InstanceValue>\-Objekt.  
  
     Die Werte im readWriteValues\-Wörterbuch werden als **InstanceValue**\-Objekte gepackt.Die Werte im lesegeschützten Wörterbuch werden als **InstanceValue**\-Objekte gepackt, wobei InstanceValueOptions.Optional und InstanceValueOption.WriteOnly festgelegt sind.Jedes **InstanceValue**\-Objekt, das von den **CollectValues**\-Implementierungen für die einzelnen Persistenzteilnehmer bereitgestellt wird, muss über einen eindeutigen Namen verfügen.  
  
    ```  
    protected virtual void CollectValues (out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)  
  
    ```  
  
3.  Implementieren Sie die <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>\-Methode.Die **MapValues**\-Methode akzeptiert zwei Parameter, die den Parametern für die **CollectValues**\-Methode ähneln.Alle in der **CollectValues**\-Phase gesammelten Werte werden über diese Wörterbuchparameter übergeben.Den lesegeschützten Werten werden die neuen von der **MapValues**\-Phase hinzugefügten Werte hinzugefügt.Das lesegeschützte Wörterbuch wird verwendet, um Daten für eine externe Quelle bereitzustellen, nicht direkt den Instanzwerten zugeordnet ist.Jeder von Implementierungen der **MapValues**\-Methode bereitgestellte Wert für alle Persistenzteilnehmer muss über einen eindeutigen Namen verfügen.  
  
    ```  
    protected virtual IDictionary<XName,Object> MapValues (IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)  
    ```  
  
     Die <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>\-Methode stellt Funktionen bereit, die <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> nicht bereitgestellt werden, und zwar im Hinblick darauf, dass sie eine Abhängigkeit von einem anderen Wert zulässt, der von einem anderen Persistenzteilnehmer bereitgestellt wird, der noch nicht durch <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> verarbeitet wurde.  
  
4.  Implementieren Sie die **PublishValues**\-Methode.Die **PublishValues**\-Methode empfängt ein Wörterbuch, das alle aus dem Persistenzspeicher geladenen Werte enthält.  
  
    ```  
    protected virtual void PublishValues (IDictionary<XName,Object> readWriteValues)  
  
    ```  
  
5.  Implementieren Sie die **BeginOnSave**\-Methode, falls der Teilnehmer ein E\/A\-Persistenzteilnehmer ist.Diese Methode wird während eines Save\-Vorgangs aufgerufen.In dieser Methode müssen Sie zusätzlich zu den Workflowinstanzen für die persistente Speicherung E\/A\-Vorgänge ausführen.Wenn der Host eine Transaktion für den entsprechenden Persistenzbefehl verwendet, wird die gleiche Transaktion in Transaction.Current bereitgestellt.Darüber hinaus zeigen PersistenceIOParticipants möglicherweise eine Transaktionskonsistenzanforderung an. In diesem Fall erstellt der Host gegebenenfalls eine Transaktion für den Persistenzabschnitt.  
  
    ```  
  
    protected virtual IAsyncResult BeginOnSave (IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)  
    ```  
  
6.  Implementieren Sie die **BeginOnLoad**\-Methode, falls der Teilnehmer ein E\/A\-Persistenzteilnehmer ist.Diese Methode wird während eines Load\-Vorgangs aufgerufen.In dieser Methode müssen Sie zusätzlich zum Laden von Workflowinstanzen E\/A\-Vorgänge ausführen.Wenn der Host eine Transaktion für den entsprechenden Persistenzbefehl verwendet, wird die gleiche Transaktion in Transaction.Current bereitgestellt.Darüber hinaus zeigen E\/A\-Persistenzteilnehmer möglicherweise eine Transaktionskonsistenzanforderung an. In diesem Fall erstellt der Host gegebenenfalls eine Transaktion für den Persistenzabschnitt.  
  
    ```  
  
    protected virtual IAsyncResult BeginOnLoad (IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)  
  
    ```