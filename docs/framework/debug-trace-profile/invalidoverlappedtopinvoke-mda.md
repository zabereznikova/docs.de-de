---
title: invalidOverlappedToPinvoke-MDA
description: Überprüfen Sie den invalidoverlappedtopcallback-MDA (Managed Debugging Assistant) in .net, der während eines Absturzes oder einer nicht erklärenden Heap Beschädigung aktiviert werden kann.
ms.date: 03/30/2017
helpviewer_keywords:
- overlapped pointers
- managed debugging assistants (MDAs), overlapped pointers
- invalid overlapped pointer to platform invoke
- InvalidOverlappedToPinvoke MDA
- MDAs (managed debugging assistants), overlapped pointers
- pointers, overlapped
ms.assetid: 28876047-58bd-4fed-9452-c7da346d67c0
ms.openlocfilehash: 162efd55bf636cf2e8698706bd011379f2f6f11f
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051700"
---
# <a name="invalidoverlappedtopinvoke-mda"></a><span data-ttu-id="a2c5b-103">invalidOverlappedToPinvoke-MDA</span><span class="sxs-lookup"><span data-stu-id="a2c5b-103">invalidOverlappedToPinvoke MDA</span></span>
<span data-ttu-id="a2c5b-104">Der `invalidOverlappedToPinvoke`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn ein überlappender Zeiger, der nicht auf dem Garbage Collection-Heap erstellt wurde, an spezifische Win32-Funktionen übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="a2c5b-104">The `invalidOverlappedToPinvoke` managed debugging assistant (MDA) is activated when an overlapped pointer that was not created on the garbage collection heap is passed to specific Win32 functions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a2c5b-105">Dieser MDA wird standardmäßig nur aktiviert, wenn der Plattformaufruf im Code definiert wurde und der Debugger den JustMyCode-Status der einzelnen Methoden anzeigt.</span><span class="sxs-lookup"><span data-stu-id="a2c5b-105">By default, this MDA is activated only if the platform invoke call is defined in your code and the debugger reports the JustMyCode status of each method.</span></span> <span data-ttu-id="a2c5b-106">Dieser MDA wird von Debuggern, die JustMyCode nicht interpretieren können (z. B. MDbg.exe ohne Erweiterungen) nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="a2c5b-106">A debugger that does not understand JustMyCode (such as MDbg.exe with no extensions) will not activate this MDA.</span></span> <span data-ttu-id="a2c5b-107">Dieser MDA kann für diese Debugger mithilfe einer Konfigurationsdatei aktiviert werden, indem `justMyCode="false"` in der Datei ".mda.config" explizit festgelegt wird: `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`.</span><span class="sxs-lookup"><span data-stu-id="a2c5b-107">This MDA can be enabled for those debuggers by using a configuration file and explicitly settting `justMyCode="false"` in the .mda.config file `(<invalidOverlappedToPinvoke enable="true" justMyCode="false"/>`).</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a2c5b-108">Symptome</span><span class="sxs-lookup"><span data-stu-id="a2c5b-108">Symptoms</span></span>  
 <span data-ttu-id="a2c5b-109">Abstürze oder unerklärliche Heapbeschädigungen.</span><span class="sxs-lookup"><span data-stu-id="a2c5b-109">Crashes or unexplainable heap corruptions.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a2c5b-110">Ursache</span><span class="sxs-lookup"><span data-stu-id="a2c5b-110">Cause</span></span>  
 <span data-ttu-id="a2c5b-111">Ein überlappender Zeiger, der nicht auf dem Garbage Collection-Heap erstellt wurde, wird an spezifische Betriebssystemfunktionen übergeben.</span><span class="sxs-lookup"><span data-stu-id="a2c5b-111">An overlapped pointer that was not created on the garbage collection heap is passed to specific operating system functions.</span></span>  
  
 <span data-ttu-id="a2c5b-112">In der folgenden Tabelle werden die Funktionen gezeigt, die von diesem MDA überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="a2c5b-112">The following table shows the functions that this MDA tracks.</span></span>  
  
