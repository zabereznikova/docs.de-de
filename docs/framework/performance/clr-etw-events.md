---
title: CLR-ETW-Ereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9d64ee6942d9397ceb45b812ef3c26179fac9b2b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540298"
---
# <a name="clr-etw-events"></a>CLR-ETW-Ereignisse
Die Themen in diesem Abschnitt beschreiben die Ereignisablaufverfolgung für Windows-Ereignisse (ETW). Jedes Ereignis verfügt über ein zugeordnetes Schlüsselwort und die Ebene, die im Thema [CLR-ETW-Schlüsselwörter und-Ebenen](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) beschrieben werden. Die CLR verfügt über zwei Anbieter für die Ereignisse:  
  
-   Der Laufzeitanbieter löst Ereignisse in Abhängigkeit von den aktivierten Schlüsselwörtern (Ereigniskategorien) aus. Die GUID des CLR-Laufzeitanbieters ist e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.  
  
-   Der Rundownanbieter, der für spezielle Zwecke genutzt werden kann. Die GUID des CLR-Rundownanbieters ist A669021C-C450-4609-A035-5AF59AF4DF18.  
  
 Weitere Informationen zu den Anbietern finden Sie unter [CLR-ETW-Anbieter](../../../docs/framework/performance/clr-etw-providers.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Laufzeitinformationsereignisse](../../../docs/framework/performance/runtime-information-etw-events.md)  
 Erfasst Informationen über die Laufzeit, einschließlich der SKU, der Versionsnummer, der Art der Aktivierung der Laufzeit, der Befehlszeilenparameter, mit denen sie gestartet wurde, der GUID (wenn zutreffend) und weiterer wichtiger Informationen.  
  
 [ExceptionThrown_V1-Ereignis](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 Erfasst Informationen über Ausnahmen, die ausgelöst wurden.  
  
 [Konfliktereignisse](../../../docs/framework/performance/contention-etw-events.md)  
 Erfasst Informationen über Konflikte bezüglich Überwachungssperren oder nativen Sperren, die von der Laufzeit verwendet werden.  
  
 [Threadpoolereignisse](../../../docs/framework/performance/thread-pool-etw-events.md)  
 Erfasst Informationen zu den Arbeitsthreadpools und den I/O-Threadpools.  
  
 [Ladeprogrammereignisse](../../../docs/framework/performance/loader-etw-events.md)  
 Erfasst Informationen zum Laden und Entladen von Anwendungsdomänen, Assemblys und Modulen.  
  
 [Methodenereignisse](../../../docs/framework/performance/method-etw-events.md)  
 Erfasst Informationen über CLR-Methoden für die Symbolauflösung.  
  
 [Garbage Collection-Ereignisse](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 Erfasst Informationen zur Garbage Collection, und hilft Ihnen bei der Diagnose und beim Debuggen.  
  
 [JIT-Ablaufverfolgungsereignisse](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 Erfasst Informationen über JIT-Inlining und Endeaufrufe.  
  
 [Interop-Ereignisse](../../../docs/framework/performance/interop-etw-events.md)  
 Erfasst Informationen über die Stubgenerierung und Zwischenspeicherung der Microsoft Intermediate Language (MSIL).  
  
 [ARM-Ereignisse](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 Erfasst detaillierte Diagnoseinformationen über den Status einer Anwendungsdomäne.  
  
 [Sicherheitsereignisse](../../../docs/framework/performance/security-etw-events.md)  
 Erfasst Informationen über starke Namen und Authenticodeüberprüfung.  
  
 [Stapelereignis](../../../docs/framework/performance/stack-etw-event.md)  
 Erfasst Informationen, die mit anderen Ereignissen zur Generierung von Stackablaufverfolgungen verwendet werden, nachdem ein Ereignis eingetreten ist.  
  
## <a name="see-also"></a>Siehe auch
- [Verbessertes Debugging und Leistungsoptimierung mit ETW](https://go.microsoft.com/fwlink/?LinkId=179696)
- [Windows Performance-Blog](https://go.microsoft.com/fwlink/?LinkId=179509)
- [Controlling .NET Framework Logging (Steuern der Protokollierung in .NET Framework)](../../../docs/framework/performance/controlling-logging.md)
- [CLR ETW Providers (CLR-ETW-Anbieter)](../../../docs/framework/performance/clr-etw-providers.md)
- [CLR ETW Keywords and Levels (CLR-ETW-Schlüsselwörter und -Ebenen)](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)
- [ETW-Ereignisse in der Common Language Runtime](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
