---
title: ICorDebugAppDomainEnum Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e5d3d11e3897ff56ffcd475eb363405651578c1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomainenum-interface1"></a><span data-ttu-id="254ab-102">ICorDebugAppDomainEnum Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="254ab-102">ICorDebugAppDomainEnum Interface1</span></span>
<span data-ttu-id="254ab-103">Stellt die `Next` Methode, die eine angegebene Anzahl von zurückgibt `ICorDebugAppDomainEnum` Werte, die mit der nächsten Position in der Enumeration ab.</span><span class="sxs-lookup"><span data-stu-id="254ab-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="254ab-104">Diese Schnittstelle ist eine Unterklasse von "ICorDebugEnum".</span><span class="sxs-lookup"><span data-stu-id="254ab-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="254ab-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="254ab-105">Methods</span></span>  
  
|<span data-ttu-id="254ab-106">Methode</span><span class="sxs-lookup"><span data-stu-id="254ab-106">Method</span></span>|<span data-ttu-id="254ab-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="254ab-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="254ab-108">Next-Methode</span><span class="sxs-lookup"><span data-stu-id="254ab-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="254ab-109">Ruft die angegebene Anzahl von Anwendungsdomänen aus der Auflistung, beginnend mit der aktuellen Cursorposition ab.</span><span class="sxs-lookup"><span data-stu-id="254ab-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="254ab-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="254ab-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="254ab-111">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="254ab-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="254ab-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="254ab-112">Requirements</span></span>  
 <span data-ttu-id="254ab-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="254ab-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="254ab-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="254ab-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="254ab-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="254ab-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="254ab-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="254ab-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="254ab-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="254ab-117">See Also</span></span>  
 [<span data-ttu-id="254ab-118">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="254ab-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="254ab-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="254ab-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
