---
title: Mutexe
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- wait handles
- threading [.NET Framework], Mutex class
- Mutex class, about Mutex class
- threading [.NET Framework], cross-process synchronization
ms.assetid: 9dd06e25-12c0-4a9e-855a-452dc83803e2
ms.openlocfilehash: f9267bdd19a14995851f2689651c001815812912
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291174"
---
# <a name="mutexes"></a>Mutexe
Sie können ein <xref:System.Threading.Mutex>-Objekt verwenden, um exklusiven Zugriff auf eine Ressource bereitzustellen. Die <xref:System.Threading.Mutex>-Klasse verwendet mehr Systemressourcen als die <xref:System.Threading.Monitor>-Klasse, sie kann jedoch über Anwendungsdomänengrenzen hinweg gemarshallt, mit mehreren Wartevorgängen verwendet sowie zur Synchronisierung von Threads in verschiedenen Prozessen verwendet werden. Ein Vergleich der verwalteten Synchronisierungsmechanismen finden Sie unter [Overview of Synchronization Primitives (Überblick über Synchronisierungsprimitiven)](overview-of-synchronization-primitives.md).  
  
 Codebeispiele finden Sie in der Referenzdokumentation für die <xref:System.Threading.Mutex.%23ctor%2A>-Konstruktoren.  
  
## <a name="using-mutexes"></a>Verwenden von Mutexen  
 Ein Thread ruft die <xref:System.Threading.WaitHandle.WaitOne%2A>-Methode eines Mutexes auf, um Besitz anzufordern. Der Aufruf wird blockiert, bis der Mutex verfügbar ist oder bis das optionale Timeoutintervall abgelaufen ist. Der Zustand eines Mutex wird signalisiert, wenn er nicht in Besitz eines Threads ist.  
  
 Ein Thread gibt einen Mutex durch Aufrufen seiner <xref:System.Threading.Mutex.ReleaseMutex%2A>-Methode frei. Mutexe weisen Threadaffinität auf. Sie können nur von einem Thread freigegeben werden, in dessen Besitz sie sich befinden. Wenn ein Thread einen Mutex freigibt, den er nicht besitzt, wird im Thread eine <xref:System.ApplicationException> ausgelöst.  
  
 Da die <xref:System.Threading.Mutex>-Klasse von <xref:System.Threading.WaitHandle> abgeleitet wird, können Sie außerdem die statische <xref:System.Threading.WaitHandle.WaitAll%2A>- oder <xref:System.Threading.WaitHandle.WaitAny%2A>-Methode von <xref:System.Threading.WaitHandle> aufrufen, um den Besitz eines <xref:System.Threading.Mutex> in Kombination mit anderen Wait-Handles anzufordern.  
  
 Wenn ein <xref:System.Threading.Mutex> im Besitz eines Threads ist, kann dieser Thread genau diesen <xref:System.Threading.Mutex> bei wiederholten Warteanforderungen angeben, ohne dessen Ausführung zu blockieren. Der <xref:System.Threading.Mutex> muss jedoch ebenso oft freigegeben werden, um den Besitz freizugeben.  
  
## <a name="abandoned-mutexes"></a>Abgebrochene Mutexe  
 Wenn ein Thread ohne Freigabe eines <xref:System.Threading.Mutex> beendet wird, wird der Mutex als abgebrochener Mutex bezeichnet. Dabei handelt es sich häufig um einen Hinweis auf einen schwerwiegenden Programmierfehler, da die Ressource, die durch den Mutex geschützt wird, in einem inkonsistenten Zustand verbleiben kann. In .NET Framework Version 2.0 wird <xref:System.Threading.AbandonedMutexException> im nächsten Thread ausgelöst, der den Mutex verwendet.  
  
> [!NOTE]
> In .NET Framework Version 1.0 und 1.1 wird ein abgebrochener <xref:System.Threading.Mutex> auf den signalisierten Zustand festgelegt, und der Besitz geht auf den nächsten wartenden Thread über. Wenn sich kein Thread im Wartezustand befindet, verbleibt der <xref:System.Threading.Mutex> in einem signalisierten Zustand. Es werden keine Ausnahmen ausgelöst.  
  
 Wenn es sich um einen systemweiten Mutex handelt, kann ein abgebrochener Mutex darauf hinweisen, dass eine Anwendung plötzlich beendet wurde (z.B. über den Windows Task-Manager).  
  
## <a name="local-and-system-mutexes"></a>Lokale Mutexe und Systemmutexe  
 Es gibt zwei Typen von Mutexen: lokale Mutexe und benannte Systemmutexe. Wenn Sie ein <xref:System.Threading.Mutex>-Objekt mithilfe eines Konstruktors erstellen, der einen Namen akzeptiert, wird es mit einem Betriebssystemobjekt mit dem betreffenden Namen verknüpft. Benannte Systemmutexe sind im gesamten Betriebssystem sichtbar, und mit ihrer Hilfe können die Aktivitäten von Prozessen synchronisiert werden. Sie können mehrere <xref:System.Threading.Mutex>-Objekte erstellen, die denselben benannten Systemmutex darstellen, und Sie können mithilfe der <xref:System.Threading.Mutex.OpenExisting%2A>-Methode einen vorhandenen benannten Systemmutex öffnen.  
  
 Ein lokaler Mutex ist nur innerhalb des Prozesses vorhanden. Er kann von jedem Thread in einem Prozess verwendet werden, der einen Verweis auf das lokale <xref:System.Threading.Mutex>-Objekt enthält. Jedes <xref:System.Threading.Mutex>-Objekt ist ein separater lokaler Mutex.  
  
### <a name="access-control-security-for-system-mutexes"></a>Sichere Zugriffssteuerung für Systemmutexe  
 .NET Framework Version 2.0 bietet die Möglichkeit, für benannte Systemobjekte Sicherheitsmerkmale für die Windows-Zugriffssteuerung abzufragen und festzulegen. Es wird empfohlen, Systemmutexe direkt ab ihrer Erstellung zu sichern, da Systemobjekte global sind und deshalb auch durch Fremdcode gesperrt werden können.  
  
 Informationen zur sicheren Zugriffssteuerung für Mutexe finden Sie in den Artikeln zu <xref:System.Security.AccessControl.MutexSecurity>- und <xref:System.Security.AccessControl.MutexAccessRule>-Klasse, der <xref:System.Security.AccessControl.MutexRights>-Enumeration, der <xref:System.Threading.Mutex.GetAccessControl%2A>-, <xref:System.Threading.Mutex.SetAccessControl%2A>- und <xref:System.Threading.Mutex.OpenExisting%2A>-Methode der <xref:System.Threading.Mutex>-Klasse und dem <xref:System.Threading.Mutex.%23ctor%28System.Boolean%2CSystem.String%2CSystem.Boolean%40%2CSystem.Security.AccessControl.MutexSecurity%29>-Konstruktor.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Mutex?displayProperty=nameWithType>
- <xref:System.Threading.Mutex.%23ctor%2A>
- <xref:System.Security.AccessControl.MutexSecurity?displayProperty=nameWithType>
- <xref:System.Security.AccessControl.MutexAccessRule?displayProperty=nameWithType>
- <xref:System.Threading.Monitor?displayProperty=nameWithType>
- [Threadingobjekte und -funktionen](threading-objects-and-features.md)
- [Threads und Threading](threads-and-threading.md)
- [Threading](index.md)
