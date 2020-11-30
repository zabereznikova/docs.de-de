---
title: COM-Wrapper
description: COM-Clients und .NET-Objekte interagieren mithilfe eines COM Callable Wrapper und eines Runtime Callable Wrapper. Die CLR erstellt Wrapper automatisch.
ms.date: 03/30/2017
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
ms.openlocfilehash: 17a303cde5fa51cd940b0375d2c6657fcd354dc5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706327"
---
# <a name="com-wrappers"></a><span data-ttu-id="05b24-104">COM-Wrapper</span><span class="sxs-lookup"><span data-stu-id="05b24-104">COM Wrappers</span></span>

<span data-ttu-id="05b24-105">COM unterscheidet sich vom .NET Runtime-Objektmodell in mehreren wichtigen Punkten:</span><span class="sxs-lookup"><span data-stu-id="05b24-105">COM differs from the .NET runtime object model in several important ways:</span></span>  
  
- <span data-ttu-id="05b24-106">Clients von COM-Objekten müssen die Lebensdauer dieser Objekte verwalten. Die Common Language Runtime verwaltet die Lebensdauer der Objekte in ihrer Umgebung.</span><span class="sxs-lookup"><span data-stu-id="05b24-106">Clients of COM objects must manage the lifetime of those objects; the common language runtime manages the lifetime of objects in its environment.</span></span>  
  
- <span data-ttu-id="05b24-107">Clients von COM-Objekten ermitteln, ob ein Dienst verfügbar ist, indem sie eine Schnittstelle anfordern, die diesen Dienst bereitstellt und einen Schnittstellenzeiger erhalten oder nicht.</span><span class="sxs-lookup"><span data-stu-id="05b24-107">Clients of COM objects discover whether a service is available by requesting an interface that provides that service and getting back an interface pointer, or not.</span></span> <span data-ttu-id="05b24-108">Clients von .NET-Objekten erhalten durch Reflektion eine Beschreibung der Objektfunktionen.</span><span class="sxs-lookup"><span data-stu-id="05b24-108">Clients of .NET objects can obtain a description of an object's functionality using reflection.</span></span>  
  
- <span data-ttu-id="05b24-109">NET-Objekte befinden sich im Arbeitsspeicher, der von der .NET Runtime-Ausführungsumgebung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="05b24-109">NET objects reside in memory managed by the .NET runtime execution environment.</span></span> <span data-ttu-id="05b24-110">Die Ausführungsumgebung kann Objekte im Arbeitsspeicher aus Leistungsgründen verschieben und alle Verweise auf die verschobenen Objekte aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="05b24-110">The execution environment can move objects around in memory for performance reasons and update all references to the objects it moves.</span></span> <span data-ttu-id="05b24-111">Nicht verwaltete Clients, die einen Zeiger auf ein Objekt erhalten haben, verlassen sich darauf, dass das Objekt am selben Speicherort verbleibt.</span><span class="sxs-lookup"><span data-stu-id="05b24-111">Unmanaged clients, having obtained a pointer to an object, rely on the object to remain at the same location.</span></span> <span data-ttu-id="05b24-112">Diese Clients haben keinen Mechanismen für den Umgang mit einem Objekt, dessen Position nicht fest ist.</span><span class="sxs-lookup"><span data-stu-id="05b24-112">These clients have no mechanism for dealing with an object whose location is not fixed.</span></span>  
  
 <span data-ttu-id="05b24-113">Um diese Unterschiede zu überwinden, stellt die Common Language Runtime Wrapperklassen bereit, um sowohl verwalteten als auch nicht verwalteten Clients den Eindruck zu geben, dass sie Objekte in ihrer jeweiligen Umgebung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="05b24-113">To overcome these differences, the runtime provides wrapper classes to make both managed and unmanaged clients think they are calling objects within their respective environment.</span></span> <span data-ttu-id="05b24-114">Wenn Ihr verwalteter Client eine Methode für ein COM-Objekt aufruft, erstellt die Laufzeit einen [Runtime Callable Wrapper](runtime-callable-wrapper.md) (RCW).</span><span class="sxs-lookup"><span data-stu-id="05b24-114">Whenever your managed client calls a method on a COM object, the runtime creates a [runtime callable wrapper](runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="05b24-115">RCWs abstrahieren unter anderem die Unterschiede zwischen verwalteten und nicht verwalteten Verweismechanismen.</span><span class="sxs-lookup"><span data-stu-id="05b24-115">RCWs abstract the differences between managed and unmanaged reference mechanisms, among other things.</span></span> <span data-ttu-id="05b24-116">Die Common Language Runtime erstellt außerdem einen [COM Callable Wrapper](com-callable-wrapper.md) (CCW) zur Umkehrung dieses Prozesses. Der COM-Client kann eine Methode für ein .NET-Objekt nahtlos aufrufen.</span><span class="sxs-lookup"><span data-stu-id="05b24-116">The runtime also creates a [COM callable wrapper](com-callable-wrapper.md) (CCW) to reverse the process, enabling a COM client to seamlessly call a method on a .NET object.</span></span> <span data-ttu-id="05b24-117">Wie in der folgenden Abbildung gezeigt, bestimmt die Perspektive des aufrufenden Codes die Wrapperklasse, die die Common Language Runtime erstellt.</span><span class="sxs-lookup"><span data-stu-id="05b24-117">As the following illustration shows, the perspective of the calling code determines which wrapper class the runtime creates.</span></span>  
  
 ![Übersicht über COM-Wrapper](./media/com-wrappers/bidirectional-com-overview.gif)  
  
 <span data-ttu-id="05b24-119">In den meisten Fällen stellen die von der Common Language Runtime standardmäßig generierten RCW oder CCW ausreichend Marshalling für Aufrufe bereit, die die Anwendungsgrenze zwischen COM und der .NET Runtime überschreiten.</span><span class="sxs-lookup"><span data-stu-id="05b24-119">In most cases, the standard RCW or CCW generated by the runtime provides adequate marshaling for calls that cross the boundary between COM and the .NET runtime.</span></span> <span data-ttu-id="05b24-120">Mithilfe von benutzerdefinierten Attributen können Sie optional anpassen, wie die Common Language Runtime verwalteten und nicht verwalteten Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="05b24-120">Using custom attributes, you can optionally adjust the way the runtime represents managed and unmanaged code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05b24-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05b24-121">See also</span></span>

- <span data-ttu-id="05b24-122">[Erweiterte COM-Interoperabilität in .NET Framework](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="05b24-122">[Advanced COM Interoperability in .NET Framework](/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="05b24-123">Runtime Callable Wrapper (RCW)</span><span class="sxs-lookup"><span data-stu-id="05b24-123">Runtime Callable Wrapper</span></span>](runtime-callable-wrapper.md)
- [<span data-ttu-id="05b24-124">COM Callable Wrapper</span><span class="sxs-lookup"><span data-stu-id="05b24-124">COM Callable Wrapper</span></span>](com-callable-wrapper.md)
- <span data-ttu-id="05b24-125">[Anpassen von Standardwrappern in .NET Framework](/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="05b24-125">[Customizing Standard Wrappers in .NET Framework](/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))</span></span>
- <span data-ttu-id="05b24-126">[How to: Anpassen von Runtime Callable Wrappers in .NET Framework](/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="05b24-126">[How to: Customize Runtime Callable Wrappers in .NET Framework](/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))</span></span>
