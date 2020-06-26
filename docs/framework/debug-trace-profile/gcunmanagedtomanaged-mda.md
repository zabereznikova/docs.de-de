---
title: gcUnmanagedToManaged-MDA
description: Überprüfen Sie den gcmanageddeunmanaged Debug Assistant in .net. Dieser MDA kann aufgrund von Garbage Heap-Beschädigungen während des Übergangs zu verwaltetem Code aktiviert werden.
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), garbage collection
- GC unmanaged to managed
- transitioning threads unmanaged to managed code
- GcUnmanagedToManaged MDA
- threading [.NET Framework], garbage collection
- managed debugging assistants (MDAs), garbage collection
- threading [.NET Framework], managed debugging assistants
- garbage collection, run-time errors
- unmanaged to managed garbage collection
ms.assetid: 103eb3a3-1cf0-4406-8a9a-a7798fdc22d1
ms.openlocfilehash: 320d55224e6a204d330447d6c68eabe0fa6cf892
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415900"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="41cd5-104">gcUnmanagedToManaged-MDA</span><span class="sxs-lookup"><span data-stu-id="41cd5-104">gcUnmanagedToManaged MDA</span></span>
<span data-ttu-id="41cd5-105">Der `gcUnmanagedToManaged`-Assistent für verwaltetes Debuggen (MDA) bewirkt eine Garbage Collection bei jedem Übergang eines Threads von nicht verwaltetem zu verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="41cd5-105">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="41cd5-106">Symptome</span><span class="sxs-lookup"><span data-stu-id="41cd5-106">Symptoms</span></span>  
 <span data-ttu-id="41cd5-107">Eine Anwendung, die mithilfe von COM und Plattformaufrufen nicht verwaltete Benutzerkomponenten ausführt, verursacht eine nicht deterministische Zugriffsverletzung in der CLR.</span><span class="sxs-lookup"><span data-stu-id="41cd5-107">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="41cd5-108">Ursache</span><span class="sxs-lookup"><span data-stu-id="41cd5-108">Cause</span></span>  
 <span data-ttu-id="41cd5-109">Wenn eine Anwendung nicht verwaltete Benutzerkomponenten ausführt, haben diese Komponenten möglicherweise den Heap der Garbage Collection beschädigt.</span><span class="sxs-lookup"><span data-stu-id="41cd5-109">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="41cd5-110">Dies verursacht eine Zugriffsverletzung in der CLR, wenn der Garbage Collector versucht, das Objektdiagramm zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="41cd5-110">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="41cd5-111">Lösung</span><span class="sxs-lookup"><span data-stu-id="41cd5-111">Resolution</span></span>  
 <span data-ttu-id="41cd5-112">Das Aktivieren dieses Assistenten verringert die Zeit zwischen dem Zeitpunkt der Beschädigung des Heaps der Garbage Collection durch die nicht verwaltete Komponente und dem Zeitpunkt, wenn die Zugriffsverletzung durch Erzwingen einer Garbage Collection vor jedem verwalteten Übergang auftritt.</span><span class="sxs-lookup"><span data-stu-id="41cd5-112">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="41cd5-113">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="41cd5-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="41cd5-114">Löst immer eine Garbage Collection aus, wenn der Übergang eines Threads von nicht verwaltetem zu verwaltetem Code erfolgt.</span><span class="sxs-lookup"><span data-stu-id="41cd5-114">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="41cd5-115">Output</span><span class="sxs-lookup"><span data-stu-id="41cd5-115">Output</span></span>  
 <span data-ttu-id="41cd5-116">Dieser MDA erzeugt keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="41cd5-116">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="41cd5-117">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="41cd5-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="41cd5-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41cd5-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="41cd5-119">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="41cd5-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="41cd5-120">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="41cd5-120">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)
- [<span data-ttu-id="41cd5-121">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="41cd5-121">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
