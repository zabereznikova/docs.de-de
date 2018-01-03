---
title: overlappedFreeError-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- OverlappedFreeError MDA
- overlapped free method call error
- managed debugging assistants (MDAs), overlapped structures
- overlapped structures
- MDAs (managed debugging assistants), overlapped structures
- freeing overlapped structures
ms.assetid: b6ab2d48-6eee-4bab-97a3-046b3b0a5470
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4e17e9d6a93b69d358e89109cf965b7b9856c325
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="overlappedfreeerror-mda"></a><span data-ttu-id="1a4b0-102">overlappedFreeError-MDA</span><span class="sxs-lookup"><span data-stu-id="1a4b0-102">overlappedFreeError MDA</span></span>
<span data-ttu-id="1a4b0-103">Der `overlappedFreeError`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn die <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType>-Methode aufgerufen wird, bevor der überlappende Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1a4b0-103">The `overlappedFreeError` managed debugging assistant (MDA) is activated when the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29?displayProperty=nameWithType> method is called before the overlapped operation has completed.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="1a4b0-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="1a4b0-104">Symptoms</span></span>  
 <span data-ttu-id="1a4b0-105">Zugriffsverletzungen oder Beschädigungen des Heaps der Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="1a4b0-105">Access violations or corruption of the garbage-collected heap.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="1a4b0-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="1a4b0-106">Cause</span></span>  
 <span data-ttu-id="1a4b0-107">Eine überlappende Struktur wurde freigegeben, bevor der Vorgang abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1a4b0-107">An overlapped structure was freed before the operation completed.</span></span> <span data-ttu-id="1a4b0-108">Die Funktion, die den überlappenden Zeiger verwendet, wird möglicherweise später auf die Struktur schreiben, nachdem dieser freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="1a4b0-108">The function that is using the overlapped pointer might write to the structure later, after it has been freed.</span></span> <span data-ttu-id="1a4b0-109">Dies kann den Heap beschädigen, da ein anderes Objekt jetzt diesen Bereich einnehmen kann.</span><span class="sxs-lookup"><span data-stu-id="1a4b0-109">That can cause heap corruption because another object might now occupy that region.</span></span>  
  
 <span data-ttu-id="1a4b0-110">Dieser MDA stellt möglicherweise keine Fehler dar, wenn der überlappende Vorgang nicht erfolgreich gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="1a4b0-110">This MDA might not represent an error if the overlapped operation did not start successfully.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="1a4b0-111">Auflösung</span><span class="sxs-lookup"><span data-stu-id="1a4b0-111">Resolution</span></span>  
 <span data-ttu-id="1a4b0-112">Stellen Sie sicher, dass der E/A-Vorgang die überlappende Struktur verwendet, bevor Sie die <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29>-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="1a4b0-112">Ensure that the I/O operation using the overlapped structure has completed before calling the <xref:System.Threading.Overlapped.Free%28System.Threading.NativeOverlapped%2A%29> method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="1a4b0-113">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="1a4b0-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="1a4b0-114">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="1a4b0-114">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="1a4b0-115">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="1a4b0-115">Output</span></span>  
 <span data-ttu-id="1a4b0-116">Nachfolgend wird eine Beispielausgabe für diesen MDA angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a4b0-116">The following is sample output for this MDA.</span></span>  
  
 `An overlapped pointer (0x00ea3430) that was not allocated on the GC heap was passed via Pinvoke to the win32 function 'WriteFile' in module 'KERNEL32.DLL'. If the AppDomain is shut down, this can cause heap corruption when the async I/O completes. The best solution is to pass a NativeOverlappedStructure retrieved from a call to System.Threading.Overlapped.Pack(). If the AppDomain exits, the CLR will keep this structure alive and pinned until the I/O completes.`  
  
## <a name="configuration"></a><span data-ttu-id="1a4b0-117">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="1a4b0-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <overlappedFreeError/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1a4b0-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a4b0-118">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="1a4b0-119">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="1a4b0-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="1a4b0-120">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="1a4b0-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
