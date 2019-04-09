---
title: NonComVisibleBaseClass-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- visible classes
- managed debugging assistants (MDAs), COM visible classes
- nonComVisibleBaseClass MDA
- COM visible classes
- QueryInterface call failures
- MDAs (managed debugging assistants), COM visible classes
ms.assetid: 9ec1af27-604b-477e-9ee2-e833eb10d3ce
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb0810a9e0ffce825abecc87eb2698920209d86f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59171807"
---
# <a name="noncomvisiblebaseclass-mda"></a><span data-ttu-id="f8cd2-102">NonComVisibleBaseClass-MDA</span><span class="sxs-lookup"><span data-stu-id="f8cd2-102">nonComVisibleBaseClass MDA</span></span>
<span data-ttu-id="f8cd2-103">Der `nonComVisibleBaseClass`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn durch systemeigenen oder nicht verwalteten Code ein `QueryInterface`-Aufruf für den COM Callable Wrapper (CCW) einer für COM sichtbaren verwalteten Klasse erfolgt, die von einer für COM nicht sichtbaren Basisklasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="f8cd2-103">The `nonComVisibleBaseClass` managed debugging assistant (MDA) is activated when a `QueryInterface` call is made by native or unmanaged code on the COM callable wrapper (CCW) of a COM-visible managed class that derives from a base class that is not COM visible.</span></span>  <span data-ttu-id="f8cd2-104">Der `QueryInterface`-Aufruf führt nur in den Fällen zur Aktivierung des MDA, in denen der Aufruf die Klassenschnittstelle oder die `IDispatch`-Standardschnittstelle der für COM sichtbaren verwalteten Klasse anfordert.</span><span class="sxs-lookup"><span data-stu-id="f8cd2-104">The `QueryInterface` call causes the MDA to activate only in cases where call requests the class interface or default `IDispatch` of the COM-visible managed class.</span></span>  <span data-ttu-id="f8cd2-105">Der MDA wird nicht aktiviert, wenn mit dem `QueryInterface`-Aufruf eine explizite Schnittstelle angefordert wird, auf die das <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>-Attribut angewendet wurde und die von der für COM sichtbaren Klasse explizit implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="f8cd2-105">The MDA is not activated when the `QueryInterface` is for an explicit interface that has the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute applied and is explicitly implemented by the COM-visible class.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f8cd2-106">Symptome</span><span class="sxs-lookup"><span data-stu-id="f8cd2-106">Symptoms</span></span>  
 <span data-ttu-id="f8cd2-107">Ein `QueryInterface`-Aufruf von systemeigenem Code, der zu einem HRESULT COR_E_INVALIDOPERATION führt.</span><span class="sxs-lookup"><span data-stu-id="f8cd2-107">A `QueryInterface` call made from native code that is failing with a COR_E_INVALIDOPERATION HRESULT.</span></span>  <span data-ttu-id="f8cd2-108">Das HRESULT ist möglicherweise darauf zurückzuführen, dass die Laufzeit keine `QueryInterface`-Aufrufe zulässt, die zur Aktivierung dieses MDA führen würden.</span><span class="sxs-lookup"><span data-stu-id="f8cd2-108">The HRESULT might be due to the runtime disallowing `QueryInterface` calls that would cause the activation of this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f8cd2-109">Ursache</span><span class="sxs-lookup"><span data-stu-id="f8cd2-109">Cause</span></span>  
 <span data-ttu-id="f8cd2-110">Aufgrund von potenziellen Versionsproblemen kann die Laufzeit keine `QueryInterface`-Aufrufe für die Klassenschnittstelle oder für die `IDispatch`-Standardschnittstelle einer für COM sichtbaren Klasse zulassen, die von einer für COM nicht sichtbaren Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="f8cd2-110">The runtime cannot allow `QueryInterface` calls for the class interface or default `IDispatch` interface of a COM-visible class that derives from a class that is not COM-visible because of potential versioning problems.</span></span>  <span data-ttu-id="f8cd2-111">Beispiel: Falls der für COM nicht sichtbaren Basisklasse öffentliche Member hinzugefügt würden, könnten vorhandene COM-Clients, die die abgeleitete Klasse verwenden, beschädigt werden, weil die vtable der abgeleiteten Klasse, die die Member der Basisklasse enthält, hierbei geändert würde.</span><span class="sxs-lookup"><span data-stu-id="f8cd2-111">For example, if any public members were added to the base class that is not COM-visible, existing COM clients using the derived class could potentially break because the vtable of the derived class, which contains the base class members, would be altered by such a change.</span></span>  <span data-ttu-id="f8cd2-112">Bei expliziten Schnittstellen, die für COM verfügbar gemacht wurden, tritt dieses Problem nicht auf, weil deren vtable die Basismember der Schnittstellen nicht enthält.</span><span class="sxs-lookup"><span data-stu-id="f8cd2-112">Explicit interfaces exposed to COM do not have this problem because they do not include the base members of interfaces in the vtable.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f8cd2-113">Auflösung</span><span class="sxs-lookup"><span data-stu-id="f8cd2-113">Resolution</span></span>  
 <span data-ttu-id="f8cd2-114">Machen Sie die Klassenschnittstelle nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f8cd2-114">Do not expose the class interface.</span></span> <span data-ttu-id="f8cd2-115">Definieren Sie eine explizite Schnittstelle, und wenden Sie das <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>-Attribut auf die Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="f8cd2-115">Define an explicit interface and apply the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute to it.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f8cd2-116">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f8cd2-116">Effect on the Runtime</span></span>  
 <span data-ttu-id="f8cd2-117">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="f8cd2-117">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f8cd2-118">Output</span><span class="sxs-lookup"><span data-stu-id="f8cd2-118">Output</span></span>  
 <span data-ttu-id="f8cd2-119">Im Folgenden finden Sie eine Beispielmeldung für einen `QueryInterface`-Aufruf für die für COM sichtbare `Derived`-Klasse, die von der für COM nicht sichtbaren `Base`-Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="f8cd2-119">The following is an example message for a `QueryInterface` call on a COM-visible class `Derived` that derives from a non-COM-visible class `Base`.</span></span>  
  
```  
A QueryInterface call was made requesting the class interface of COM   
visible managed class 'Derived'. However since this class derives from   
non COM visible class 'Base', the QueryInterface call will fail. This   
is done to prevent the non COM visible base class from being   
constrained by the COM versioning rules.   
```  
  
## <a name="configuration"></a><span data-ttu-id="f8cd2-120">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="f8cd2-120">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <nonComVisibleBaseClass />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f8cd2-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8cd2-121">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f8cd2-122">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="f8cd2-122">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f8cd2-123">Interop-Marshalling</span><span class="sxs-lookup"><span data-stu-id="f8cd2-123">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
