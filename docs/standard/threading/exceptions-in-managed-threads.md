---
title: Ausnahmen in verwalteten Threads
description: Informationen zur Verarbeitung von Ausnahmefehlern in .NET Bei .NET-Version 2.0 werden die meisten Ausnahmefehler für Threads auf ordnungsgemäße Weise fortgesetzt und führen zu einem Anwendungsabbruch.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- unhandled exceptions,in managed threads
- threading [.NET Framework],unhandled exceptions
- threading [.NET Framework],exceptions in managed threads
- managed threading
ms.assetid: 11294769-2e89-43cb-890e-ad4ad79cfbee
ms.openlocfilehash: 2facb68c77815de7a6fb97ab8f2ee683ffbad724
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/15/2020
ms.locfileid: "84767883"
---
# <a name="exceptions-in-managed-threads"></a>Ausnahmen in verwalteten Threads
Ab .NET Framework, Version 2.0, erlaubt die Common Language Runtime bei den meisten Ausnahmefehlern in Threads deren ordnungsgemäße Fortsetzung. Das für i. d R. dazu, dass die Anwendung durch die unbehandelte Ausnahme beendet wird.  
  
> [!NOTE]
> Dies ist eine wichtige Änderung im Vergleich zu den .NET Framework-Versionen 1.0 und 1.1, die für zahlreiche unbehandelte Ausnahmen ein Sicherheitsnetz bereitstellen, z. B. für unbehandelte Ausnahmen in Threadpoolthreads. Weitere Informationen finden Sie später in diesem Thema unter [Änderung von früheren Versionen](#ChangeFromPreviousVersions).  
  
 Die Common Language Runtime stellt für bestimmte unbehandelte Ausnahmen, die zum Steuern des Programmablaufs verwendet werden, ein Sicherheitsnetz bereit:  
  
- In einem Thread wird eine <xref:System.Threading.ThreadAbortException> ausgelöst, da <xref:System.Threading.Thread.Abort%2A> aufgerufen wurde.  
  
- In einem Thread wird eine <xref:System.AppDomainUnloadedException> ausgelöst, da die Anwendungsdomäne, in der der Thread ausgeführt wird, entladen wird.  
  
- Die Common Language Runtime oder ein Hostprozess beendet den Thread durch Auslösen einer internen Ausnahme.  
  
 Wenn eine dieser Ausnahmen in Threads, die von der Common Language Runtime erstellt wurden, nicht behandelt werden, beendet die Ausnahme den Thread, die Common Language Runtime lässt jedoch die Weiterreichung der Ausnahme nicht zu.  
  
 Wenn diese Ausnahmen im Hauptthread oder in Threads, die von nicht verwaltetem Code in die Laufzeit eintreten, nicht behandelt werden, werden sie normal fortgesetzt, d. h., sie beenden die Anwendung.  
  
> [!NOTE]
> Die Laufzeit kann eine unbehandelte Ausnahme auslösen, bevor verwalteter Code einen Ausnahmehandler installieren kann. Auch wenn verwalteter Code eine derartige Ausnahme nicht behandeln könnte, kann die Ausnahme normal fortgesetzt werden.  
  
## <a name="exposing-threading-problems-during-development"></a>Aufdecken von Threadingproblemen bei der Entwicklung  
 Wenn Threads unerkannt fehlschlagen können, ohne die Anwendung zu beenden, können Sie gravierende Programmierfehler übersehen. Dies ist insbesondere bei Diensten und anderen Anwendungen ein Problem, die über einen längeren Zeitraum ausgeführt werden. Durch das Fehlschlagen von Threads wird der Programmzustand allmählich beschädigt. Dadurch kann sich die Anwendungsleistung verschlechtern, und es kann passieren, dass die Anwendung nicht mehr reagiert.  
  
 Wenn Sie die normale Fortsetzung von unbehandelten Ausnahmen in Threads zulassen, bis das Programm vom Betriebssystem beendet wird, werden derartige Probleme bei der Entwicklung und beim Testen entdeckt. Fehlerberichte über Beendigungen des Programms unterstützen das Debuggen.  
  
<a name="ChangeFromPreviousVersions"></a>
## <a name="change-from-previous-versions"></a>Änderung von früheren Versionen  
 Die wichtigste Änderung betrifft verwaltete Threads. In den .NET Framework-Versionen 1.0 und 1.1 stellt die Common Language Runtime für unbehandelte Ausnahmen in den folgenden Situationen ein Sicherheitsnetz bereit:  
  
- In einem Threadpoolthread gibt es keine unbehandelten Ausnahmen. Wenn eine Aufgabe eine Ausnahme auslöst, die sie nicht behandelt, gibt die Laufzeit die Ausnahmestapelüberwachung an die Konsole aus, und gibt den Thread an den Threadpool zurück.  
  
- In einem Thread, der mit der <xref:System.Threading.Thread.Start%2A>-Methode der <xref:System.Threading.Thread>-Klasse behandelt wird, gibt es keine unbehandelten Ausnahmen. Wenn Code, der in einem derartigen Thread ausgeführt wird, eine Ausnahme auslöst, die er nicht behandelt, gibt die Laufzeit die Ausnahmestapelüberwachung an die Konsole aus und beendet den Thread dann ordnungsgemäß.  
  
- In einem Finalizerthread gibt keine unbehandelten Ausnahmen. Wenn ein Finalizer eine Ausnahme auslöst, die er nicht behandelt, gibt die Laufzeit die Ausnahmestapelüberwachung an die Konsole aus und lässt den Finalizerthread dann die Ausführung von Finalizern fortsetzen.  
  
 Der Vordergrund- oder Hintergrundstatus eines verwalteten Threads beeinflusst dieses Verhalten nicht.  
  
 Bei unbehandelten Ausnahmen in Threads, die aus nicht verwaltetem Code stammen, ist der Unterschied feiner. Das Dialogfeld des an einen Prozess angefügten JIT hat bei verwalteten Ausnahmen oder systemeigenen Ausnahmen in Threads, die durch systemeigenen Code übergeben wurden, Vorrang vor dem Dialogfeld des Betriebssystems. Der Prozess wird in allen Fällen beendet.  
  
### <a name="migrating-code"></a>Migrieren von Code  
 Die Änderung deckt im Allgemeinen zuvor unerkannte Programmierfehler auf, sodass diese behoben werden können. In einigen Fällen war das Sicherheitsnetz der Laufzeit jedoch für Programmierer praktisch, z. B. zum Beenden von Threads. Je nach Situation bietet sich eine der folgenden Migrationsstrategien an:  
  
- Strukturieren Sie den Code so um, dass der Thread beim Empfang eines Signals ordnungsgemäß beendet wird.  
  
- Verwenden Sie die <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>-Methode, um den Thread abzubrechen.  
  
- Wenn ein Thread angehalten werden muss, um die Prozessbeendigung fortzusetzen, machen Sie den Thread zu einem Hintergrundthread, damit er beim Prozessende automatisch beendet wird.  
  
 Sie sollten dabei auf jeden die Entwurfsrichtlinien für Ausnahmen einhalten. Siehe [Entwurfsrichtlinien für Ausnahmen](../design-guidelines/exceptions.md).  
  
### <a name="application-compatibility-flag"></a>Anwendungskompatibilitätsflag  
 Administratoren können als vorübergehende Kompatibilitätsmaßnahme im `<runtime>`-Abschnitt der Anwendungskonfigurationsdatei ein Kompatibilitätsflag angeben. Dadurch wird die Common Language Runtime auf das Verhalten der Versionen 1.0 und 1.1 zurückgesetzt.  
  
```xml  
<legacyUnhandledExceptionPolicy enabled="1"/>  
```  
  
## <a name="host-override"></a>Hostüberschreibung  
 In .NET Framework, Version 2.0, kann ein nicht verwalteter Host über die [ICLRPolicyManager](../../framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)-Schnittstelle in der Hosting-API die Standardrichtlinie für unbehandelte Ausnahmen der Common Language Runtime überschreiben. Die [ICLRPolicyManager::SetUnhandledExceptionPolicy](../../framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)-Funktion wird zum Festlegen der Richtlinie für unbehandelte Ausnahmen verwendet.  
  
## <a name="see-also"></a>Siehe auch

- [Grundlagen des verwalteten Threadings](managed-threading-basics.md)
