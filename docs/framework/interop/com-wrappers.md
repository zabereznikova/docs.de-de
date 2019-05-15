---
title: COM-Wrapper
ms.date: 03/30/2017
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 47fa0065bad76640b1ad8f61734c5749ec51286b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64613832"
---
# <a name="com-wrappers"></a><span data-ttu-id="4cc2f-102">COM-Wrapper</span><span class="sxs-lookup"><span data-stu-id="4cc2f-102">COM Wrappers</span></span>
<span data-ttu-id="4cc2f-103">COM unterscheidet sich vom .NET Framework-Objektmodell in mehreren wichtigen Punkten:</span><span class="sxs-lookup"><span data-stu-id="4cc2f-103">COM differs from the .NET Framework object model in several important ways:</span></span>  
  
- <span data-ttu-id="4cc2f-104">Clients von COM-Objekten müssen die Lebensdauer dieser Objekte verwalten. Die Common Language Runtime verwaltet die Lebensdauer der Objekte in ihrer Umgebung.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-104">Clients of COM objects must manage the lifetime of those objects; the common language runtime manages the lifetime of objects in its environment.</span></span>  
  
- <span data-ttu-id="4cc2f-105">Clients von COM-Objekten ermitteln, ob ein Dienst verfügbar ist, indem sie eine Schnittstelle anfordern, die diesen Dienst bereitstellt und einen Schnittstellenzeiger erhalten oder nicht.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-105">Clients of COM objects discover whether a service is available by requesting an interface that provides that service and getting back an interface pointer, or not.</span></span> <span data-ttu-id="4cc2f-106">Clients von .NET-Objekten erhalten durch Reflektion eine Beschreibung der Objektfunktionen.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-106">Clients of .NET objects can obtain a description of an object's functionality using reflection.</span></span>  
  
- <span data-ttu-id="4cc2f-107">NET-Objekte befinden sich im Arbeitsspeicher, der von der .NET Framework-Ausführungsumgebung verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-107">NET objects reside in memory managed by the .NET Framework execution environment.</span></span> <span data-ttu-id="4cc2f-108">Die Ausführungsumgebung kann Objekte im Arbeitsspeicher aus Leistungsgründen verschieben und alle Verweise auf die verschobenen Objekte aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-108">The execution environment can move objects around in memory for performance reasons and update all references to the objects it moves.</span></span> <span data-ttu-id="4cc2f-109">Nicht verwaltete Clients, die einen Zeiger auf ein Objekt erhalten haben, verlassen sich darauf, dass das Objekt am selben Speicherort verbleibt.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-109">Unmanaged clients, having obtained a pointer to an object, rely on the object to remain at the same location.</span></span> <span data-ttu-id="4cc2f-110">Diese Clients haben keinen Mechanismen für den Umgang mit einem Objekt, dessen Position nicht fest ist.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-110">These clients have no mechanism for dealing with an object whose location is not fixed.</span></span>  
  
 <span data-ttu-id="4cc2f-111">Um diese Unterschiede zu überwinden, stellt die Common Language Runtime Wrapperklassen bereit, um sowohl verwalteten als auch nicht verwalteten Clients den Eindruck zu geben, dass sie Objekte in ihrer jeweiligen Umgebung aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-111">To overcome these differences, the runtime provides wrapper classes to make both managed and unmanaged clients think they are calling objects within their respective environment.</span></span> <span data-ttu-id="4cc2f-112">Wenn Ihr verwalteter Client eine Methode für ein COM-Objekt aufruft, erstellt die Laufzeit einen [Runtime Callable Wrapper](runtime-callable-wrapper.md) (RCW).</span><span class="sxs-lookup"><span data-stu-id="4cc2f-112">Whenever your managed client calls a method on a COM object, the runtime creates a [runtime callable wrapper](runtime-callable-wrapper.md) (RCW).</span></span> <span data-ttu-id="4cc2f-113">RCWs abstrahieren unter anderem die Unterschiede zwischen verwalteten und nicht verwalteten Verweismechanismen.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-113">RCWs abstract the differences between managed and unmanaged reference mechanisms, among other things.</span></span> <span data-ttu-id="4cc2f-114">Die Common Language Runtime erstellt außerdem einen [COM Callable Wrapper](com-callable-wrapper.md) (CCW) zur Umkehrung dieses Prozesses. Der COM-Client kann eine Methode für ein .NET-Objekt nahtlos aufrufen.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-114">The runtime also creates a [COM callable wrapper](com-callable-wrapper.md) (CCW) to reverse the process, enabling a COM client to seamlessly call a method on a .NET object.</span></span> <span data-ttu-id="4cc2f-115">Wie in der folgenden Abbildung gezeigt, bestimmt die Perspektive des aufrufenden Codes die Wrapperklasse, die die Common Language Runtime erstellt.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-115">As the following illustration shows, the perspective of the calling code determines which wrapper class the runtime creates.</span></span>  
  
 ![Übersicht über COM-Wrapper](./media/com-wrappers/bidirectional-com-overview.gif)  
  
 <span data-ttu-id="4cc2f-117">In den meisten Fällen stellen die von der Common Language Runtime standardmäßig generierten RCW oder CCW ausreichend Marshalling für Aufrufe bereit, die die Anwendungsgrenze zwischen COM und dem .NET Framework überschreiten.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-117">In most cases, the standard RCW or CCW generated by the runtime provides adequate marshaling for calls that cross the boundary between COM and the .NET Framework.</span></span> <span data-ttu-id="4cc2f-118">Mithilfe von benutzerdefinierten Attributen können Sie optional anpassen, wie die Common Language Runtime verwalteten und nicht verwalteten Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="4cc2f-118">Using custom attributes, you can optionally adjust the way the runtime represents managed and unmanaged code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cc2f-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cc2f-119">See also</span></span>

- <span data-ttu-id="4cc2f-120">[Erweiterte COM-Interoperabilität](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4cc2f-120">[Advanced COM Interoperability](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))</span></span>
- [<span data-ttu-id="4cc2f-121">Runtime Callable Wrapper (RCW)</span><span class="sxs-lookup"><span data-stu-id="4cc2f-121">Runtime Callable Wrapper</span></span>](runtime-callable-wrapper.md)
- [<span data-ttu-id="4cc2f-122">COM Callable Wrapper</span><span class="sxs-lookup"><span data-stu-id="4cc2f-122">COM Callable Wrapper</span></span>](com-callable-wrapper.md)
- <span data-ttu-id="4cc2f-123">[Anpassen von Standardwrappern](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4cc2f-123">[Customizing Standard Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))</span></span>
- <span data-ttu-id="4cc2f-124">[Vorgehensweise: Anpassen von Runtime Callable Wrappern](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="4cc2f-124">[How to: Customize Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))</span></span>
