---
title: Mutexe
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wait handles
- threading [.NET Framework], Mutex class
- Mutex class, about Mutex class
- threading [.NET Framework], cross-process synchronization
ms.assetid: 9dd06e25-12c0-4a9e-855a-452dc83803e2
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a1d69c1b943d15b9ad8c80b4d7dbafebc54990ab
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="mutexes"></a>Mutexe
Sie können eine <xref:System.Threading.Mutex> exklusiven Zugriff auf eine Ressource zu verwendendes Objekt. Die <xref:System.Threading.Mutex> Klasse verwendet mehr Systemressourcen beansprucht, als die <xref:System.Threading.Monitor> -Klasse, aber sie können über Anwendungsdomänengrenzen hinweg gemarshallt werden, kann mit mehreren Wartevorgängen verwendet werden und es kann verwendet werden, um Threads in verschiedenen Prozessen zu synchronisieren. Ein Vergleich der verwalteten Synchronisierungsmechanismen finden Sie unter [Overview of Synchronization Primitives (Überblick über Synchronisierungsprimitiven)](../../../docs/standard/threading/overview-of-synchronization-primitives.md).  
  
 Codebeispiele finden Sie in der Referenzdokumentation für die <xref:System.Threading.Mutex.%23ctor%2A> Konstruktoren.  
  
## <a name="using-mutexes"></a>Verwenden von Mutexen  
 Ein Thread aufruft, die <xref:System.Threading.WaitHandle.WaitOne%2A> Methode des Mutex auf, um den Besitz anfordert. Der Aufruf wird blockiert, bis der Mutex verfügbar ist oder bis das optionale Timeoutintervall abgelaufen ist. Der Zustand eines Mutex wird signalisiert, wenn er nicht in Besitz eines Threads ist.  
  
 Ein Thread einen Mutex freigibt, durch Aufrufen seiner <xref:System.Threading.Mutex.ReleaseMutex%2A> Methode. Mutexe weisen Threadaffinität auf. Sie können nur von einem Thread freigegeben werden, in dessen Besitz sie sich befinden. Wenn ein Thread einen Mutex Besitzer er nicht ist freigibt, ein <xref:System.ApplicationException> wird im Thread ausgelöst.  
  
 Da die <xref:System.Threading.Mutex> Klasse abgeleitet <xref:System.Threading.WaitHandle>, rufen Sie außerdem die statische <xref:System.Threading.WaitHandle.WaitAll%2A> oder <xref:System.Threading.WaitHandle.WaitAny%2A> Methoden der <xref:System.Threading.WaitHandle> , der Anforderung den Besitz des einer <xref:System.Threading.Mutex> in Kombination mit anderen wait-Handles.  
  
 Wenn ein Thread im Besitz einer <xref:System.Threading.Mutex>, Thread dasselbe angeben kann <xref:System.Threading.Mutex> in wiederholte Wait-Anforderung aufrufen, ohne Blockierung seiner Ausführung; allerdings muss freizugeben der <xref:System.Threading.Mutex> so oft, den Besitz freigibt.  
  
## <a name="abandoned-mutexes"></a>Abgebrochene Mutexe  
 Wenn ein Thread beendet, ohne die Freigabe wird einer <xref:System.Threading.Mutex>, wird der Mutex verworfen wird. Dabei handelt es sich häufig um einen Hinweis auf einen schwerwiegenden Programmierfehler, da die Ressource, die durch den Mutex geschützt wird, in einem inkonsistenten Zustand verbleiben kann. In .NET Framework, Version 2.0 ein <xref:System.Threading.AbandonedMutexException> wird ausgelöst, in der nächste Thread, der den Mutex verwendet.  
  
> [!NOTE]
>  In der .NET Framework-Versionen 1.0 und 1.1, ein abgebrochener <xref:System.Threading.Mutex> wartet auf den signalisierten Zustand und den nächsten Thread Ruft den Besitz. Wenn kein Thread wartet, die <xref:System.Threading.Mutex> verbleibt im Zustand "signalisiert". Es werden keine Ausnahmen ausgelöst.  
  
 Wenn es sich um einen systemweiten Mutex handelt, kann ein abgebrochener Mutex darauf hinweisen, dass eine Anwendung plötzlich beendet wurde (z.B. über den Windows Task-Manager).  
  
## <a name="local-and-system-mutexes"></a>Lokale Mutexe und Systemmutexe  
 Es gibt zwei Typen von Mutexen: lokale Mutexe und benannte Systemmutexe. Bei Erstellung einer <xref:System.Threading.Mutex> -Objekt mithilfe eines Konstruktors, der einen Namen akzeptiert ein Betriebssystem-Objekt mit diesem Namen zugeordnet ist. Benannte Systemmutexe sind im gesamten Betriebssystem sichtbar, und mit ihrer Hilfe können die Aktivitäten von Prozessen synchronisiert werden. Sie können mehrere erstellen <xref:System.Threading.Mutex> benannte Systemmutex Objekte, die die gleiche darstellen, und Sie können die <xref:System.Threading.Mutex.OpenExisting%2A> Methode zum Öffnen einer vorhandenen benannten Systemmutex.  
  
 Ein lokaler Mutex ist nur innerhalb des Prozesses vorhanden. Es kann von jedem Thread innerhalb des Prozesses, der einen Verweis auf die lokale verwendet werden <xref:System.Threading.Mutex> Objekt. Jede <xref:System.Threading.Mutex> Objekt ist ein separater lokaler Mutex.  
  
### <a name="access-control-security-for-system-mutexes"></a>Sichere Zugriffssteuerung für Systemmutexe  
 .NET Framework Version 2.0 bietet die Möglichkeit, für benannte Systemobjekte Sicherheitsmerkmale für die Windows-Zugriffssteuerung abzufragen und festzulegen. Es wird empfohlen, Systemmutexe direkt ab ihrer Erstellung zu sichern, da Systemobjekte global sind und deshalb auch durch Fremdcode gesperrt werden können.  
  
 Informationen zugriffssteuerungssicherheit für Mutexe finden Sie unter der <xref:System.Security.AccessControl.MutexSecurity> und <xref:System.Security.AccessControl.MutexAccessRule> Klassen, die <xref:System.Security.AccessControl.MutexRights> -Enumeration, die <xref:System.Threading.Mutex.GetAccessControl%2A>, <xref:System.Threading.Mutex.SetAccessControl%2A>, und <xref:System.Threading.Mutex.OpenExisting%2A> Methoden die <xref:System.Threading.Mutex> Klasse und die <xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29> Konstruktor.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading.Mutex>  
 <xref:System.Threading.Mutex.%23ctor%2A>  
 <xref:System.Security.AccessControl.MutexSecurity>  
 <xref:System.Security.AccessControl.MutexAccessRule>  
 [Threading](../../../docs/standard/threading/index.md)  
 [Threading Objects and Features (Threadingobjekte und -funktionen)](../../../docs/standard/threading/threading-objects-and-features.md)  
 [Monitore](http://msdn.microsoft.com/library/33fe4aef-b44b-42fd-9e72-c908e39e75db)  
 [Threads and Threading (Threads und Threading)](../../../docs/standard/threading/threads-and-threading.md)
