---
title: NonComVisibleBaseClass-MDA
description: Weitere Informationen finden Sie unter nonComVisibleBaseClass Managed Debug Assistant (MDA), der für QueryInterface-Aufrufe von nativem Code aufgerufen wird, der mit COR_E_INVALIDOPERATION fehlschlägt.
ms.date: 03/30/2017
helpviewer_keywords:
- visible classes
- managed debugging assistants (MDAs), COM visible classes
- nonComVisibleBaseClass MDA
- COM visible classes
- QueryInterface call failures
- MDAs (managed debugging assistants), COM visible classes
ms.assetid: 9ec1af27-604b-477e-9ee2-e833eb10d3ce
ms.openlocfilehash: 9f32b2c57f50fcd900b1fd78f4f8df1ec656a6db
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85803918"
---
# <a name="noncomvisiblebaseclass-mda"></a><span data-ttu-id="5f19b-103">NonComVisibleBaseClass-MDA</span><span class="sxs-lookup"><span data-stu-id="5f19b-103">nonComVisibleBaseClass MDA</span></span>
<span data-ttu-id="5f19b-104">Der `nonComVisibleBaseClass`-MDA (Managed Debugging Assistant, Assistent für verwaltetes Debuggen) wird aktiviert, wenn durch systemeigenen oder nicht verwalteten Code ein `QueryInterface`-Aufruf für den COM Callable Wrapper (CCW) einer für COM sichtbaren verwalteten Klasse erfolgt, die von einer für COM nicht sichtbaren Basisklasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="5f19b-104">The `nonComVisibleBaseClass` managed debugging assistant (MDA) is activated when a `QueryInterface` call is made by native or unmanaged code on the COM callable wrapper (CCW) of a COM-visible managed class that derives from a base class that is not COM visible.</span></span>  <span data-ttu-id="5f19b-105">Der `QueryInterface`-Aufruf führt nur in den Fällen zur Aktivierung des MDA, in denen der Aufruf die Klassenschnittstelle oder die `IDispatch`-Standardschnittstelle der für COM sichtbaren verwalteten Klasse anfordert.</span><span class="sxs-lookup"><span data-stu-id="5f19b-105">The `QueryInterface` call causes the MDA to activate only in cases where call requests the class interface or default `IDispatch` of the COM-visible managed class.</span></span>  <span data-ttu-id="5f19b-106">Der MDA wird nicht aktiviert, wenn mit dem `QueryInterface`-Aufruf eine explizite Schnittstelle angefordert wird, auf die das <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>-Attribut angewendet wurde und die von der für COM sichtbaren Klasse explizit implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="5f19b-106">The MDA is not activated when the `QueryInterface` is for an explicit interface that has the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute applied and is explicitly implemented by the COM-visible class.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="5f19b-107">Symptome</span><span class="sxs-lookup"><span data-stu-id="5f19b-107">Symptoms</span></span>  
 <span data-ttu-id="5f19b-108">Ein `QueryInterface`-Aufruf von systemeigenem Code, der zu einem HRESULT COR_E_INVALIDOPERATION führt.</span><span class="sxs-lookup"><span data-stu-id="5f19b-108">A `QueryInterface` call made from native code that is failing with a COR_E_INVALIDOPERATION HRESULT.</span></span>  <span data-ttu-id="5f19b-109">Das HRESULT ist möglicherweise darauf zurückzuführen, dass die Laufzeit keine `QueryInterface`-Aufrufe zulässt, die zur Aktivierung dieses MDA führen würden.</span><span class="sxs-lookup"><span data-stu-id="5f19b-109">The HRESULT might be due to the runtime disallowing `QueryInterface` calls that would cause the activation of this MDA.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="5f19b-110">Ursache</span><span class="sxs-lookup"><span data-stu-id="5f19b-110">Cause</span></span>  
 <span data-ttu-id="5f19b-111">Aufgrund von potenziellen Versionsproblemen kann die Laufzeit keine `QueryInterface`-Aufrufe für die Klassenschnittstelle oder für die `IDispatch`-Standardschnittstelle einer für COM sichtbaren Klasse zulassen, die von einer für COM nicht sichtbaren Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="5f19b-111">The runtime cannot allow `QueryInterface` calls for the class interface or default `IDispatch` interface of a COM-visible class that derives from a class that is not COM-visible because of potential versioning problems.</span></span>  <span data-ttu-id="5f19b-112">Beispiel: Falls der für COM nicht sichtbaren Basisklasse öffentliche Member hinzugefügt würden, könnten vorhandene COM-Clients, die die abgeleitete Klasse verwenden, beschädigt werden, weil die vtable der abgeleiteten Klasse, die die Member der Basisklasse enthält, hierbei geändert würde.</span><span class="sxs-lookup"><span data-stu-id="5f19b-112">For example, if any public members were added to the base class that is not COM-visible, existing COM clients using the derived class could potentially break because the vtable of the derived class, which contains the base class members, would be altered by such a change.</span></span>  <span data-ttu-id="5f19b-113">Bei expliziten Schnittstellen, die für COM verfügbar gemacht wurden, tritt dieses Problem nicht auf, weil deren vtable die Basismember der Schnittstellen nicht enthält.</span><span class="sxs-lookup"><span data-stu-id="5f19b-113">Explicit interfaces exposed to COM do not have this problem because they do not include the base members of interfaces in the vtable.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="5f19b-114">Lösung</span><span class="sxs-lookup"><span data-stu-id="5f19b-114">Resolution</span></span>  
 <span data-ttu-id="5f19b-115">Machen Sie die Klassenschnittstelle nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5f19b-115">Do not expose the class interface.</span></span> <span data-ttu-id="5f19b-116">Definieren Sie eine explizite Schnittstelle, und wenden Sie das <xref:System.Runtime.InteropServices.ClassInterfaceAttribute>-Attribut auf die Schnittstelle an.</span><span class="sxs-lookup"><span data-stu-id="5f19b-116">Define an explicit interface and apply the <xref:System.Runtime.InteropServices.ClassInterfaceAttribute> attribute to it.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="5f19b-117">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="5f19b-117">Effect on the Runtime</span></span>  
 <span data-ttu-id="5f19b-118">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="5f19b-118">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="5f19b-119">Output</span><span class="sxs-lookup"><span data-stu-id="5f19b-119">Output</span></span>  
 <span data-ttu-id="5f19b-120">Im Folgenden finden Sie eine Beispielmeldung für einen `QueryInterface`-Aufruf für die für COM sichtbare `Derived`-Klasse, die von der für COM nicht sichtbaren `Base`-Klasse abgeleitet ist.</span><span class="sxs-lookup"><span data-stu-id="5f19b-120">The following is an example message for a `QueryInterface` call on a COM-visible class `Derived` that derives from a non-COM-visible class `Base`.</span></span>  
  
```output
A QueryInterface call was made requesting the class interface of COM
visible managed class 'Derived'. However since this class derives from
non COM visible class 'Base', the QueryInterface call will fail. This
is done to prevent the non COM visible base class from being
constrained by the COM versioning rules.
```  
  
## <a name="configuration"></a><span data-ttu-id="5f19b-121">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="5f19b-121">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <nonComVisibleBaseClass />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5f19b-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5f19b-122">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="5f19b-123">Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen</span><span class="sxs-lookup"><span data-stu-id="5f19b-123">Diagnosing Errors with Managed Debugging Assistants</span></span>](diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="5f19b-124">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="5f19b-124">Interop Marshaling</span></span>](../interop/interop-marshaling.md)
