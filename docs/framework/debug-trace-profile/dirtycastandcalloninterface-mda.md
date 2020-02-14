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
ms.openlocfilehash: 6e4f0074958e8a6a8ca322968e9c29e89481c0c8
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77216515"
---
# <a name="dirtycastandcalloninterface-mda"></a><span data-ttu-id="b9c59-102">dirtyCastAndCallOnInterface-MDA</span><span class="sxs-lookup"><span data-stu-id="b9c59-102">dirtyCastAndCallOnInterface MDA</span></span>
<span data-ttu-id="b9c59-103">Der `dirtyCastAndCallOnInterface`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn für eine Klassenschnittstelle, die für ausschließlich späte Bindung gekennzeichnet ist, ein früh gebundener Aufruf über eine Vtable erfolgt.</span><span class="sxs-lookup"><span data-stu-id="b9c59-103">The `dirtyCastAndCallOnInterface` managed debugging assistant (MDA) is activated when an early-bound call through a vtable is attempted on a class interface that has been marked late-bound only.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="b9c59-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="b9c59-104">Symptoms</span></span>  
 <span data-ttu-id="b9c59-105">Eine Anwendung löst eine Zugriffsverletzung aus oder zeigt unerwartetes Verhalten, wenn ein früh gebundener Aufruf über COM in die CLR erfolgt</span><span class="sxs-lookup"><span data-stu-id="b9c59-105">An application throws an access violation or has unexpected behavior when placing an early-bound call via COM into the CLR.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="b9c59-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="b9c59-106">Cause</span></span>  
 <span data-ttu-id="b9c59-107">Code versucht einen früh gebundenen Aufruf durch eine Vtable über eine Klassenschnittstelle, die nur spät gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="b9c59-107">Code is attempting an early-bound call through a vtable via a class interface that is late-bound only.</span></span> <span data-ttu-id="b9c59-108">Beachten Sie, dass Klassenschnittstellen standardmäßig als ausschließlich spät gebunden gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b9c59-108">Note that by default class interfaces are identified as being late-bound only.</span></span> <span data-ttu-id="b9c59-109">Sie können aber auch mit dem <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>-Attribut mit einem <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch>-Wert (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`) als spät gebunden gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="b9c59-109">They can also be identified as late-bound with the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute with an <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDispatch> value (`[ClassInterface(ClassInterfaceType.AutoDispatch)]`).</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="b9c59-110">Lösung</span><span class="sxs-lookup"><span data-stu-id="b9c59-110">Resolution</span></span>  
 <span data-ttu-id="b9c59-111">Die empfohlene Lösung besteht darin, eine explizite Schnittstelle für die Verwendung durch COM zu definieren und Aufrufe von COM-Clients über diese Schnittstelle erfolgen zu lassen, nicht über die automatisch generierte Klassenschnittstelle.</span><span class="sxs-lookup"><span data-stu-id="b9c59-111">The recommended resolution is to define an explicit interface for use by COM and have the COM clients call through this interface instead of through the automatically generated class interface.</span></span> <span data-ttu-id="b9c59-112">Alternativ kann der Aufruf aus COM über `IDispatch` in einen spät gebundenen Aufruf transformiert werden.</span><span class="sxs-lookup"><span data-stu-id="b9c59-112">Alternatively, the call from COM can be transformed into a late-bound call via `IDispatch`.</span></span>  
  
 <span data-ttu-id="b9c59-113">Schließlich kann die Klasse auch als <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) gekennzeichnet werden, um früh gebundene Aufrufe aus COM zuzulassen. Wegen der unter <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> beschriebenen Versionseinschränkungen wird jedoch dringend davon abgeraten, <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b9c59-113">Finally, it is possible to identify the class as <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> (`[ClassInterface(ClassInterfaceType.AutoDual)]`) to allow early bound calls to be placed from COM; however, using <xref:System.Runtime.InteropServices.ClassInterfaceType.AutoDual> is strongly discouraged because of the versioning limitations described in <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b9c59-114">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b9c59-114">Effect on the Runtime</span></span>  
 <span data-ttu-id="b9c59-115">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="b9c59-115">This MDA has no effect on the CLR.</span></span> <span data-ttu-id="b9c59-116">Er meldet nur Daten über früh gebundene Aufrufe für spät gebundene Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="b9c59-116">It only reports data about early-bound calls on late-bound interfaces.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b9c59-117">Output</span><span class="sxs-lookup"><span data-stu-id="b9c59-117">Output</span></span>  
 <span data-ttu-id="b9c59-118">Der Name der Methode oder des Felds, auf die oder das über frühe Bindung zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="b9c59-118">The name of the method or name of the field being accessed early-bound.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="b9c59-119">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b9c59-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <dirtyCastAndCallOnInterface />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9c59-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b9c59-120">See also</span></span>

- <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>
- [<span data-ttu-id="b9c59-121">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="b9c59-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
