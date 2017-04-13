---
title: "CLR ETW Events | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CLR ETW events"
  - "ETW, common language runtime"
  - "ETW, CLR events"
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
caps.latest.revision: 45
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 45
---
# CLR ETW Events
In den Themen dieses Abschnitts werden ETW \(Event Tracing for Windows, Ereignisablaufverfolgung für Windows\)\-Ereignisse beschrieben.  Jedes Ereignis verfügt über ein zugeordnetes Schlüsselwort und eine Ebene, die im Thema [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) beschrieben sind.  Die CLR verfügt über zwei Anbieter für die Ereignisse:  
  
-   Den Laufzeitanbieter, der Ereignisse in Abhängigkeit von den aktivierten Schlüsselwörtern \(Ereigniskategorien\) auslöst.  Die GUID des CLR\-Laufzeitanbieters ist e13c0d23\-ccbc\-4e12\-931b\-d9cc2eee27e4.  
  
-   Den Rundownanbieter, der zweckgebunden verwendet wird.  Die GUID des CLR\-Rundownanbieters lautet a669021c\-c450\-4609\-a035\-5af59af4df18.  
  
 Weitere Informationen zu den Anbietern finden Sie unter [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md).  
  
## In diesem Abschnitt  
 [Runtime Information Events](../../../docs/framework/performance/runtime-information-etw-events.md)  
 Erfasst Informationen zur Laufzeit, u. a. SKU, Versionsnummer, die Methode, mit der die Laufzeit aktiviert wurde, die Befehlszeilenparameter, mit denen sie gestartet wurde, die GUID \(sofern zutreffend\) und weitere relevante Informationen.  
  
 [Exception Thrown\_V1 Event](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 Erfasst Informationen zu ausgelösten Ausnahmen.  
  
 [Contention Events](../../../docs/framework/performance/contention-etw-events.md)  
 Erfasst Informationen zu Konflikten für Monitorsperren oder systemeigene Sperren, die die Laufzeit verwendet.  
  
 [Thread Pool Events](../../../docs/framework/performance/thread-pool-etw-events.md)  
 Erfasst Informationen zu Arbeitsthreadpools und E\/A\-Threadpools.  
  
 [Loader Events](../../../docs/framework/performance/loader-etw-events.md)  
 Erfasst Informationen zum Laden und Entladen von Anwendungsdomänen, Assemblys und Modulen.  
  
 [Method Events](../../../docs/framework/performance/method-etw-events.md)  
 Erfasst Informationen zu CLR\-Methoden für die Symbolauflösung.  
  
 [Garbage Collection Events](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 Erfasst Informationen zur Garbage Collection, um Diagnosen und Debugging zu erleichtern.  
  
 [JIT Tracing Events](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 Erfasst Informationen zum JIT \(Just\-In\-Time\)\-Inlining und zu JIT\-Endeaufrufen.  
  
 [Interop Events](../../../docs/framework/performance/interop-etw-events.md)  
 Erfasst Informationen zur MSIL \(Microsoft Intermediate Language\)\-Stubgenerierung und \-Zwischenspeicherung.  
  
 [ARM Events](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 Erfasst ausführliche Diagnoseinformationen zum Zustand einer Anwendungsdomäne.  
  
 [Security Events](../../../docs/framework/performance/security-etw-events.md)  
 Erfasst Informationen zur Überprüfung starker Namen und von Authenticode.  
  
 [Stack Event](../../../docs/framework/performance/stack-etw-event.md)  
 Erfasst für andere Ereignisse verwendete Informationen, um nach dem Auslösen eines Ereignisses Stapelüberwachungen zu generieren.  
  
## Siehe auch  
 [Bessere Debuggen und Leistungsoptimierung mit ETW](http://go.microsoft.com/fwlink/?LinkId=179696)   
 [Windows\-Leistungs\-Blog](http://go.microsoft.com/fwlink/?LinkId=179509)   
 [Controlling .NET Framework Logging](../../../docs/framework/performance/controlling-logging.md)   
 [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md)   
 [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)   
 [ETW Events in the Common Language Runtime](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)