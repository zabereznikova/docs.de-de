---
title: Verwaltetes und nicht verwaltetes Threading in Windows
ms.date: 10/24/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- threading [.NET Framework], unmanaged
- threading [.NET Framework], managed
- threading [.NET], managed
- threads and fibers [.NET]
- managed threading
ms.assetid: 4fb6452f-c071-420d-9e71-da16dee7a1eb
ms.openlocfilehash: 6ab0cc7c1ec2f7bbc633ac966dd18ab3ea7a395b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "73127544"
---
# <a name="managed-and-unmanaged-threading-in-windows"></a>Verwaltetes und nicht verwaltetes Threading in Windows

Die Verwaltung aller Threads erfolgt über die <xref:System.Threading.Thread> -Klasse, einschließlich Threads, die von der Common Language Runtime erstellt werden, und Threads, die außerhalb der Runtime erstellt werden und in die verwaltete Umgebung eintreten, um Code auszuführen. Die Laufzeit überwacht alle Threads in ihrem Prozess, die jemals Code in der verwalteten Ausführungsumgebung ausgeführt haben. Sie verfolgt keine anderen Threads. Threads können über COM-Interop (da die Runtime verwaltete Objekte als COM-Objekte für die nicht verwaltete Umgebung verfügbar macht), über die COM- [DllGetClassObject](/windows/desktop/api/combaseapi/nf-combaseapi-dllgetclassobject) -Funktion und über einen Plattformaufruf in die verwaltete Ausführungsumgebung eintreten.  
  
 Wenn ein nicht verwalteter Thread beispielsweise über einen COM Callable Wrapper in die Runtime eintritt, überprüft das System den lokalen Threadspeicher auf ein intern verwaltetes <xref:System.Threading.Thread> -Objekt. Wird eins gefunden, ist der Laufzeit dieser Thread bereits bewusst. Wird keins gefunden, erstellt die Runtime jedoch ein neues <xref:System.Threading.Thread> -Objekt und installiert es im lokalen Threadspeicher dieses Threads.  
  
 Beim verwalteten Threading ist <xref:System.Threading.Thread.GetHashCode%2A?displayProperty=nameWithType> die stabile ID für den verwalteten Thread. Für die Lebensdauer des Threads wird kein Konflikt mit dem Wert eines anderen Threads entstehen, unabhängig von der Anwendungsdomäne, aus der Sie diesen Wert erhalten.  
  
> [!NOTE]
> Eine Betriebssystem- **ThreadId** hat keine feste Beziehung zu einem verwalteten Thread, da ein nicht verwalteter Host die Beziehung zwischen verwalteten und nicht verwalteten Threads steuern kann. Insbesondere kann ein komplexer Host die Fiber-API verwenden, um viele verwaltete mit demselben Betriebssystemthread zu verwalten oder einen verwalteten Thread unter verschiedenen Betriebssystemthreads zu verschieben.  
  
## <a name="mapping-from-win32-threading-to-managed-threading"></a>Zuordnen zwischen Win32-Threading und verwaltetem Threading

 In der folgenden Tabelle sind Win32-Threadingelemente ihren ungefähren Laufzeitentsprechungen zugeordnet. Beachten Sie, dass diese Zuordnung keine identische Funktionalität darstellt. **TerminateThread** führt beispielsweise keine **finally** -Klauseln aus, setzt keine Ressourcen frei und kann nicht vermieden werden. <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> jedoch führt Ihren gesamten Rollbackcode aus, gibt alle Ressourcen frei und kann über <xref:System.Threading.Thread.ResetAbort%2A>verweigert werden. Lesen Sie unbedingt sorgfältig die Dokumentation, bevor Sie Annahmen über die Funktionalität treffen.  
  
|In Win32|In der Common Language Runtime|  
|--------------|------------------------------------|  
|**CreateThread**|Kombination aus **Thread** und <xref:System.Threading.ThreadStart>|  
|**TerminateThread**|<xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>|  
|**SuspendThread**|<xref:System.Threading.Thread.Suspend%2A?displayProperty=nameWithType>|  
|**ResumeThread**|<xref:System.Threading.Thread.Resume%2A?displayProperty=nameWithType>|  
|**Sleep**|<xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType>|  
|**WaitForSingleObject** im Threadhandle|<xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>|  
|**ExitThread**|Keine Entsprechung|  
|**GetCurrentThread**|<xref:System.Threading.Thread.CurrentThread%2A?displayProperty=nameWithType>|  
|**SetThreadPriority**|<xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType>|  
|Keine Entsprechung|<xref:System.Threading.Thread.Name%2A?displayProperty=nameWithType>|  
|Keine Entsprechung|<xref:System.Threading.Thread.IsBackground%2A?displayProperty=nameWithType>|  
|Nahe an **CoInitializeEx** (OLE32.DLL)|<xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType>|  
  
## <a name="managed-threads-and-com-apartments"></a>Verwaltete Threads und COM-Apartments

