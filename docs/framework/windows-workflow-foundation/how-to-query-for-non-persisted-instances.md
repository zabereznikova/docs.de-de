---
title: 'Vorgehensweise: Abfragen von nicht persistenten Instanzen'
ms.date: 03/30/2017
ms.assetid: 294019b1-c1a7-4b81-a14f-b47c106cd723
ms.openlocfilehash: 54a442dab6700dda33cf05df1fb5c60a96bcbd56
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96279999"
---
# <a name="how-to-query-for-non-persisted-instances"></a>Vorgehensweise: Abfragen von nicht persistenten Instanzen

Wenn eine neue Dienstinstanz erstellt wird und für den Dienst das SQL-Workflowinstanzspeicher-Verhalten definiert ist, erstellt der Diensthost einen ersten Eintrag für diese Dienstinstanz im Instanzspeicher. Bei der ersten permanenten Speicherung der Dienstinstanz speichert das SQL-Workflowinstanzspeicher-Verhalten den aktuellen Instanzstatus zusammen mit weiteren Daten, die zur Aktivierung, Wiederherstellung und Steuerung erforderlich sind.

Wenn eine Instanz nach dem Erstellen des ersten Eintrags nicht permanent gespeichert wird, ist der Status der Instanz "nicht permanent". Alle permanent gespeicherten Dienstinstanzen können abgefragt und gesteuert werden. Nicht permanente Dienstinstanzen können weder abgefragt noch gesteuert werden. Wenn eine nicht permanente Instanz aufgrund einer nicht behandelten Ausnahme angehalten wird, kann diese abgefragt, jedoch nicht gesteuert werden.

Permanente Dienstinstanzen, die noch nicht persistent gespeichert wurden, behalten in den folgenden Szenarios den Status "nicht persistent":

- Der Diensthost stürzt ab, bevor die Instanz zum ersten Mal persistent gespeichert wurde. Der ursprüngliche Eintrag für die Instanz verbleibt im Instanzspeicher. Die Instanz ist nicht wiederherstellbar. Bei Empfang einer korrelierten Meldung wird die Instanz erneut aktiviert.

- Es tritt eine nicht behandelte Ausnahme auf, bevor die Instanz zum ersten Mal persistent gespeichert wurde. Die folgenden Szenarios treten auf:

  - Wenn der Wert der **unlenker dexceptionaction** -Eigenschaft auf verwerfen festgelegt **ist, werden** die Dienst Bereitstellungs Informationen in den Instanzspeicher geschrieben, und die Instanz wird aus dem Arbeitsspeicher entladen. Die Instanz verbleibt in der Persistenzdatenbank im nicht persistenten Status.

  - Wenn der Wert der **untordexceptionaction** -Eigenschaft auf **abandonandsuspend** festgelegt ist, werden die Dienst Bereitstellungs **Informationen in die** Persistenzdatenbank geschrieben, und der Instanzstatus wird auf "angehalten" festgelegt. Die Instanz kann nicht fortgesetzt, abgebrochen oder beendet werden. Der Diensthost kann die Instanz nicht laden, da die Instanz noch nicht persistent gespeichert wurde, d. h. der Datenbankeintrag für die Instanz ist noch nicht abgeschlossen.

  - Wenn der Wert der **untordexceptionaction** -Eigenschaft auf **Abbrechen** oder **Beenden** festgelegt ist, werden die Dienst Bereitstellungs Informationen in den Instanzspeicher geschrieben, und der Instanzstatus wird auf **abgeschlossen** festgelegt.

Die folgenden Abschnitte enthalten Beispielabfragen zur Suche von nicht persistenten Instanzen in der SQL-Persistenzdatenbank und zum Löschen dieser Instanzen aus der Datenbank.

## <a name="to-find-all-instances-not-persisted-yet"></a>So suchen Sie nach allen noch nicht persistenten Instanzen

Die folgende SQL-Abfrage gibt die ID und den Erstellungszeitpunkt für alle Instanzen zurück, die noch nicht persistent in der Persistenzdatenbank gespeichert wurden.

```sql
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0;
```

## <a name="to-find-all-instances-not-persisted-yet-and-also-not-loaded"></a>So suchen Sie nach allen noch nicht persistenten und nicht geladenen Instanzen

 Die folgende SQL-Abfrage gibt die ID und den Erstellungszeitpunkt für alle Instanzen zurück, die nicht persistent gespeichert und auch nicht geladen wurden.

```sql
select InstanceId, CreationTime from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and CurrentMachine is NULL;
```

## <a name="to-find-all-suspended-instances-not-persisted-yet"></a>So suchen Sie nach allen angehaltenen noch nicht persistenten Instanzen

Die folgende SQL-Abfrage gibt die ID, den Erstellungszeitpunkt, den Unterbrechungsgrund und den Namen der Unterbrechungsausnahme für alle Instanzen an, die nicht persistent sind und angehalten wurden.

```sql
select InstanceId, CreationTime, SuspensionReason, SuspensionExceptionName from [System.Activities.DurableInstancing].[Instances] where IsInitialized = 0 and IsSuspended = 1;
```

## <a name="to-delete-non-persisted-instances-from-the-persistence-database"></a>So löschen Sie nicht persistente Instanzen aus der Persistenzdatenbank

Es wird empfohlen, den Instanzspeicher in regelmäßigen Abständen auf nicht persistente Instanzen zu überprüfen und diese aus dem Instanzspeicher zu entfernen, wenn Sie sicher sind, dass die Instanz keine korrelierte Meldung empfangen wird. Beispiel: Wenn eine Instanz sich bereits mehrere Monate in der Datenbank befindet und Sie wissen, dass der Workflow in der Regel eine Lebensdauer von einigen Tagen hat, können Sie sicher annehmen, dass es sich um eine nicht initialisierte Instanz handelt, die abgestürzt ist.

Im Allgemeinen ist es sicher, nicht persistente Instanzen zu löschen, die nicht angehalten oder geladen wurden. Sie sollten nicht **alle** nicht beibehaltenen Instanzen löschen, da dieser Instanzsatz Instanzen enthält, die gerade erstellt, aber noch nicht persistent gespeichert wurden. Löschen Sie nur nicht persistente Instanzen, die nicht mehr verwendet werden können, da beim Laden der Instanz durch den Workflowdiensthost oder durch die Instanz selbst eine Ausnahme ausgelöst wurde.

> [!WARNING]
> Durch das Löschen nicht persistenter Instanzen aus dem Instanzspeicher wird weniger Speicher belegt und die Leistung von Speichervorgängen möglicherweise verbessert.
