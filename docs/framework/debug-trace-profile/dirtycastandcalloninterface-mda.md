---
title: dirtyCastAndCallOnInterface-MDA
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a28820479ca15ad72475ae9a7754bbbf99ce5c5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108588"
---
# <a name="dirtycastandcalloninterface-mda"></a><span data-ttu-id="69fe9-102">dirtyCastAndCallOnInterface-MDA</span><span class="sxs-lookup"><span data-stu-id="69fe9-102">dirtyCastAndCallOnInterface MDA</span></span>
<span data-ttu-id="69fe9-103">Der `dirtyCastAndCallOnInterface`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn für eine Klassenschnittstelle, die für ausschließlich späte Bindung gekennzeichnet ist, ein früh gebundener Aufruf über eine Vtable erfolgt.</span><span class="sxs-lookup"><span data-stu-id="69fe9-103">The `dirtyCastAndCallOnInterface` managed debugging assistant (MDA) is activated when an early-bound call through a vtable is attempted on a class interface that has been marked late-bound only.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="69fe9-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="69fe9-104">Symptoms</span></span>  
 <span data-ttu-id="69fe9-105">Eine Anwendung löst eine Zugriffsverletzung aus oder zeigt unerwartetes Verhalten, wenn ein früh gebundener Aufruf über COM in die CLR erfolgt</span><span class="sxs-lookup"><span data-stu-id="69fe9-105">An application throws an access violation or has unexpected behavior when placing an early-bound call via COM into the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="69fe9-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="69fe9-106">Cause</span></span>  
 <span data-ttu-id="69fe9-107">Code versucht einen früh gebundenen Aufruf durch eine Vtable über eine Klassenschnittstelle, die nur spät gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="69fe9-107">Code is attempting an early-bound call through a vtable via a class interface that is late-bound only.</span></span> <span data-ttu-id="69fe9-108">Beachten Sie, dass Klassenschnittstellen standardmäßig als ausschließlich spät gebunden gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="69fe9-108">Note that by default class interfaces are identified as being late-bound only.</span></span> <span data-ttu-id="69fe9-109">Sie können aber auch mit dem <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>-Attribut mit einem <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch>-Wert (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`) als spät gebunden gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="69fe9-109">They can also be identified as late-bound with the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute with an <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> value (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="69fe9-110">Auflösung</span><span class="sxs-lookup"><span data-stu-id="69fe9-110">Resolution</span></span>  
 <span data-ttu-id="69fe9-111">Die empfohlene Lösung besteht darin, eine explizite Schnittstelle für die Verwendung durch COM zu definieren und Aufrufe von COM-Clients über diese Schnittstelle erfolgen zu lassen, nicht über die automatisch generierte Klassenschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="69fe9-111">The recommended resolution is to define an explicit interface for use by COM and have the COM clients call through this interface instead of through the automatically generated class interface.</span></span> <span data-ttu-id="69fe9-112">Alternativ kann der Aufruf aus COM über `IDispatch` in einen spät gebundenen Aufruf transformiert werden.</span><span class="sxs-lookup"><span data-stu-id="69fe9-112">Alternatively, the call from COM can be transformed into a late-bound call via `IDispatch`.</span></span>  
  
 <span data-ttu-id="69fe9-113">Schließlich kann die Klasse auch als <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) gekennzeichnet werden, um früh gebundene Aufrufe aus COM zuzulassen. Wegen der unter <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> beschriebenen Versionseinschränkungen wird jedoch dringend davon abgeraten, <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="69fe9-113">Finally, it is possible to identify the class as <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) to allow early bound calls to be placed from COM; however, using <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> is strongly discouraged because of the versioning limitations described in <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="69fe9-114">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="69fe9-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="69fe9-115">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="69fe9-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="69fe9-116">Er meldet nur Daten über früh gebundene Aufrufe für spät gebundene Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="69fe9-116">It only reports data about early-bound calls on late-bound interfaces.</span></span>  
  
## <a name="output"></a><span data-ttu-id="69fe9-117">Output</span><span class="sxs-lookup"><span data-stu-id="69fe9-117">Output</span></span>  
 <span data-ttu-id="69fe9-118">Der Name der Methode oder des Felds, auf die oder das über frühe Bindung zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="69fe9-118">The name of the method or name of the field being accessed early-bound.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="69fe9-119">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="69fe9-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="69fe9-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69fe9-120">See also</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [<span data-ttu-id="69fe9-121">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="69fe9-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
