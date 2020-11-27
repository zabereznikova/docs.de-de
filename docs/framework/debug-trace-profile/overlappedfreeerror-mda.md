---
title: overlappedFreeError-MDA
description: Überprüfen Sie den overlappedfreerror Managed Debug Assistant (MDA) in .net, der bei Zugriffs Verletzungen oder Beschädigungen des Garbage Collection-Heaps aktiviert werden kann.
ms.date: 03/30/2017
helpviewer_keywords:
- OverlappedFreeError MDA
- overlapped free method call error
- managed debugging assistants (MDAs), overlapped structures
- overlapped structures
- MDAs (managed debugging assistants), overlapped structures
- freeing overlapped structures
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
ms.openlocfilehash: 1bedb8ad3b9801f0d235371a397c8951ff8723b1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254531"
---
# <a name="overlappedfreeerror-mda"></a><span data-ttu-id="90c57-103">overlappedFreeError-MDA</span><span class="sxs-lookup"><span data-stu-id="90c57-103">overlappedFreeError MDA</span></span>

<span data-ttu-id="90c57-104">Der `overlappedFreeError`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn die <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType>-Methode aufgerufen wird, bevor der überlappende Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="90c57-104">The `overlappedFreeError` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> method is called before the overlapped operation has completed.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="90c57-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="90c57-105">Symptoms</span></span>  

 <span data-ttu-id="90c57-106">Zugriffsverletzungen oder Beschädigungen des Heaps der Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="90c57-106">Access violations or corruption of the garbage-collected heap.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="90c57-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="90c57-107">Cause</span></span>  

 <span data-ttu-id="90c57-108">Eine überlappende Struktur wurde freigegeben, bevor der Vorgang abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="90c57-108">An overlapped structure was freed before the operation completed.</span></span> <span data-ttu-id="90c57-109">Die Funktion, die den überlappenden Zeiger verwendet, wird möglicherweise später auf die Struktur schreiben, nachdem dieser freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="90c57-109">The function that is using the overlapped pointer might write to the structure later, after it has been freed.</span></span> <span data-ttu-id="90c57-110">Dies kann den Heap beschädigen, da ein anderes Objekt jetzt diesen Bereich einnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="90c57-110">That can cause heap corruption because another object might now occupy that region.</span></span>  
  
 <span data-ttu-id="90c57-111">Dieser MDA stellt möglicherweise keine Fehler dar, wenn der überlappende Vorgang nicht erfolgreich gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="90c57-111">This MDA might not represent an error if the overlapped operation did not start successfully.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="90c57-112">Lösung</span><span class="sxs-lookup"><span data-stu-id="90c57-112">Resolution</span></span>  

 <span data-ttu-id="90c57-113">Stellen Sie sicher, dass der E/A-Vorgang die überlappende Struktur verwendet, bevor Sie die <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="90c57-113">Ensure that the I/O operation using the overlapped structure has completed before calling the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29> method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="90c57-114">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="90c57-114">Effect on the Runtime</span></span>  

 <span data-ttu-id="90c57-115">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="90c57-115">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="90c57-116">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="90c57-116">Output</span></span>  

 <span data-ttu-id="90c57-117">Nachfolgend wird eine Beispielausgabe für diesen MDA angezeigt.</span><span class="sxs-lookup"><span data-stu-id="90c57-117">The following is sample output for this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="90c57-118">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="90c57-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="90c57-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90c57-119">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="90c57-120">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="90c57-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="90c57-121">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="90c57-121">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
