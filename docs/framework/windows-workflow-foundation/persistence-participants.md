---
title: Persistenzteilnehmer
ms.date: 03/30/2017
ms.assetid: f84d2d5d-1c1b-4f19-be45-65b552d3e9e3
ms.openlocfilehash: 0bff6cc8fafb1832dc4d0e33b754fe3adb81dcf6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96246107"
---
# <a name="persistence-participants"></a>Persistenzteilnehmer

Ein Persistenzteilnehmer kann an einem von einem Anwendungshost ausgelösten Persistenzvorgang (Speichern oder Laden) teilnehmen. Der [!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] wird mit zwei abstrakten Klassen, **persistenceteilnehmer** und **persistenceioparticipant**, ausgeliefert, die Sie zum Erstellen eines Dauerhaftigkeits Teilnehmers verwenden können. Ein Persistenzteilnehmer leitet sich von einer dieser Klassen ab, implementiert die passenden Methoden und fügt dann der <xref:System.ServiceModel.Activities.WorkflowServiceHost.WorkflowExtensions%2A>-Auflistung im <xref:System.ServiceModel.Activities.WorkflowServiceHost> eine Instanz der Klasse hinzu. Beim Beibehalten einer Workflowinstanz sucht der Anwendungshost möglicherweise nach Workflowerweiterungen dieser Art und ruft auf den Persistenzteilnehmern zur richtigen Zeit jeweils die entsprechenden Methoden auf.  
  
 In der folgenden Liste werden die Aufgaben beschrieben, die das Persistenzsubsystem in den einzelnen Phasen des Persistenzvorgangs (Speichern) ausführt. Die Persistenzteilnehmer werden in der dritten und vierten Phase verwendet. Wenn der Teilnehmer ein e/a-Teilnehmer ist (ein persistenzteilnehmer, der auch an e/a-Vorgängen teilnimmt), wird der Teilnehmer auch in der sechsten Phase verwendet.  
  
1. Erfasst integrierte Werte, einschließlich Workflowstatus, Lesezeichen, zugeordnete Variablen und Timestamps.  
  
2. Erfasst alle Persistenzteilnehmer, die der Erweiterungsauflistung mit Zuordnung zur Workflowinstanz hinzugefügt wurden.  
  
3. Ruft die <xref:System.Activities.Persistence.PersistenceParticipant.CollectValues%2A>-Methode auf, die von allen Persistenzteilnehmern implementiert wurde.  
  
4. Ruft die <xref:System.Activities.Persistence.PersistenceParticipant.MapValues%2A>-Methode auf, die von allen Persistenzteilnehmern implementiert wurde.  
  
5. Beibehalten oder Speichern des Workflows im persistenten Speicher.  
  
6. Ruft die- <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnSave%2A> Methode für alle Persistenz-e/a-Teilnehmer auf. Wenn der Teilnehmer kein e/a-Teilnehmer ist, wird diese Aufgabe übersprungen. Falls der Persistenzabschnitt transaktionsgebunden ist, wird die Transaktion in der Transaction.Current-Eigenschaft bereitgestellt.  
  
7. Wartet, bis die Vorgänge aller Persistenzteilnehmer abgeschlossen sind. Falls alle Teilnehmer das Beibehalten der Instanzdaten erfolgreich abschließen, wird für die Transaktion ein Commit ausgeführt.  
  
 Ein persistenzteilnehmer wird von der **PersistenceParticipants** -Klasse abgeleitet und kann die Methoden **CollectValues** und **mapvalues** implementieren. Ein e/A-persistenzteilnehmer wird von der **persistenceioparticipant** -Klasse abgeleitet und kann die **beginonsave** -Methode zusätzlich zur Implementierung der Methoden **CollectValues** und **mapvalues** implementieren.  
  
 Jede Phase wird abgeschlossen, bevor die nächste Phase beginnt. Beispielsweise werden Werte von **allen** persistenzteilnehmern in der ersten Phase gesammelt. Alle in der ersten Phase erfassten Werte werden in der zweiten Phase dann für alle Persistenzteilnehmer bereitgestellt, um die Zuordnung sicherzustellen. Alle in der ersten und zweiten Phase erfassten Werte werden dann für alle Persistenzteilnehmer in der dritten Phase bereitgestellt usw.  
  
 In der folgenden Liste werden die Aufgaben beschrieben, die das Persistenzsubsystem in den einzelnen Phasen des Ladevorgangs ausführt. Die Persistenzteilnehmer werden in der vierten Phase verwendet. Die e/a-persistenzteilnehmer (persistenzteilnehmer, die auch an e/a-Vorgängen teilnehmen) werden auch in der dritten Phase verwendet.  
  
