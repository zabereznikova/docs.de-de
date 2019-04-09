---
title: gcUnmanagedToManaged-MDA
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66f662114868832f909d734a482e1dc9aefb841a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150879"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="36cae-102">gcUnmanagedToManaged-MDA</span><span class="sxs-lookup"><span data-stu-id="36cae-102">gcUnmanagedToManaged MDA</span></span>
<span data-ttu-id="36cae-103">Der `gcUnmanagedToManaged`-Assistent für verwaltetes Debuggen (MDA) bewirkt eine Garbage Collection bei jedem Übergang eines Threads von nicht verwaltetem zu verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="36cae-103">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="36cae-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="36cae-104">Symptoms</span></span>  
 <span data-ttu-id="36cae-105">Eine Anwendung, die mithilfe von COM und Plattformaufrufen nicht verwaltete Benutzerkomponenten ausführt, verursacht eine nicht deterministische Zugriffsverletzung in der CLR.</span><span class="sxs-lookup"><span data-stu-id="36cae-105">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="36cae-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="36cae-106">Cause</span></span>  
 <span data-ttu-id="36cae-107">Wenn eine Anwendung nicht verwaltete Benutzerkomponenten ausführt, haben diese Komponenten möglicherweise den Heap der Garbage Collection beschädigt.</span><span class="sxs-lookup"><span data-stu-id="36cae-107">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="36cae-108">Dies verursacht eine Zugriffsverletzung in der CLR, wenn der Garbage Collector versucht, das Objektdiagramm zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="36cae-108">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="36cae-109">Auflösung</span><span class="sxs-lookup"><span data-stu-id="36cae-109">Resolution</span></span>  
 <span data-ttu-id="36cae-110">Das Aktivieren dieses Assistenten verringert die Zeit zwischen dem Zeitpunkt der Beschädigung des Heaps der Garbage Collection durch die nicht verwaltete Komponente und dem Zeitpunkt, wenn die Zugriffsverletzung durch Erzwingen einer Garbage Collection vor jedem verwalteten Übergang auftritt.</span><span class="sxs-lookup"><span data-stu-id="36cae-110">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="36cae-111">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="36cae-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="36cae-112">Löst immer eine Garbage Collection aus, wenn der Übergang eines Threads von nicht verwaltetem zu verwaltetem Code erfolgt.</span><span class="sxs-lookup"><span data-stu-id="36cae-112">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="36cae-113">Output</span><span class="sxs-lookup"><span data-stu-id="36cae-113">Output</span></span>  
 <span data-ttu-id="36cae-114">Dieser MDA erzeugt keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="36cae-114">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="36cae-115">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="36cae-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="36cae-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36cae-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="36cae-117">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="36cae-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="36cae-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="36cae-118">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)
- [<span data-ttu-id="36cae-119">Interop-Marshalling</span><span class="sxs-lookup"><span data-stu-id="36cae-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
