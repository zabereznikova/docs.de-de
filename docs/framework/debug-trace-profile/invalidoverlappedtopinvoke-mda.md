---
title: invalidOverlappedToPinvoke-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- overlapped pointers
- managed debugging assistants (MDAs), overlapped pointers
- invalid overlapped pointer to platform invoke
- InvalidOverlappedToPinvoke MDA
- MDAs (managed debugging assistants), overlapped pointers
- pointers, overlapped
ms.assetid: 28876047-58bd-4fed-9452-c7da346d67c0
ms.openlocfilehash: 1f557cc370d5c6121b0ad9a4528bd75dcb70a93c
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216279"
---
# <a name="invalidoverlappedtopinvoke-mda"></a><span data-ttu-id="d7691-102">invalidOverlappedToPinvoke-MDA</span><span class="sxs-lookup"><span data-stu-id="d7691-102">invalidOverlappedToPinvoke MDA</span></span>
<span data-ttu-id="d7691-103">Der `invalidOverlappedToPinvoke`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn ein überlappender Zeiger, der nicht auf dem Garbage Collection-Heap erstellt wurde, an spezifische Win32-Funktionen übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="d7691-103">The `invalidOverlappedToPinvoke` managed debugging assistant (MDA) is activated when an overlapped pointer that was not created on the garbage collection heap is passed to specific Win32 functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d7691-104">Dieser MDA wird standardmäßig nur aktiviert, wenn der Plattformaufruf im Code definiert wurde und der Debugger den JustMyCode-Status der einzelnen Methoden anzeigt.</span><span class="sxs-lookup"><span data-stu-id="d7691-104">By default, this MDA is activated only if the platform invoke call is defined in your code and the debugger reports the JustMyCode status of each method.</span></span> <span data-ttu-id="d7691-105">Dieser MDA wird von Debuggern, die JustMyCode nicht interpretieren können (z. B. MDbg.exe ohne Erweiterungen) nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d7691-105">A debugger that does not understand JustMyCode (such as MDbg.exe with no extensions) will not activate this MDA.</span></span> <span data-ttu-id="d7691-106">Dieser MDA kann für diese Debugger mithilfe einer Konfigurationsdatei aktiviert werden, indem `justMyCode="false"` in der Datei ".mda.config" explizit festgelegt wird: `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`.</span><span class="sxs-lookup"><span data-stu-id="d7691-106">This MDA can be enabled for those debuggers by using a configuration file and explicitly settting `justMyCode="false"` in the .mda.config file `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`).</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="d7691-107">Symptome</span><span class="sxs-lookup"><span data-stu-id="d7691-107">Symptoms</span></span>  
 <span data-ttu-id="d7691-108">Abstürze oder unerklärliche Heapbeschädigungen.</span><span class="sxs-lookup"><span data-stu-id="d7691-108">Crashes or unexplainable heap corruptions.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="d7691-109">Ursache</span><span class="sxs-lookup"><span data-stu-id="d7691-109">Cause</span></span>  
 <span data-ttu-id="d7691-110">Ein überlappender Zeiger, der nicht auf dem Garbage Collection-Heap erstellt wurde, wird an spezifische Betriebssystemfunktionen übergeben.</span><span class="sxs-lookup"><span data-stu-id="d7691-110">An overlapped pointer that was not created on the garbage collection heap is passed to specific operating system functions.</span></span>  
  
 <span data-ttu-id="d7691-111">In der folgenden Tabelle werden die Funktionen gezeigt, die von diesem MDA überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="d7691-111">The following table shows the functions that this MDA tracks.</span></span>  
  
