---
title: dirtyCastAndCallOnInterface-MDA
description: Überprüfen Sie den dirtyCastAndCallOnInterface-Assistenten für verwaltetes Debuggen, der aufgerufen wird, wenn frühe gebundene Vtable-Aufrufe an nur spät gebundene Klassen Schnittstellen durchgeführt werden.
ms.date: 03/30/2017
helpviewer_keywords:
- managed debugging assistants (MDAs), early bound calls AutoDispatch
- dispatch-only mode
- dirtyCastAndCallOnInterface
- early-bound managed classes
- early bound calls on AutoDispatch
- MDAs (managed debugging assistants), early bound calls AutoDispatch
- EarlyBoundCallOnAutorDispatchClassInteface MDA
ms.assetid: aa388ed3-7e3d-48ea-a0b5-c47ae19cec38
ms.openlocfilehash: 2ed5589909915a261a22c48490e469ae52659c8c
ms.sourcegitcommit: a2c8b19e813a52b91facbb5d7e3c062c7188b457
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2020
ms.locfileid: "85416069"
---
# <a name="dirtycastandcalloninterface-mda"></a><span data-ttu-id="b9225-103">dirtyCastAndCallOnInterface-MDA</span><span class="sxs-lookup"><span data-stu-id="b9225-103">dirtyCastAndCallOnInterface MDA</span></span>
<span data-ttu-id="b9225-104">Der `dirtyCastAndCallOnInterface`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn für eine Klassenschnittstelle, die für ausschließlich späte Bindung gekennzeichnet ist, ein früh gebundener Aufruf über eine Vtable erfolgt.</span><span class="sxs-lookup"><span data-stu-id="b9225-104">The `dirtyCastAndCallOnInterface` managed debugging assistant (MDA) is activated when an early-bound call through a vtable is attempted on a class interface that has been marked late-bound only.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="b9225-105">Symptome</span><span class="sxs-lookup"><span data-stu-id="b9225-105">Symptoms</span></span>  
 <span data-ttu-id="b9225-106">Eine Anwendung löst eine Zugriffsverletzung aus oder zeigt unerwartetes Verhalten, wenn ein früh gebundener Aufruf über COM in die CLR erfolgt</span><span class="sxs-lookup"><span data-stu-id="b9225-106">An application throws an access violation or has unexpected behavior when placing an early-bound call via COM into the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="b9225-107">Ursache</span><span class="sxs-lookup"><span data-stu-id="b9225-107">Cause</span></span>  
 <span data-ttu-id="b9225-108">Code versucht einen früh gebundenen Aufruf durch eine Vtable über eine Klassenschnittstelle, die nur spät gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="b9225-108">Code is attempting an early-bound call through a vtable via a class interface that is late-bound only.</span></span> <span data-ttu-id="b9225-109">Beachten Sie, dass Klassenschnittstellen standardmäßig als ausschließlich spät gebunden gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b9225-109">Note that by default class interfaces are identified as being late-bound only.</span></span> <span data-ttu-id="b9225-110">Sie können aber auch mit dem <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>-Attribut mit einem <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch>-Wert (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`) als spät gebunden gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b9225-110">They can also be identified as late-bound with the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute with an <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> value (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="b9225-111">Lösung</span><span class="sxs-lookup"><span data-stu-id="b9225-111">Resolution</span></span>  
 <span data-ttu-id="b9225-112">Die empfohlene Lösung besteht darin, eine explizite Schnittstelle für die Verwendung durch COM zu definieren und Aufrufe von COM-Clients über diese Schnittstelle erfolgen zu lassen, nicht über die automatisch generierte Klassenschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b9225-112">The recommended resolution is to define an explicit interface for use by COM and have the COM clients call through this interface instead of through the automatically generated class interface.</span></span> <span data-ttu-id="b9225-113">Alternativ kann der Aufruf aus COM über `IDispatch` in einen spät gebundenen Aufruf transformiert werden.</span><span class="sxs-lookup"><span data-stu-id="b9225-113">Alternatively, the call from COM can be transformed into a late-bound call via `IDispatch`.</span></span>  
  
 <span data-ttu-id="b9225-114">Schließlich kann die Klasse auch als <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) gekennzeichnet werden, um früh gebundene Aufrufe aus COM zuzulassen. Wegen der unter <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> beschriebenen Versionseinschränkungen wird jedoch dringend davon abgeraten, <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9225-114">Finally, it is possible to identify the class as <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) to allow early bound calls to be placed from COM; however, using <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> is strongly discouraged because of the versioning limitations described in <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b9225-115">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b9225-115">Effect on the Runtime</span></span>  
 <span data-ttu-id="b9225-116">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="b9225-116">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="b9225-117">Er meldet nur Daten über früh gebundene Aufrufe für spät gebundene Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="b9225-117">It only reports data about early-bound calls on late-bound interfaces.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b9225-118">Output</span><span class="sxs-lookup"><span data-stu-id="b9225-118">Output</span></span>  
 <span data-ttu-id="b9225-119">Der Name der Methode oder des Felds, auf die oder das über frühe Bindung zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="b9225-119">The name of the method or name of the field being accessed early-bound.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="b9225-120">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b9225-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9225-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b9225-121">See also</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [<span data-ttu-id="b9225-122">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="b9225-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
