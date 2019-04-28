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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0ecb05dba70dc9c8aba7f04928fd0ab49c900c8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61873950"
---
# <a name="reportavoncomrelease-mda"></a><span data-ttu-id="8ed01-102">reportAvOnComRelease-MDA</span><span class="sxs-lookup"><span data-stu-id="8ed01-102">reportAvOnComRelease MDA</span></span>
<span data-ttu-id="8ed01-103">Der `reportAvOnComRelease`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn aufgrund von Fehlern bei der Benutzerverweiszählung Ausnahmen ausgelöst werden, während COM-Interop durchgeführt und die <xref:System.Runtime.InteropServices.Marshal.Release%2A>- oder die <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A>-Methode in Kombination mit Rohdaten-COM-Aufrufen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8ed01-103">The `reportAvOnComRelease` managed debugging assistant (MDA) is activated when exceptions are thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8ed01-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="8ed01-104">Symptoms</span></span>  
 <span data-ttu-id="8ed01-105">Zugriffsverletzungen und Speicherschäden.</span><span class="sxs-lookup"><span data-stu-id="8ed01-105">Access violations and memory corruption.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8ed01-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="8ed01-106">Cause</span></span>  
 <span data-ttu-id="8ed01-107">Es kann vorkommen, dass durch Fehler bei der Benutzerverweiszählung eine Ausnahme ausgelöst wird, während COM-Interop durchgeführt und die <xref:System.Runtime.InteropServices.Marshal.Release%2A>- oder die <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A>-Methode in Kombination mit Rohdaten-COM-Aufrufen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8ed01-107">Occasionally, an exception is thrown due to user reference counting errors while performing COM interop and using the <xref:System.Runtime.InteropServices.Marshal.Release%2A> or <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> method combined with raw COM calls.</span></span> <span data-ttu-id="8ed01-108">Normalerweise wird diese Ausnahme verworfen, da es andernfalls zu einer Zugriffsverletzung in der CLR kommen kann, wodurch diese beendet wird.</span><span class="sxs-lookup"><span data-stu-id="8ed01-108">Normally, this exception is discarded because not doing so would cause an access violation in the CLR, bringing it down.</span></span> <span data-ttu-id="8ed01-109">Ist dieser Assistent aktiviert, können solche Ausnahmen festgestellt und gemeldet werden, anstatt sie einfach zu verwerfen.</span><span class="sxs-lookup"><span data-stu-id="8ed01-109">When this assistant is enabled, such exceptions can be detected and reported instead of being simply discarded.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8ed01-110">Auflösung</span><span class="sxs-lookup"><span data-stu-id="8ed01-110">Resolution</span></span>  
 <span data-ttu-id="8ed01-111">Überprüfen Sie den Verweiszählungscode und prüfen Sie auch die systemeigenen Clients Ihres Objekts auf Fehler bei der Verweiszählung.</span><span class="sxs-lookup"><span data-stu-id="8ed01-111">Examine your reference counting code and search for errors as well as examining the native clients of your object for reference counting errors.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8ed01-112">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="8ed01-112">Effect on the Runtime</span></span>  
 <span data-ttu-id="8ed01-113">Es sind zwei Modi verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8ed01-113">Two modes are available.</span></span> <span data-ttu-id="8ed01-114">Ist das `allowAv`-Attribut `true`, verhindert der Assistent, dass die Laufzeit die Zugriffsverletzung verwirft.</span><span class="sxs-lookup"><span data-stu-id="8ed01-114">If the `allowAv` attribute is `true`, the assistant prevents the runtime from discarding the access violation.</span></span> <span data-ttu-id="8ed01-115">Hat `allowAv` den Standardwert `false`, verwirft die Laufzeit die Zugriffsverletzung und der Benutzer erhält die Warnmeldung, dass eine Ausnahme ausgelöst und verworfen wurde.</span><span class="sxs-lookup"><span data-stu-id="8ed01-115">If `allowAv` is `false`, which is the default, the runtime discards the access violation, but a warning message is reported to the user to indicate that an exception was thrown and discarded.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8ed01-116">Output</span><span class="sxs-lookup"><span data-stu-id="8ed01-116">Output</span></span>  
 <span data-ttu-id="8ed01-117">Wenn möglich, enthält die Ausgabe den ursprünglichen vtable des COM-Schnittstellenzeigers.</span><span class="sxs-lookup"><span data-stu-id="8ed01-117">If possible, the output contains the COM interface pointer's original vtable.</span></span> <span data-ttu-id="8ed01-118">Andernfalls wird eine Informationsmeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ed01-118">Otherwise, an informational message is displayed.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8ed01-119">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8ed01-119">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <reportAvOnComRelease />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ed01-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ed01-120">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="8ed01-121">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="8ed01-121">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="8ed01-122">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="8ed01-122">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
