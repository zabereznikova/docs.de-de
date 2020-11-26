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
ms.openlocfilehash: 61fbdbf0d3941aa3e876748ae4d76cd7ad0c0977
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244222"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="3bbb1-104">gcUnmanagedToManaged-MDA</span><span class="sxs-lookup"><span data-stu-id="3bbb1-104">gcUnmanagedToManaged MDA</span></span>

<span data-ttu-id="3bbb1-105">Der `gcUnmanagedToManaged`-Assistent für verwaltetes Debuggen (MDA) bewirkt eine Garbage Collection bei jedem Übergang eines Threads von nicht verwaltetem zu verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="3bbb1-105">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="3bbb1-106">Symptome</span><span class="sxs-lookup"><span data-stu-id="3bbb1-106">Symptoms</span></span>  

 <span data-ttu-id="3bbb1-107">Eine Anwendung, die mithilfe von COM und Plattformaufrufen nicht verwaltete Benutzerkomponenten ausführt, verursacht eine nicht deterministische Zugriffsverletzung in der CLR.</span><span class="sxs-lookup"><span data-stu-id="3bbb1-107">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="3bbb1-108">Ursache</span><span class="sxs-lookup"><span data-stu-id="3bbb1-108">Cause</span></span>  

 <span data-ttu-id="3bbb1-109">Wenn eine Anwendung nicht verwaltete Benutzerkomponenten ausführt, haben diese Komponenten möglicherweise den Heap der Garbage Collection beschädigt.</span><span class="sxs-lookup"><span data-stu-id="3bbb1-109">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="3bbb1-110">Dies verursacht eine Zugriffsverletzung in der CLR, wenn der Garbage Collector versucht, das Objektdiagramm zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="3bbb1-110">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="3bbb1-111">Lösung</span><span class="sxs-lookup"><span data-stu-id="3bbb1-111">Resolution</span></span>  

 <span data-ttu-id="3bbb1-112">Das Aktivieren dieses Assistenten verringert die Zeit zwischen dem Zeitpunkt der Beschädigung des Heaps der Garbage Collection durch die nicht verwaltete Komponente und dem Zeitpunkt, wenn die Zugriffsverletzung durch Erzwingen einer Garbage Collection vor jedem verwalteten Übergang auftritt.</span><span class="sxs-lookup"><span data-stu-id="3bbb1-112">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="3bbb1-113">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="3bbb1-113">Effect on the Runtime</span></span>  

 <span data-ttu-id="3bbb1-114">Löst immer eine Garbage Collection aus, wenn der Übergang eines Threads von nicht verwaltetem zu verwaltetem Code erfolgt.</span><span class="sxs-lookup"><span data-stu-id="3bbb1-114">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="3bbb1-115">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="3bbb1-115">Output</span></span>  

 <span data-ttu-id="3bbb1-116">Dieser MDA erzeugt keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="3bbb1-116">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="3bbb1-117">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="3bbb1-117">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3bbb1-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3bbb1-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="3bbb1-119">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="3bbb1-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="3bbb1-120">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="3bbb1-120">gcManagedToUnmanaged</span></span>](gcmanagedtounmanaged-mda.md)
- [<span data-ttu-id="3bbb1-121">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="3bbb1-121">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
