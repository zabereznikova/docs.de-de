---
title: "Mutexes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "wait handles"
  - "threading [.NET Framework], Mutex class"
  - "Mutex class, about Mutex class"
  - "threading [.NET Framework], cross-process synchronization"
ms.assetid: 9dd06e25-12c0-4a9e-855a-452dc83803e2
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# Mutexes
Sie können ein <xref:System.Threading.Mutex>\-Objekt verwenden, um exklusiven Zugriff auf eine Ressource bereitzustellen.  Die <xref:System.Threading.Mutex>\-Klasse verwendet mehr Systemressourcen als die <xref:System.Threading.Monitor>\-Klasse, sie kann jedoch über Anwendungsdomänengrenzen hinweg gemarshallt, mit mehreren Wartevorgängen verwendet sowie zur Synchronisierung von Threads in verschiedenen Prozessen verwendet werden.  Ein Vergleich der verwalteten Synchronisierungsmechanismen finden Sie unter [Overview of Synchronization Primitives](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Codebeispiele finden Sie in der Referenzdokumentation für die <xref:System.Threading.Mutex.%23ctor%2A>\-Konstruktoren.  
  
## Verwenden von Mutexen  
 Ein Thread ruft die <xref:System.Threading.WaitHandle.WaitOne%2A>\-Methode eines Mutex auf, um dessen Besitz anzufordern.  Der Aufruf wird blockiert, bis der Mutex verfügbar ist oder bis das optionale Timeoutintervall abgelaufen ist.  Der Zustand eines Mutex wird signalisiert, wenn er nicht in Besitz eines Threads ist.  
  
 Ein Thread gibt einen Mutex frei, indem er seine <xref:System.Threading.Mutex.ReleaseMutex%2A>\-Methode aufruft.  Mutexe weisen Threadaffinität auf. Sie können nur von einem Thread freigegeben werden, in dessen Besitz sie sich befinden.  Wenn ein Thread einen Mutex freigibt, den er nicht besitzt, wird im Thread eine <xref:System.ApplicationException> ausgelöst.  
  
 Da die <xref:System.Threading.Mutex>\-Klasse von <xref:System.Threading.WaitHandle> abgeleitet wird, können Sie die statische <xref:System.Threading.WaitHandle.WaitAll%2A>\-Methode oder <xref:System.Threading.WaitHandle.WaitAny%2A>\-Methode von <xref:System.Threading.WaitHandle> aufrufen, um den Besitz von <xref:System.Threading.Mutex> zusammen mit anderen Wait\-Handles anzufordern.  
  
 Wenn <xref:System.Threading.Mutex> im Besitz eines Threads ist, kann dieser Thread genau diesen <xref:System.Threading.Mutex> bei wiederholten Warteanforderungen angeben, ohne dessen Ausführung zu blockieren. <xref:System.Threading.Mutex> muss jedoch ebenso oft freigegeben werden, um den Besitz freizugeben.  
  
## Abgebrochene Mutexe  
 Wenn ein Thread ohne Freigabe von <xref:System.Threading.Mutex> beendet wird, wird der Mutex als abgebrochener Mutex bezeichnet.  Dabei handelt es sich häufig um einen Hinweis auf einen schwerwiegenden Programmierfehler, da die Ressource, die durch den Mutex geschützt wird, in einem inkonsistenten Zustand verbleiben kann.  In .NET Framework, Version 2.0, wird <xref:System.Threading.AbandonedMutexException> im nächsten Thread ausgelöst, der den Mutex verwendet.  
  
> [!NOTE]
>  In .NET Framework, Version 1.0 und 1.1, wird ein abgebrochener <xref:System.Threading.Mutex> auf den signalisierten Zustand festgelegt, und der Besitz geht auf den nächsten wartenden Thread über.  Wenn sich kein Thread im Wartezustand befindet, verbleibt <xref:System.Threading.Mutex> in einem signalisierten Zustand.  Es wird keine Ausnahme ausgelöst.  
  
 Wenn es sich um einen systemweiten Mutex handelt, kann ein abgebrochener Mutex darauf hinweisen, dass eine Anwendung plötzlich beendet wurde \(z. B. über den Windows Task\-Manager\).  
  
## Lokale und Systemmutexe  
 Es gibt zwei Typen von Mutexen: lokale Mutexe und benannte Systemmutexe.  Wenn Sie ein <xref:System.Threading.Mutex>\-Objekt mithilfe eines Konstruktors erstellen, der einen Namen akzeptiert, wird es mit einem Betriebssystemobjekt mit dem betreffenden Namen verknüpft.  Benannte Systemmutexe sind im gesamten Betriebssystem sichtbar, und mit ihrer Hilfe können die Aktivitäten von Prozessen synchronisiert werden.  Sie können mehrere <xref:System.Threading.Mutex>\-Objekte erstellen, die denselben benannten Systemmutex darstellen, und Sie können mithilfe der <xref:System.Threading.Mutex.OpenExisting%2A>\-Methode einen vorhandenen benannten Systemmutex öffnen.  
  
 Ein lokaler Mutex ist nur innerhalb des Prozesses vorhanden.  Es kann von jedem Thread in einem Prozess verwendet werden, der einen Verweis auf das lokale <xref:System.Threading.Mutex>\-Objekt enthält.  Jedes <xref:System.Threading.Mutex>\-Objekt ist ein separater lokaler Mutex.  
  
### Sichere Zugriffssteuerung für Systemmutexe  
 .NET Framework, Version 2.0, bietet die Möglichkeit, für benannte Systemobjekte Sicherheitsmerkmale für die Windows\-Zugriffssteuerung abzufragen und festzulegen.  Es wird empfohlen, Systemmutexe direkt ab ihrer Erstellung zu sichern, da Systemobjekte global sind und deshalb auch durch Fremdcode gesperrt werden können.  
  
 Weitere Informationen darüber, wie Sie eine sichere Zugriffssteuerung für Mutexe einrichten, finden Sie unter den Themen zu folgenden Elementen: <xref:System.Security.AccessControl.MutexSecurity>\-Klasse und <xref:System.Security.AccessControl.MutexAccessRule>\-Klasse, <xref:System.Security.AccessControl.MutexRights>\-Enumeration, Methoden <xref:System.Threading.Mutex.GetAccessControl%2A>, <xref:System.Threading.Mutex.SetAccessControl%2A> und <xref:System.Threading.Mutex.OpenExisting%2A> der <xref:System.Threading.Mutex>\-Klasse und <xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29>\-Konstruktor.  
  
## Siehe auch  
 <xref:System.Threading.Mutex>   
 <xref:System.Threading.Mutex.%23ctor%2A>   
 <xref:System.Security.AccessControl.MutexSecurity>   
 <xref:System.Security.AccessControl.MutexAccessRule>   
 [Threading](../../../docs/standard/threading/index.md)   
 [Threading Objects and Features](../../../docs/standard/threading/threading-objects-and-features.md)   
 [Monitore](../Topic/Monitors.md)   
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)