|<span data-ttu-id="a2c5b-113">Modul</span><span class="sxs-lookup"><span data-stu-id="a2c5b-113">Module</span></span>|<span data-ttu-id="a2c5b-114">Funktion</span><span class="sxs-lookup"><span data-stu-id="a2c5b-114">Function</span></span>|  
|------------|--------------|  
|<span data-ttu-id="a2c5b-115">HttpApi.dll</span><span class="sxs-lookup"><span data-stu-id="a2c5b-115">HttpApi.dll</span></span>|`HttpReceiveHttpRequest`|  
|<span data-ttu-id="a2c5b-116">IpHlpApi.dll</span><span class="sxs-lookup"><span data-stu-id="a2c5b-116">IpHlpApi.dll</span></span>|`NotifyAddrChange`|  
|<span data-ttu-id="a2c5b-117">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="a2c5b-117">kernel32.dll</span></span>|`ReadFile`|  
|<span data-ttu-id="a2c5b-118">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="a2c5b-118">kernel32.dll</span></span>|`ReadFileEx`|  
|<span data-ttu-id="a2c5b-119">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="a2c5b-119">kernel32.dll</span></span>|`WriteFile`|  
|<span data-ttu-id="a2c5b-120">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="a2c5b-120">kernel32.dll</span></span>|`WriteFileEx`|  
|<span data-ttu-id="a2c5b-121">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="a2c5b-121">kernel32.dll</span></span>|`ReadDirectoryChangesW`|  
|<span data-ttu-id="a2c5b-122">kernel32.dll</span><span class="sxs-lookup"><span data-stu-id="a2c5b-122">kernel32.dll</span></span>|`PostQueuedCompletionStatus`|  
|<span data-ttu-id="a2c5b-123">MSWSock.dll</span><span class="sxs-lookup"><span data-stu-id="a2c5b-123">MSWSock.dll</span></span>|`ConnectEx`|  
|<span data-ttu-id="a2c5b-124">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="a2c5b-124">WS2_32.dll</span></span>|`WSASend`|  
|<span data-ttu-id="a2c5b-125">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="a2c5b-125">WS2_32.dll</span></span>|`WSASendTo`|  
|<span data-ttu-id="a2c5b-126">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="a2c5b-126">WS2_32.dll</span></span>|`WSARecv`|  
|<span data-ttu-id="a2c5b-127">WS2_32.dll</span><span class="sxs-lookup"><span data-stu-id="a2c5b-127">WS2_32.dll</span></span>|`WSARecvFrom`|  
|<span data-ttu-id="a2c5b-128">MQRT.dll</span><span class="sxs-lookup"><span data-stu-id="a2c5b-128">MQRT.dll</span></span>|`MQReceiveMessage`|  
  
 <span data-ttu-id="a2c5b-129">Unter dieser Bedingung besteht eine hohe Wahrscheinlichkeit von Heapbeschädigungen, da die <xref:System.AppDomain>, die den Aufruf durchführt, möglicherweise entladen wird.</span><span class="sxs-lookup"><span data-stu-id="a2c5b-129">The potential for heap corruption is high for this condition because the <xref:System.AppDomain> making the call might unload.</span></span> <span data-ttu-id="a2c5b-130">Falls die <xref:System.AppDomain> entladen wird, gibt der Anwendungscode den Speicher für den überlappenden Zeiger frei, was beim Ende des Vorgangs zu Beschädigungen führt, oder der Code verursacht einen Speicherverlust, was später zu Schwierigkeiten führt.</span><span class="sxs-lookup"><span data-stu-id="a2c5b-130">If the <xref:System.AppDomain> unloads, the application code will either free the memory for the overlapped pointer, causing corruption when the operation finishes, or the code will leak the memory, causing difficulties later.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a2c5b-131">Lösung</span><span class="sxs-lookup"><span data-stu-id="a2c5b-131">Resolution</span></span>  
 <span data-ttu-id="a2c5b-132">Verwenden Sie ein <xref:System.Threading.Overlapped>-Objekt mit einem Aufruf der <xref:System.Threading.Overlapped.Pack%2A>-Methode, um eine <xref:System.Threading.NativeOverlapped>-Struktur abzurufen, die an die Funktion übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="a2c5b-132">Use an <xref:System.Threading.Overlapped> object, calling the <xref:System.Threading.Overlapped.Pack%2A> method to get a <xref:System.Threading.NativeOverlapped> structure that can be passed to the function.</span></span> <span data-ttu-id="a2c5b-133">Wenn die <xref:System.AppDomain> entladen wird, wartet die CLR auf den Abschluss des asynchronen Vorgangs, bevor der Zeiger freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a2c5b-133">If the <xref:System.AppDomain> unloads, the CLR waits until the asynchronous operation completes before freeing the pointer.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a2c5b-134">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a2c5b-134">Effect on the Runtime</span></span>  
 <span data-ttu-id="a2c5b-135">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="a2c5b-135">This MDA had no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a2c5b-136">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="a2c5b-136">Output</span></span>  
 <span data-ttu-id="a2c5b-137">Im Folgenden finden Sie ein Beispiel für die Ausgabe dieses MDA.</span><span class="sxs-lookup"><span data-stu-id="a2c5b-137">The following is an example of output from this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the Win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlapped structure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="a2c5b-138">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a2c5b-138">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidOverlappedToPinvoke/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2c5b-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a2c5b-139">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="a2c5b-140">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="a2c5b-140">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="a2c5b-141">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="a2c5b-141">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
