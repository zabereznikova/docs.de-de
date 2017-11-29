---
title: dirtyCastAndCallOnInterface-MDA
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managed debugging assistants (MDAs), early bound calls AutoDispatch
- dispatch-only mode
- dirtyCastAndCallOnInterface
- early-bound managed classes
- early bound calls on AutoDispatch
- MDAs (managed debugging assistants), early bound calls AutoDispatch
- EarlyBoundCallOnAutorDispatchClassInteface MDA
ms.assetid: aa388ed3-7e3d-48ea-a0b5-c47ae19cec38
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: eebbf48f084a0c0125bf40e5e14b8c71c1b0a6ec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="dirtycastandcalloninterface-mda"></a><span data-ttu-id="5bcb1-102">dirtyCastAndCallOnInterface-MDA</span><span class="sxs-lookup"><span data-stu-id="5bcb1-102">dirtyCastAndCallOnInterface MDA</span></span>
<span data-ttu-id="5bcb1-103">Der `dirtyCastAndCallOnInterface`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn für eine Klassenschnittstelle, die für ausschließlich späte Bindung gekennzeichnet ist, ein früh gebundener Aufruf über eine Vtable erfolgt.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-103">The `dirtyCastAndCallOnInterface` managed debugging assistant (MDA) is activated when an early-bound call through a vtable is attempted on a class interface that has been marked late-bound only.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="5bcb1-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="5bcb1-104">Symptoms</span></span>  
 <span data-ttu-id="5bcb1-105">Eine Anwendung löst eine Zugriffsverletzung aus oder zeigt unerwartetes Verhalten, wenn ein früh gebundener Aufruf über COM in die CLR erfolgt</span><span class="sxs-lookup"><span data-stu-id="5bcb1-105">An application throws an access violation or has unexpected behavior when placing an early-bound call via COM into the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="5bcb1-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="5bcb1-106">Cause</span></span>  
 <span data-ttu-id="5bcb1-107">Code versucht einen früh gebundenen Aufruf durch eine Vtable über eine Klassenschnittstelle, die nur spät gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-107">Code is attempting an early-bound call through a vtable via a class interface that is late-bound only.</span></span> <span data-ttu-id="5bcb1-108">Beachten Sie, dass Klassenschnittstellen standardmäßig als ausschließlich spät gebunden gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-108">Note that by default class interfaces are identified as being late-bound only.</span></span> <span data-ttu-id="5bcb1-109">Sie können aber auch mit dem <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>-Attribut mit einem <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch>-Wert (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`) als spät gebunden gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-109">They can also be identified as late-bound with the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute with an <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> value (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="5bcb1-110">Lösung</span><span class="sxs-lookup"><span data-stu-id="5bcb1-110">Resolution</span></span>  
 <span data-ttu-id="5bcb1-111">Die empfohlene Lösung besteht darin, eine explizite Schnittstelle für die Verwendung durch COM zu definieren und Aufrufe von COM-Clients über diese Schnittstelle erfolgen zu lassen, nicht über die automatisch generierte Klassenschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-111">The recommended resolution is to define an explicit interface for use by COM and have the COM clients call through this interface instead of through the automatically generated class interface.</span></span> <span data-ttu-id="5bcb1-112">Alternativ kann der Aufruf aus COM über `IDispatch` in einen spät gebundenen Aufruf umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-112">Alternatively, the call from COM can be transformed into a late-bound call via `IDispatch`.</span></span>  
  
 <span data-ttu-id="5bcb1-113">Schließlich kann die Klasse auch als <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) gekennzeichnet werden, um früh gebundene Aufrufe aus COM zuzulassen. Wegen der unter <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> beschriebenen Versionseinschränkungen wird jedoch dringend davon abgeraten, <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-113">Finally, it is possible to identify the class as <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) to allow early bound calls to be placed from COM; however, using <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> is strongly discouraged because of the versioning limitations described in <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="5bcb1-114">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="5bcb1-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="5bcb1-115">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="5bcb1-116">Er meldet nur Daten über früh gebundene Aufrufe für spät gebundene Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-116">It only reports data about early-bound calls on late-bound interfaces.</span></span>  
  
## <a name="output"></a><span data-ttu-id="5bcb1-117">Ausgabe</span><span class="sxs-lookup"><span data-stu-id="5bcb1-117">Output</span></span>  
 <span data-ttu-id="5bcb1-118">Der Name der Methode oder des Felds, auf die oder das über frühe Bindung zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="5bcb1-118">The name of the method or name of the field being accessed early-bound.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="5bcb1-119">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5bcb1-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5bcb1-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bcb1-120">See Also</span></span>  
 <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>  
 [<span data-ttu-id="5bcb1-121">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="5bcb1-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