Ein verwalteter Thread kann gekennzeichnet werden, um anzugeben, dass er ein [Singlethread](/windows/desktop/com/single-threaded-apartments) - oder ein [Multithread](/windows/desktop/com/multithreaded-apartments) -Apartment hostet. (Weitere Informationen zur COM-Threadingarchitektur finden Sie unter [Prozesse, Threads und Apartments](/windows/desktop/com/processes--threads--and-apartments).) Die Methoden <xref:System.Threading.Thread.GetApartmentState%2A>, <xref:System.Threading.Thread.SetApartmentState%2A> und <xref:System.Threading.Thread.TrySetApartmentState%2A> der <xref:System.Threading.Thread>-Klasse geben den Apartmentzustand eines Threads zurück und weisen ihn zu. Wurde der Zustand nicht festgelegt, gibt <xref:System.Threading.Thread.GetApartmentState%2A> den Wert <xref:System.Threading.ApartmentState.Unknown?displayProperty=nameWithType> zurück.  
  
 Die Eigenschaft kann nur festgelegt werden, wenn sich der Thread im Zustand <xref:System.Threading.ThreadState.Unstarted?displayProperty=nameWithType> befindet. Die Eigenschaft kann für einen Thread nur einmal festgelegt werden.  
  
 Wenn der Apartmentzustand nicht festgelegt ist, bevor der Thread gestartet wird, wird der Thread als Multithread-Apartment (MTA) initialisiert. Der Finalizerthread und alle von <xref:System.Threading.ThreadPool> gesteuerten Threads sind MTAs.  
  
> [!IMPORTANT]
> Bei Anwendungsstartcode besteht die einzige Möglichkeit zum Steuern des Apartmentstatus darin, <xref:System.MTAThreadAttribute> oder <xref:System.STAThreadAttribute> für das Einstiegspunktverfahren anzuwenden. In .NET Framework 1.0 und 1.1 kann die Eigenschaft <xref:System.Threading.Thread.ApartmentState%2A> als erste Codezeile festgelegt werden. Das ist in .NET Framework 2.0 nicht zulässig.  
  
 Verwaltete Objekte, die für COM verfügbar gemacht werden, verhalten sich, als hätten sie den Freethread-Marshaler aggregiert. Anders gesagt können Sie von jedem COM-Apartment auf eine Freethreadweise aufgerufen werden. Die einzigen verwalteten Objekte, die dieses Freethread-Verhalten nicht zeigen, die Objekte, die von <xref:System.EnterpriseServices.ServicedComponent> oder <xref:System.Runtime.InteropServices.StandardOleMarshalObject> abgeleitet werden.  
  
 In der verwalteten Umgebung wird <xref:System.Runtime.Remoting.Contexts.SynchronizationAttribute> nur unterstützt, wenn Sie Kontexte und kontextgebundene verwaltete Instanzen verwenden. Wenn Sie Enterprise Services verwenden, muss Ihr Objekt aus der <xref:System.EnterpriseServices.ServicedComponent>-Klasse abgeleitet sein (die wiederum selbst aus <xref:System.ContextBoundObject> abgeleitet ist).  
  
 Wenn verwalteter Code COM-Objekte aufruft, befolgt er immer COM-Regeln. Anders gesagt erfolgt der Aufruf über COM-Apartmentproxies und COM+ 1.0-Kontext-Wrapper, wie von OLE32 vorgegeben.  
  
## <a name="blocking-issues"></a>Blockierprobleme  

Wenn ein Thread einen nicht verwalteten Aufruf in der Betriebssystem vornimmt, das den Thread in nicht verwaltetem Code blockiert hat, übernimmt die Laufzeit keine Kontrolle darüber für <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> oder <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. Im Fall von <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>kennzeichnet die Laufzeit den Thread für **Abort** und übernimmt die Kontrolle darüber, wenn der verwaltete Code erneut eingegeben wird. Sie sollten vorzugsweise die verwaltete Blockierung statt die nicht verwaltete Blockierung verwenden. <xref:System.Threading.WaitHandle.WaitOne%2A?displayProperty=nameWithType>,<xref:System.Threading.WaitHandle.WaitAny%2A?displayProperty=nameWithType>, <xref:System.Threading.WaitHandle.WaitAll%2A?displayProperty=nameWithType>, <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType>, <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType>, <xref:System.Threading.Thread.Join%2A?displayProperty=nameWithType>, <xref:System.GC.WaitForPendingFinalizers%2A?displayProperty=nameWithType>und so weiter reagieren alle auf <xref:System.Threading.Thread.Interrupt%2A?displayProperty=nameWithType> und auf <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType>. Wenn sich Ihr Thread in einem Singlethread-Apartment befindet, werden all diese verwalteten Blockierungsvorgänge außerdem Meldungen in Ihr Apartment verschieben, während Ihr Thread blockiert ist.  

## <a name="threads-and-fibers"></a>Threads und Fibers

Das .NET-Threadingmodell unterstützt keine [Fibers](/windows/desktop/procthread/fibers). Sie sollten keine nicht verwaltete Funktion aufrufen, die mithilfe von Fibers implementiert wurde. Solche Aufrufe können zu einem Absturz der .NET-Runtime führen.

## <a name="see-also"></a>Siehe auch

- <xref:System.Threading.Thread.ApartmentState%2A?displayProperty=nameWithType>
- <xref:System.Threading.ThreadState>
- <xref:System.EnterpriseServices.ServicedComponent>
- <xref:System.Threading.Thread>
- <xref:System.Threading.Monitor>
