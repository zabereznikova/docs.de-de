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
ms.openlocfilehash: dfaa77adef7cdc21b1ad8abaca1439361a33d4b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33386625"
---
# <a name="gcunmanagedtomanaged-mda"></a><span data-ttu-id="ddb2f-102">gcUnmanagedToManaged-MDA</span><span class="sxs-lookup"><span data-stu-id="ddb2f-102">gcUnmanagedToManaged MDA</span></span>
<span data-ttu-id="ddb2f-103">Der `gcUnmanagedToManaged`-Assistent für verwaltetes Debuggen (MDA) bewirkt eine Garbage Collection bei jedem Übergang eines Threads von nicht verwaltetem zu verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="ddb2f-103">The `gcUnmanagedToManaged` managed debugging assistant (MDA) causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="ddb2f-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="ddb2f-104">Symptoms</span></span>  
 <span data-ttu-id="ddb2f-105">Eine Anwendung, die mithilfe von COM und Plattformaufrufen nicht verwaltete Benutzerkomponenten ausführt, verursacht eine nicht deterministische Zugriffsverletzung in der CLR.</span><span class="sxs-lookup"><span data-stu-id="ddb2f-105">An application running unmanaged user components using COM and platform invoke is causing a nondeterministic access violation in the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="ddb2f-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="ddb2f-106">Cause</span></span>  
 <span data-ttu-id="ddb2f-107">Wenn eine Anwendung nicht verwaltete Benutzerkomponenten ausführt, haben diese Komponenten möglicherweise den Heap der Garbage Collection beschädigt.</span><span class="sxs-lookup"><span data-stu-id="ddb2f-107">If an application is running unmanaged user components, then those components might have corrupted the garbage-collected heap.</span></span> <span data-ttu-id="ddb2f-108">Dies verursacht eine Zugriffsverletzung in der CLR, wenn der Garbage Collector versucht, das Objektdiagramm zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="ddb2f-108">This causes an access violation in the CLR when the garbage collector tries to walk the object graph.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="ddb2f-109">Auflösung</span><span class="sxs-lookup"><span data-stu-id="ddb2f-109">Resolution</span></span>  
 <span data-ttu-id="ddb2f-110">Das Aktivieren dieses Assistenten verringert die Zeit zwischen dem Zeitpunkt der Beschädigung des Heaps der Garbage Collection durch die nicht verwaltete Komponente und dem Zeitpunkt, wenn die Zugriffsverletzung durch Erzwingen einer Garbage Collection vor jedem verwalteten Übergang auftritt.</span><span class="sxs-lookup"><span data-stu-id="ddb2f-110">Enabling this assistant reduces the time between when the unmanaged component corrupts the garbage-collected heap and when the access violation happens by forcing a garbage collection to occur before every managed transition.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="ddb2f-111">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="ddb2f-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="ddb2f-112">Löst immer eine Garbage Collection aus, wenn der Übergang eines Threads von nicht verwaltetem zu verwaltetem Code erfolgt.</span><span class="sxs-lookup"><span data-stu-id="ddb2f-112">Causes a garbage collection whenever a thread transitions from unmanaged to managed code.</span></span>  
  
## <a name="output"></a><span data-ttu-id="ddb2f-113">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="ddb2f-113">Output</span></span>  
 <span data-ttu-id="ddb2f-114">Dieser MDA erzeugt keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="ddb2f-114">This MDA produces no output.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="ddb2f-115">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ddb2f-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <gcUnmanagedToManaged/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ddb2f-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddb2f-116">See Also</span></span>  
 <xref:System.Runtime.InteropServices.MarshalAsAttribute>  
 [<span data-ttu-id="ddb2f-117">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="ddb2f-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="ddb2f-118">gcManagedToUnmanaged</span><span class="sxs-lookup"><span data-stu-id="ddb2f-118">gcManagedToUnmanaged</span></span>](../../../docs/framework/debug-trace-profile/gcmanagedtounmanaged-mda.md)  
 [<span data-ttu-id="ddb2f-119">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="ddb2f-119">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
