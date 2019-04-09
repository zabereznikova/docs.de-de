---
title: ICorDebugHandleValue-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebugHandleValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHandleValue
helpviewer_keywords:
- ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a9eb63e681b47f058901b0ff002015baffe6048
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117442"
---
# <a name="icordebughandlevalue-interface"></a><span data-ttu-id="1388c-102">ICorDebugHandleValue-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1388c-102">ICorDebugHandleValue Interface</span></span>

<span data-ttu-id="1388c-103">Eine Unterklasse von ICorDebugReferenceValue, die einen Verweiswert darstellt, den der Debugger einen Handle zur Garbagecollection erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="1388c-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1388c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1388c-104">Methods</span></span>  
  
|<span data-ttu-id="1388c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1388c-105">Method</span></span>|<span data-ttu-id="1388c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1388c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1388c-107">Dispose-Methode</span><span class="sxs-lookup"><span data-stu-id="1388c-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="1388c-108">Gibt das Handle, das auf die dieses frei `ICorDebugHandleValue` Objekt ohne den Schnittstellenzeiger explizit freizugeben.</span><span class="sxs-lookup"><span data-stu-id="1388c-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="1388c-109">GetHandleType-Methode</span><span class="sxs-lookup"><span data-stu-id="1388c-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="1388c-110">Ruft einen CorDebugHandleType-Wert, der den Typ des Handles, die auf die dieses beschreibt `ICorDebugHandleValue`.</span><span class="sxs-lookup"><span data-stu-id="1388c-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1388c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1388c-111">Remarks</span></span>  
 <span data-ttu-id="1388c-112">Ein `ICorDebugReferenceValue` Objekt durch eine Unterbrechung der Ausführung des debuggten Codes ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="1388c-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="1388c-113">Ein `ICorDebugHandleValue` seinen Verweis über Unterbrechungen und Fortsetzungen, verwaltet, bis er explizit freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1388c-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1388c-114">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1388c-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1388c-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1388c-115">Requirements</span></span>  
 <span data-ttu-id="1388c-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1388c-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1388c-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1388c-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1388c-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1388c-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="1388c-119">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="1388c-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1388c-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1388c-120">See also</span></span>

- [<span data-ttu-id="1388c-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1388c-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