|<span data-ttu-id="d7691-112">Modul</span><span class="sxs-lookup"><span data-stu-id="d7691-112">Module</span></span>|<span data-ttu-id="d7691-113">Funktion</span><span class="sxs-lookup"><span data-stu-id="d7691-113">Function</span></span>|  
|------------|--------------|  
|<span data-ttu-id="d7691-114">HttpApi.dll</span><span class="sxs-lookup"><span data-stu-id="d7691-114">HttpApi.dll</span></span>|`HttpReceiveHttpRequest`|  
|<span data-ttu-id="d7691-115">IpHlpApi.dll</span><span class="sxs-lookup"><span data-stu-id="d7691-115">IpHlpApi.dll</span></span>|`NotifyAddrChange`|  
|<span data-ttu-id="d7691-116">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="d7691-116">kernel32.dll</span></span>|`ReadFile`|  
|<span data-ttu-id="d7691-117">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="d7691-117">kernel32.dll</span></span>|`ReadFileEx`|  
|<span data-ttu-id="d7691-118">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="d7691-118">kernel32.dll</span></span>|`WriteFile`|  
|<span data-ttu-id="d7691-119">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="d7691-119">kernel32.dll</span></span>|`WriteFileEx`|  
|<span data-ttu-id="d7691-120">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="d7691-120">kernel32.dll</span></span>|`ReadDirectoryChangesW`|  
|<span data-ttu-id="d7691-121">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="d7691-121">kernel32.dll</span></span>|`PostQueuedCompletionStatus`|  
|<span data-ttu-id="d7691-122">MSWSock.dll</span><span class="sxs-lookup"><span data-stu-id="d7691-122">MSWSock.dll</span></span>|`ConnectEx`|  
|<span data-ttu-id="d7691-123">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="d7691-123">WS2_32.dll</span></span>|`WSASend`|  
|<span data-ttu-id="d7691-124">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="d7691-124">WS2_32.dll</span></span>|`WSASendTo`|  
|<span data-ttu-id="d7691-125">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="d7691-125">WS2_32.dll</span></span>|`WSARecv`|  
|<span data-ttu-id="d7691-126">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="d7691-126">WS2_32.dll</span></span>|`WSARecvFrom`|  
|<span data-ttu-id="d7691-127">MQRT.dll</span><span class="sxs-lookup"><span data-stu-id="d7691-127">MQRT.dll</span></span>|`MQReceiveMessage`|  
  
 <span data-ttu-id="d7691-128">Unter dieser Bedingung besteht eine hohe Wahrscheinlichkeit von Heapbeschädigungen, da die <xref:System.AppDomain>, die den Aufruf durchführt, möglicherweise entladen wird.</span><span class="sxs-lookup"><span data-stu-id="d7691-128">The potential for heap corruption is high for this condition because the <xref:System.AppDomain> making the call might unload.</span></span> <span data-ttu-id="d7691-129">Falls die <xref:System.AppDomain> entladen wird, gibt der Anwendungscode den Speicher für den überlappenden Zeiger frei, was beim Ende des Vorgangs zu Beschädigungen führt, oder der Code verursacht einen Speicherverlust, was später zu Schwierigkeiten führt.</span><span class="sxs-lookup"><span data-stu-id="d7691-129">If the <xref:System.AppDomain> unloads, the application code will either free the memory for the overlapped pointer, causing corruption when the operation finishes, or the code will leak the memory, causing difficulties later.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="d7691-130">Lösung</span><span class="sxs-lookup"><span data-stu-id="d7691-130">Resolution</span></span>  
 <span data-ttu-id="d7691-131">Verwenden Sie ein <xref:System.Threading.Overlapped>-Objekt mit einem Aufruf der <xref:System.Threading.Overlapped.Pack%2A>-Methode, um eine <xref:System.Threading.NativeOverlapped>-Struktur abzurufen, die an die Funktion übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="d7691-131">Use an <xref:System.Threading.Overlapped> object, calling the <xref:System.Threading.Overlapped.Pack%2A> method to get a <xref:System.Threading.NativeOverlapped> structure that can be passed to the function.</span></span> <span data-ttu-id="d7691-132">Wenn die <xref:System.AppDomain> entladen wird, wartet die CLR auf den Abschluss des asynchronen Vorgangs, bevor der Zeiger freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d7691-132">If the <xref:System.AppDomain> unloads, the CLR waits until the asynchronous operation completes before freeing the pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="d7691-133">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="d7691-133">Effect on the Runtime</span></span>  
 <span data-ttu-id="d7691-134">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="d7691-134">This MDA had no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="d7691-135">Output</span><span class="sxs-lookup"><span data-stu-id="d7691-135">Output</span></span>  
 <span data-ttu-id="d7691-136">Im Folgenden finden Sie ein Beispiel für die Ausgabe dieses MDA.</span><span class="sxs-lookup"><span data-stu-id="d7691-136">The following is an example of output from this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the Win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlapped structure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="d7691-137">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="d7691-137">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidOverlappedToPinvoke/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7691-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7691-138">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="d7691-139">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="d7691-139">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="d7691-140">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="d7691-140">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
