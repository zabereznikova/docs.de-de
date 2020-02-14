---
title: reportAvOnComRelease-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), reference counting errors
- exceptions, reference counting errors
- ReportAvOnComRelease MDA
- COM release access violations
- user reference counting errors
- managed debugging assistants (MDAs), reference counting errors
- report access violation on Com release
- reference counting errors
ms.assetid: a2b86b63-08b2-4943-b344-3c2cf46ccd31
ms.openlocfilehash: fca6b209e6432678a264f10762adb3871e3596ce
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2020
ms.locfileid: "77217221"
---
# <a name="reportavoncomrelease-mda"></a><span data-ttu-id="b6ff3-102">reportAvOnComRelease-MDA</span><span class="sxs-lookup"><span data-stu-id="b6ff3-102">reportAvOnComRelease MDA</span></span>
<span data-ttu-id="b6ff3-103">Der `reportAvOnComRelease`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn aufgrund von Fehlern bei der Benutzerverweiszählung Ausnahmen ausgelöst werden, während COM-Interop durchgeführt und die <xref:System.Runtime.InteropServices.Marshal.Release%2A>- oder die <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A>-Methode in Kombination mit Rohdaten-COM-Aufrufen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b6ff3-103">The `reportAvOnComRelease` managed debugging assistant (MDA) is activated when exceptions are thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="b6ff3-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="b6ff3-104">Symptoms</span></span>  
 <span data-ttu-id="b6ff3-105">Zugriffsverletzungen und Speicherschäden.</span><span class="sxs-lookup"><span data-stu-id="b6ff3-105">Access violations and memory corruption.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="b6ff3-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="b6ff3-106">Cause</span></span>  
 <span data-ttu-id="b6ff3-107">Es kann vorkommen, dass durch Fehler bei der Benutzerverweiszählung eine Ausnahme ausgelöst wird, während COM-Interop durchgeführt und die <xref:System.Runtime.InteropServices.Marshal.Release%2A>- oder die <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A>-Methode in Kombination mit Rohdaten-COM-Aufrufen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b6ff3-107">Occasionally, an exception is thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span> <span data-ttu-id="b6ff3-108">Normalerweise wird diese Ausnahme verworfen, da es andernfalls zu einer Zugriffsverletzung in der CLR kommen kann, wodurch diese beendet wird.</span><span class="sxs-lookup"><span data-stu-id="b6ff3-108">Normally, this exception is discarded because not doing so would cause an access violation in the CLR, bringing it down.</span></span> <span data-ttu-id="b6ff3-109">Ist dieser Assistent aktiviert, können solche Ausnahmen festgestellt und gemeldet werden, anstatt sie einfach zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="b6ff3-109">When this assistant is enabled, such exceptions can be detected and reported instead of being simply discarded.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="b6ff3-110">Lösung</span><span class="sxs-lookup"><span data-stu-id="b6ff3-110">Resolution</span></span>  
 <span data-ttu-id="b6ff3-111">Überprüfen Sie den Verweiszählungscode und prüfen Sie auch die systemeigenen Clients Ihres Objekts auf Fehler bei der Verweiszählung.</span><span class="sxs-lookup"><span data-stu-id="b6ff3-111">Examine your reference counting code and search for errors as well as examining the native clients of your object for reference counting errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="b6ff3-112">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="b6ff3-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="b6ff3-113">Es sind zwei Modi verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b6ff3-113">Two modes are available.</span></span> <span data-ttu-id="b6ff3-114">Ist das `allowAv`-Attribut `true`, verhindert der Assistent, dass die Laufzeit die Zugriffsverletzung verwirft.</span><span class="sxs-lookup"><span data-stu-id="b6ff3-114">If the `allowAv` attribute is `true`, the assistant prevents the runtime from discarding the access violation.</span></span> <span data-ttu-id="b6ff3-115">Hat `allowAv` den Standardwert `false`, verwirft die Laufzeit die Zugriffsverletzung und der Benutzer erhält die Warnmeldung, dass eine Ausnahme ausgelöst und verworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="b6ff3-115">If `allowAv` is `false`, which is the default, the runtime discards the access violation, but a warning message is reported to the user to indicate that an exception was thrown and discarded.</span></span>  
  
## <a name="output"></a><span data-ttu-id="b6ff3-116">Output</span><span class="sxs-lookup"><span data-stu-id="b6ff3-116">Output</span></span>  
 <span data-ttu-id="b6ff3-117">Wenn möglich, enthält die Ausgabe den ursprünglichen vtable des COM-Schnittstellenzeigers.</span><span class="sxs-lookup"><span data-stu-id="b6ff3-117">If possible, the output contains the COM interface pointer's original vtable.</span></span> <span data-ttu-id="b6ff3-118">Andernfalls wird eine Informationsmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b6ff3-118">Otherwise, an informational message is displayed.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="b6ff3-119">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b6ff3-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b6ff3-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6ff3-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="b6ff3-121">Diagnosing Errors with Managed Debugging Assistants (Fehlerdiagnose mit den Assistenten für verwaltetes Debugging)</span><span class="sxs-lookup"><span data-stu-id="b6ff3-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="b6ff3-122">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="b6ff3-122">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
