---
title: ICorDebugDebugEvent-Schnittstelle
ms.date: 03/30/2017
ms.assetid: a226737a-cb99-4e97-bd94-9a37094ded41
ms.openlocfilehash: d73857bd9d0d5dd9e5eff0c89dcc573ae0d93f0e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731877"
---
# <a name="icordebugdebugevent-interface"></a><span data-ttu-id="c7551-102">ICorDebugDebugEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c7551-102">ICorDebugDebugEvent Interface</span></span>

<span data-ttu-id="c7551-103">Definiert die Basisschnittstelle, von der alle `ICorDebug` Debug-Ereignisse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c7551-103">Defines the base interface from which all `ICorDebug` debug events derive.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c7551-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="c7551-104">Methods</span></span>  
  
|<span data-ttu-id="c7551-105">Methode</span><span class="sxs-lookup"><span data-stu-id="c7551-105">Method</span></span>|<span data-ttu-id="c7551-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c7551-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c7551-107">GetEventKind-Methode</span><span class="sxs-lookup"><span data-stu-id="c7551-107">GetEventKind Method</span></span>](icordebugdebugevent-geteventkind-method.md)|<span data-ttu-id="c7551-108">Gibt an, welche Art von Ereignis dieses `ICorDebugDebugEvent`-Objekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="c7551-108">Indicates what kind of event this `ICorDebugDebugEvent` object represents.</span></span>|  
|[<span data-ttu-id="c7551-109">GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="c7551-109">GetThread Method</span></span>](icordebugdebugevent-getthread-method.md)|<span data-ttu-id="c7551-110">Ruft den Thread auf, auf dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c7551-110">Gets the thread on which the event occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7551-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c7551-111">Remarks</span></span>  

 <span data-ttu-id="c7551-112">Die folgenden Schnittstellen sind aus der `ICorDebugDebugEvent`-Schnittstelle abgeleitet:</span><span class="sxs-lookup"><span data-stu-id="c7551-112">The following interfaces are derived from the `ICorDebugDebugEvent` interface:</span></span>  
  
- [<span data-ttu-id="c7551-113">ICorDebugExceptionDebugEvent</span><span class="sxs-lookup"><span data-stu-id="c7551-113">ICorDebugExceptionDebugEvent</span></span>](icordebugexceptiondebugevent-interface.md)  
  
- [<span data-ttu-id="c7551-114">ICorDebugModuleDebugEvent</span><span class="sxs-lookup"><span data-stu-id="c7551-114">ICorDebugModuleDebugEvent</span></span>](icordebugmoduledebugevent-interface.md)  
  
> [!NOTE]
> <span data-ttu-id="c7551-115">Diese Schnittstelle ist nur in Verbindung mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c7551-115">The interface is available with .NET Native only.</span></span> <span data-ttu-id="c7551-116">Bei dem Versuch, `QueryInterface` aufzurufen, um einen Schnittstellenzeiger abzurufen, wird für ICorDebug-Szenarien außerhalb von .NET Native `E_NOINTERFACE` zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c7551-116">Attempting to call `QueryInterface` to retrieve an interface pointer returns `E_NOINTERFACE` for ICorDebug scenarios outside of .NET Native.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7551-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c7551-117">Requirements</span></span>  

 <span data-ttu-id="c7551-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7551-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7551-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7551-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7551-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7551-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7551-121">**.NET Framework Versionen:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7551-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7551-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c7551-122">See also</span></span>

- [<span data-ttu-id="c7551-123">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="c7551-123">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c7551-124">Debuggen</span><span class="sxs-lookup"><span data-stu-id="c7551-124">Debugging</span></span>](index.md)