1. Erfasst alle Persistenzteilnehmer, die der Erweiterungsauflistung mit Zuordnung zur Workflowinstanz hinzugefügt wurden.  
  
2. Lädt den Workflow aus dem Persistenzspeicher.  
  
3. Ruft den für <xref:System.Activities.Persistence.PersistenceIOParticipant.BeginOnLoad%2A> alle Persistenz-e/a-Teilnehmer auf und wartet darauf, dass alle persistenzteilnehmer beendet werden. Falls der Persistenzabschnitt transaktionsgebunden ist, wird die Transaktion in der Transaction.Current-Eigenschaft bereitgestellt.  
  
4. Lädt die Workflowinstanz basierend auf den aus dem Persistenzspeicher abgerufenen Daten in den Arbeitsspeicher.  
  
5. Ruft <xref:System.Activities.Persistence.PersistenceParticipant.PublishValues%2A> für jeden Persistenzteilnehmer auf.  
  
 Ein persistenzteilnehmer wird von der **PersistenceParticipants** -Klasse abgeleitet und kann die **publishvalues** -Methode implementieren. Ein e/A-persistenzteilnehmer wird von der **persistenceioparticipant** -Klasse abgeleitet und kann die **beginonload** -Methode zusätzlich zur Implementierung der **publishvalues** -Methode implementieren.  
  
 Beim Laden einer Workflowinstanz erstellt der Persistenzanbieter eine Sperre für diese Instanz. Dadurch wird verhindert, dass die Instanz in einem Szenario mit mehreren Knoten von mehr als einem Host geladen wird. Wenn Sie versuchen, eine gesperrte Workflowinstanz zu laden, wird eine mit der folgenden vergleichbare Ausnahme angezeigt: Die Ausnahme " System.ServiceModel.Persistence.InstanceLockException: Der angeforderte Vorgang konnte nicht abgeschlossen werden, da die Sperre für die Instanz '00000000-0000-0000-0000-000000000000' nicht abgerufen werden konnte". Dieser Fehler tritt auf, wenn eine der folgenden Situationen vorliegt:  
  
- In einem Szenario mit mehreren Knoten wird die Instanz von einem anderen Host geladen.  Es gibt mehrere Möglichkeiten, diese Art von Konflikten zu beheben: Leiten Sie die Verarbeitung an den Knoten weiter, der die Sperre besitzt, und wiederholen Sie den Vorgang, oder erzwingen Sie das Laden, wodurch der andere Host daran gehindert wird, die Arbeit zu speichern.  
  
- In einem Szenario mit einem einzelnen Knoten ist der Host abgestürzt.  Wenn der Host erneut gestartet wurde (durch die Wiederverwendung eines Prozesses oder die Erstellung einer neuen Persistenzanbieterfactory), versucht der neue Host, eine Instanz zu laden, die noch vom alten Host gesperrt ist, da die Sperre noch nicht abgelaufen ist.  
  
- In einem Szenario mit einem einzelnen Knoten wurde die betreffende Instanz zu einem bestimmten Zeitpunkt abgebrochen, und es wird eine neue Persistenzanbieterinstanz erstellt, die eine andere Host-ID aufweist.  
  
 Das Sperrtimeout hat einen Standardwert von 5 Minuten, Sie können beim Aufrufen von <xref:System.ServiceModel.Persistence.PersistenceProvider.Load%2A> einen anderen Timeoutwert angeben.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
- [Vorgehensweise: Erstellen eines benutzerdefinierten Persistenzteilnehmers](how-to-create-a-custom-persistence-participant.md)  
  
## <a name="see-also"></a>Weitere Informationen

- [Erweiterbarkeit des Speichers](store-extensibility.md)
