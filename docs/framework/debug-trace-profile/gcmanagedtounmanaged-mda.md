---
title: gcManagedToUnmanaged-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GcManagedToUnmanaged MDA
- GC managed to unmanaged
- transitioning threads managed to unmanaged code
- threading [.NET Framework], garbage collection
- managed to unmanaged garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
ms.assetid: 7417f837-805e-4fed-a430-ca919c8421dc
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1aa528eb2acc872b1956edef3af3724bb3b54d67
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="721af-102">gcManagedToUnmanaged-MDA</span><span class="sxs-lookup"><span data-stu-id="721af-102">gcManagedToUnmanaged MDA</span></span>
<span data-ttu-id="721af-103">Der `gcManagedToUnmanaged`-Assistent für verwaltetes Debuggen (MDA) bewirkt eine Garbage Collection bei jedem Übergang eines Threads von verwaltetem zu nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="721af-103">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="721af-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="721af-104">Symptoms</span></span>  
 <span data-ttu-id="721af-105">Eine nicht verwaltete Benutzerkomponente löst bei dem Versuch, ein für COM verfügbar gemachtes verwaltetes Objekt zu verwenden, eine Zugriffsverletzung aus.</span><span class="sxs-lookup"><span data-stu-id="721af-105">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="721af-106">Das COM-Objekt wurde scheinbar freigegeben.</span><span class="sxs-lookup"><span data-stu-id="721af-106">The COM object appears to have been released.</span></span> <span data-ttu-id="721af-107">Die Zugriffsverletzung ist nicht deterministisch.</span><span class="sxs-lookup"><span data-stu-id="721af-107">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="721af-108">Ursache</span><span class="sxs-lookup"><span data-stu-id="721af-108">Cause</span></span>  
 <span data-ttu-id="721af-109">Wenn eine nicht verwaltete Komponente keine korrekte Verweiszählung für ein verwaltetes COM-Objekt durchführt, wird das für COM verfügbar gemachte verwaltete Objekt unter Umständen schon einer Garbage Collection unterzogen, während die nicht verwaltete Komponente noch über einen Verweis auf dieses Objekt verfügt.</span><span class="sxs-lookup"><span data-stu-id="721af-109">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="721af-110">Bei der Garbage Collection wird von der CLR <xref:System.Runtime.InteropServices.Marshal.Release%2A> aufgerufen. Wenn die Benutzerkomponente das Objekt also vor dem Ausführen der Garbage Collection verwendet, wurde es noch nicht der Garbage Collection unterzogen.</span><span class="sxs-lookup"><span data-stu-id="721af-110">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="721af-111">Dies ist die Ursache der Nichtdeterminiertheit.</span><span class="sxs-lookup"><span data-stu-id="721af-111">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="721af-112">Auflösung</span><span class="sxs-lookup"><span data-stu-id="721af-112">Resolution</span></span>  
 <span data-ttu-id="721af-113">Durch das Aktivieren dieses Assistenten verringert sich die Zeit zwischen der Freigabe des Objekts zur Garbage Collection und dem Aufruf von <xref:System.Runtime.InteropServices.Marshal.Release%2A>. So kann besser ermittelt werden, welche nicht verwaltete Komponente zuerst versucht, auf das der Garbage Collection unterzogene Objekt zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="721af-113">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="721af-114">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="721af-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="721af-115">Löst immer eine Garbage Collection aus, wenn der Übergang eines Threads von verwaltetem zu nicht verwaltetem Code erfolgt.</span><span class="sxs-lookup"><span data-stu-id="721af-115">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="721af-116">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="721af-116">Output</span></span>  
 <span data-ttu-id="721af-117">Dieser MDA erzeugt keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="721af-117">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="721af-118">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="721af-118">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="721af-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="721af-119">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="721af-120">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="721af-120">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="721af-121">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="721af-121">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)  
 [<span data-ttu-id="721af-122">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="721af-122">gcUnmanagedToManaged</span></span>](../../../docs/framework/debug-trace-profile/gcunmanagedtomanaged-mda.md)
