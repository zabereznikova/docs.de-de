---
title: gcManagedToUnmanaged-MDA
description: Überprüfen Sie den gcmanageddeunmanaged Debug Assistant. Dieser MDA kann aufgrund von vorzeitigen Garbage Collection während des Übergangs zu nicht verwaltetem Code aktiviert werden.
ms.date: 03/30/2017
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
ms.openlocfilehash: 668b06109e59f1239cd2b3e3017aeee1916ce69e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244235"
---
# <a name="gcmanagedtounmanaged-mda"></a><span data-ttu-id="58faa-104">gcManagedToUnmanaged-MDA</span><span class="sxs-lookup"><span data-stu-id="58faa-104">gcManagedToUnmanaged MDA</span></span>

<span data-ttu-id="58faa-105">Der `gcManagedToUnmanaged`-Assistent für verwaltetes Debuggen (MDA) bewirkt eine Garbage Collection bei jedem Übergang eines Threads von verwaltetem zu nicht verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="58faa-105">The `gcManagedToUnmanaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="58faa-106">Symptome</span><span class="sxs-lookup"><span data-stu-id="58faa-106">Symptoms</span></span>  

 <span data-ttu-id="58faa-107">Eine nicht verwaltete Benutzerkomponente löst bei dem Versuch, ein für COM verfügbar gemachtes verwaltetes Objekt zu verwenden, eine Zugriffsverletzung aus.</span><span class="sxs-lookup"><span data-stu-id="58faa-107">An unmanaged user component throws an access violation when trying to use a managed object that had been exposed to COM.</span></span> <span data-ttu-id="58faa-108">Das COM-Objekt wurde scheinbar freigegeben.</span><span class="sxs-lookup"><span data-stu-id="58faa-108">The COM object appears to have been released.</span></span> <span data-ttu-id="58faa-109">Die Zugriffsverletzung ist nicht deterministisch.</span><span class="sxs-lookup"><span data-stu-id="58faa-109">The access violation is nondeterministic.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="58faa-110">Ursache</span><span class="sxs-lookup"><span data-stu-id="58faa-110">Cause</span></span>  

 <span data-ttu-id="58faa-111">Wenn eine nicht verwaltete Komponente keine korrekte Verweiszählung für ein verwaltetes COM-Objekt durchführt, wird das für COM verfügbar gemachte verwaltete Objekt unter Umständen schon einer Garbage Collection unterzogen, während die nicht verwaltete Komponente noch über einen Verweis auf dieses Objekt verfügt.</span><span class="sxs-lookup"><span data-stu-id="58faa-111">If an unmanaged component is not reference counting a managed COM object correctly, then the runtime could collect a managed object exposed to COM when the unmanaged component still holds a reference to the object.</span></span> <span data-ttu-id="58faa-112">Bei der Garbage Collection wird von der CLR <xref:System.Runtime.InteropServices.Marshal.Release%2A> aufgerufen. Wenn die Benutzerkomponente das Objekt also vor dem Ausführen der Garbage Collection verwendet, wurde es noch nicht der Garbage Collection unterzogen.</span><span class="sxs-lookup"><span data-stu-id="58faa-112">The runtime calls <xref:System.Runtime.InteropServices.Marshal.Release%2A> during garbage collections, so if the user component uses the object before the garbage collection occurs, then it will not yet have been collected.</span></span> <span data-ttu-id="58faa-113">Dies ist die Ursache der Nichtdeterminiertheit.</span><span class="sxs-lookup"><span data-stu-id="58faa-113">This is the source of the nondeterminism.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="58faa-114">Lösung</span><span class="sxs-lookup"><span data-stu-id="58faa-114">Resolution</span></span>  

 <span data-ttu-id="58faa-115">Durch das Aktivieren dieses Assistenten verringert sich die Zeit zwischen der Freigabe des Objekts zur Garbage Collection und dem Aufruf von <xref:System.Runtime.InteropServices.Marshal.Release%2A>. So kann besser ermittelt werden, welche nicht verwaltete Komponente zuerst versucht, auf das der Garbage Collection unterzogene Objekt zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="58faa-115">Enabling this assistant reduces the time between when the object is eligible for collection and <xref:System.Runtime.InteropServices.Marshal.Release%2A> is called, helping to track down which unmanaged component first tries to access the collected object.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="58faa-116">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="58faa-116">Effect on the Runtime</span></span>  

 <span data-ttu-id="58faa-117">Löst immer eine Garbage Collection aus, wenn der Übergang eines Threads von verwaltetem zu nicht verwaltetem Code erfolgt.</span><span class="sxs-lookup"><span data-stu-id="58faa-117">Causes a garbage collection whenever a thread transitions from managed to unmanaged code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="58faa-118">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="58faa-118">Output</span></span>  

 <span data-ttu-id="58faa-119">Dieser MDA erzeugt keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="58faa-119">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="58faa-120">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="58faa-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcManagedToUnmanaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="58faa-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="58faa-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="58faa-122">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="58faa-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="58faa-123">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="58faa-123">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
- [<span data-ttu-id="58faa-124">gcUnmanagedToManaged</span><span class="sxs-lookup"><span data-stu-id="58faa-124">gcUnmanagedToManaged</span></span>](gcunmanagedtomanaged-mda.md)
