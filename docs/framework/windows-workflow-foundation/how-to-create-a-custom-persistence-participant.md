---
title: 'Vorgehensweise: Erstellen eines benutzerdefinierten Persistenzteilnehmers'
ms.date: 03/30/2017
ms.assetid: 1d9cc47a-8966-4286-94d5-4221403d9c06
ms.openlocfilehash: d1d59f139b666790920eaabe032878dca1617b62
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90557044"
---
# <a name="how-to-create-a-custom-persistence-participant"></a>Vorgehensweise: Erstellen eines benutzerdefinierten Persistenzteilnehmers
Die folgende Prozedur enthält die Schritte zur Erstellung eines Persistenzteilnehmers. Beispiele für Implementierungen von persistenzteilnehmern finden Sie im Thema zum [teilnehmen an](/previous-versions/dotnet/netframework-4.0/dd699769(v=vs.100)) Dauerhaftigkeits Beispielen und zum [Speichern der Erweiterbarkeit](store-extensibility.md) .  
  
1. Erstellen Sie eine von der <xref:System.Activities.Persistence.PersistenceParticipant>-Klasse oder von der <xref:System.Activities.Persistence.PersistenceIOParticipant>-Klasse abgeleitete Klasse. Die persistenceioparticipant-Klasse bietet die gleichen Erweiterbarkeits Punkte wie die PersistenceParticipants-Klasse und kann an e/a-Vorgängen teilnehmen. Führen Sie mindestens einen der folgenden Schritte aus.  
  
2. Implementieren Sie die <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>-Methode. Die **CollectValues** -Methode verfügt über zwei Wörterbuch Parameter, eine für das Speichern von Lese-/schreibwerten und die andere für das Speichern von schreibgeschützten Werten (wird später in Abfragen verwendet). In dieser Methode müssen Sie diese Wörterbücher mit Daten auffüllen, die für einen Persistenzteilnehmer spezifisch sind. Jedes Wörterbuch enthält den Namen des Werts als Schlüssel und den Wert selbst als <xref:System.Runtime.DurableInstancing.InstanceValue>-Objekt.  
  
    Die Werte im Read Write Items-Wörterbuch werden als **InstanceValue** -Objekte verpackt. Die Werte im schreibgeschützten Wörterbuch werden als **InstanceValue** -Objekte verpackt, wobei InstanceValueOptions. optional und instancevalueoption. Write-only festgelegt sind. Jeder **InstanceValue** , der von den **CollectValues** -Implementierungen für alle persistenzteilnehmer bereitgestellt wird, muss einen eindeutigen Namen aufweisen.
  
    ```csharp  
    protected virtual void CollectValues(out IDictionary<XName,Object> readWriteValues, out IDictionary<XName,Object> writeOnlyValues)
    {
    }
    ```  
  
3. Implementieren Sie die <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>-Methode. Die **mapvalues** -Methode nimmt zwei Parameter an, die mit den Parametern vergleichbar sind, die von der **CollectValues** -Methode empfangen werden. Alle Werte, die in der **CollectValues** -Phase gesammelt werden, werden durch diese Wörterbuch Parameter übergeben. Die neuen Werte, die von der **mapvalues** -Phase hinzugefügt werden, werden den schreibgeschützten Werten hinzugefügt.  Das lesegeschützte Wörterbuch wird verwendet, um Daten für eine externe Quelle bereitzustellen, die nicht direkt den Instanzwerten zugeordnet ist. Jeder Wert, der von Implementierungen der **mapvalues** -Methode für alle persistenzteilnehmer bereitgestellt wird, muss über einen eindeutigen Namen verfügen.  
  
    ```csharp  
    protected virtual IDictionary<XName,Object> MapValues(IDictionary<XName,Object> readWriteValues,IDictionary<XName,Object> writeOnlyValues)
    {
    }
    ```  
  
     Die <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>-Methode stellt Funktionen bereit, die von <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> nicht bereitgestellt werden, und zwar im Hinblick darauf, dass sie eine Abhängigkeit von einem anderen Wert zulässt, der von einem anderen Persistenzteilnehmer bereitgestellt wird, der noch nicht von <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A> verarbeitet wurde.  
  
4. Implementieren Sie die **publishvalues** -Methode. Die **publishvalues** -Methode empfängt ein Wörterbuch mit allen Werten, die aus dem Persistenzspeicher geladen wurden.  
  
    ```csharp  
    protected virtual void PublishValues(IDictionary<XName,Object> readWriteValues)
    {
    }
    ```  
  
5. Implementieren Sie die **beginonsave** -Methode, wenn der Teilnehmer ein e/a-persistenzteilnehmer ist. Diese Methode wird während eines Save-Vorgangs aufgerufen. In dieser Methode sollten Sie einen e/a-Ergänzung für die beibehaltenen (Speicherungs) Workflow Instanzen durchführen.  Wenn der Host eine Transaktion für den entsprechenden Persistenzbefehl verwendet, wird die gleiche Transaktion in Transaction.Current bereitgestellt.  Darüber hinaus zeigen PersistenceIOParticipants möglicherweise eine Transaktionskonsistenzanforderung an. In diesem Fall erstellt der Host gegebenenfalls eine Transaktion für den Persistenzabschnitt.  
  
    ```csharp  
    protected virtual IAsyncResult BeginOnSave(IDictionary<XName,Object> readWriteValues, IDictionary<XName,Object> writeOnlyValues, TimeSpan timeout, AsyncCallback callback, Object state)
    {
    }
    ```  
  
6. Implementieren Sie die **beginonload** -Methode, wenn der Teilnehmer ein e/a-persistenzteilnehmer ist. Diese Methode wird während eines Load-Vorgangs aufgerufen. In dieser Methode sollten Sie einen e/a-Ergänzung-Befehl zum Laden von Workflow Instanzen durchführen. Wenn der Host eine Transaktion für den entsprechenden Persistenzbefehl verwendet, wird die gleiche Transaktion in Transaction.Current bereitgestellt. Außerdem kann es sein, dass persistenze/a-Teilnehmer eine transaktionale Konsistenz Anforderung ankündigen. in diesem Fall erstellt der Host eine Transaktion für die persistenzfolge, wenn nichts anderweitig verwendet würde.  
  
    ```csharp  
    protected virtual IAsyncResult BeginOnLoad(IDictionary<XName,Object> readWriteValues, TimeSpan timeout, AsyncCallback callback, Object state)
    {
    }
    ```
