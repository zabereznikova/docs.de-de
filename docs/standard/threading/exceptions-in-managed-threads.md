---
title: Ausnahmen in verwalteten Threads
description: Informationen zur Verarbeitung von Ausnahmefehlern in .NET Die meisten Ausnahmefehler in Threads werden ordnungsgemäß fortgesetzt und führen zu einem Anwendungsabbruch.
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- unhandled exceptions,in managed threads
- threading [.NET],unhandled exceptions
- threading [.NET],exceptions in managed threads
- managed threading
ms.assetid: 11294769-2e89-43cb-890e-ad4ad79cfbee
ms.openlocfilehash: b7cf7e94156eedc82c7ec5c863ee013b75d22e73
ms.sourcegitcommit: 7588b1f16b7608bc6833c05f91ae670c22ef56f8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2020
ms.locfileid: "93188327"
---
# <a name="exceptions-in-managed-threads"></a>Ausnahmen in verwalteten Threads

Die Common Language Runtime lässt bei den meisten Ausnahmefehlern in Threads deren ordnungsgemäße Fortsetzung zu. Das für i. d R. dazu, dass die Anwendung durch die unbehandelte Ausnahme beendet wird.
  
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
  
## <a name="change-from-previous-versions"></a>Änderung im Vergleich zu früheren Versionen

In den .NET Framework-Versionen 1.0 und 1.1 stellt die Common Language Runtime für Ausnahmefehler in den folgenden Situationen ein Sicherheitsnetz bereit:  
  
- In einem Threadpoolthread gibt es keine unbehandelten Ausnahmen. Wenn eine Aufgabe eine Ausnahme auslöst, die sie nicht behandelt, gibt die Laufzeit die Ausnahmestapelüberwachung an die Konsole aus, und gibt den Thread an den Threadpool zurück.  
  
- In einem Thread, der mit der <xref:System.Threading.Thread.Start%2A>-Methode der <xref:System.Threading.Thread>-Klasse behandelt wird, gibt es keine unbehandelten Ausnahmen. Wenn Code, der in einem derartigen Thread ausgeführt wird, eine Ausnahme auslöst, die er nicht behandelt, gibt die Laufzeit die Ausnahmestapelüberwachung an die Konsole aus und beendet den Thread dann ordnungsgemäß.  
  
- In einem Finalizerthread gibt keine unbehandelten Ausnahmen. Wenn ein Finalizer eine Ausnahme auslöst, die er nicht behandelt, gibt die Laufzeit die Ausnahmestapelüberwachung an die Konsole aus und lässt den Finalizerthread dann die Ausführung von Finalizern fortsetzen.  
  
 Der Vordergrund- oder Hintergrundstatus eines verwalteten Threads beeinflusst dieses Verhalten nicht.  
  
 Bei unbehandelten Ausnahmen in Threads, die aus nicht verwaltetem Code stammen, ist der Unterschied feiner. Das Dialogfeld des an einen Prozess angefügten JIT hat bei verwalteten Ausnahmen oder systemeigenen Ausnahmen in Threads, die durch systemeigenen Code übergeben wurden, Vorrang vor dem Dialogfeld des Betriebssystems. Der Prozess wird in allen Fällen beendet.

### <a name="migration"></a>Migration

Wenn Sie von .NET Framework 1.0 oder 1.1 migrieren und das Runtime-Sicherheitsnetz ausgenutzt haben (z. B. zum Beenden von Threads), ziehen Sie eine der folgenden Migrationsstrategien in Betracht:  
  
- Strukturieren Sie den Code so um, dass der Thread beim Empfang eines Signals ordnungsgemäß beendet wird.  
  
- Verwenden Sie die <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>-Methode, um den Thread abzubrechen.  
  
- Wenn ein Thread angehalten werden muss, um die Prozessbeendigung fortzusetzen, machen Sie den Thread zu einem Hintergrundthread, damit er beim Prozessende automatisch beendet wird.  
  
Sie sollten dabei auf jeden die Entwurfsrichtlinien für Ausnahmen einhalten. Siehe [Entwurfsrichtlinien für Ausnahmen](../design-guidelines/exceptions.md).  
  
Administratoren können als vorübergehende Kompatibilitätsmaßnahme im `<runtime>`-Abschnitt der Anwendungskonfigurationsdatei ein Kompatibilitätsflag angeben. Dadurch wird die Common Language Runtime auf das Verhalten der Versionen 1.0 und 1.1 zurückgesetzt.  
  
```xml  
<legacyUnhandledExceptionPolicy enabled="1"/>  
```  
  
## <a name="host-override"></a>Hostüberschreibung

Ein nicht verwalteter Host kann über die [ICLRPolicyManager](../../framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)-Schnittstelle in der Hosting-API die Standardrichtlinie für Ausnahmefehler der Common Language Runtime überschreiben. Die [ICLRPolicyManager::SetUnhandledExceptionPolicy](../../framework/unmanaged-api/hosting/iclrpolicymanager-setunhandledexceptionpolicy-method.md)-Funktion wird zum Festlegen der Richtlinie für unbehandelte Ausnahmen verwendet.  
  
## <a name="see-also"></a>Siehe auch

- [Grundlagen des verwalteten Threadings](managed-threading-basics.md)
