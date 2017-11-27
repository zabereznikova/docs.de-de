---
title: ICorDebugHandleValue Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHandleValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHandleValue
helpviewer_keywords: ICorDebugHandleValue interface [.NET Framework debugging]
ms.assetid: 66fcd2b8-ac66-414b-83a8-75a925e17772
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b56c23caaaed2bc63c724769db1198fd088f7f1a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebughandlevalue-interface1"></a><span data-ttu-id="0eaaf-102">ICorDebugHandleValue Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="0eaaf-102">ICorDebugHandleValue Interface1</span></span>
<span data-ttu-id="0eaaf-103">Eine Unterklasse von ICorDebugReferenceValue, die einen Verweiswert darstellt, zu dem der Debugger einen Handle zur Garbagecollection erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-103">A subclass of ICorDebugReferenceValue that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="0eaaf-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="0eaaf-104">Methods</span></span>  
  
|<span data-ttu-id="0eaaf-105">Methode</span><span class="sxs-lookup"><span data-stu-id="0eaaf-105">Method</span></span>|<span data-ttu-id="0eaaf-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0eaaf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="0eaaf-107">Dispose-Methode</span><span class="sxs-lookup"><span data-stu-id="0eaaf-107">Dispose Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-dispose-method.md)|<span data-ttu-id="0eaaf-108">Gibt das Handle verweist diese frei `ICorDebugHandleValue` Objekt nicht explizit freigegeben den Schnittstellenzeiger auf.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-108">Releases the handle referenced by this `ICorDebugHandleValue` object without explicitly releasing the interface pointer.</span></span>|  
|[<span data-ttu-id="0eaaf-109">GetHandleType-Methode</span><span class="sxs-lookup"><span data-stu-id="0eaaf-109">GetHandleType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebughandlevalue-gethandletype-method.md)|<span data-ttu-id="0eaaf-110">Ruft einen CorDebugHandleType-Wert, der die Art der verwiesen, die von diesem Handle beschreibt `ICorDebugHandleValue`.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-110">Gets a CorDebugHandleType value that describes the kind of handle referenced by this `ICorDebugHandleValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0eaaf-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0eaaf-111">Remarks</span></span>  
 <span data-ttu-id="0eaaf-112">Ein `ICorDebugReferenceValue` Objekt wird durch eine Unterbrechung der Ausführung des gedebuggten Codes für ungültig erklärt.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-112">An `ICorDebugReferenceValue` object is invalidated by a break in the execution of debugged code.</span></span> <span data-ttu-id="0eaaf-113">Ein `ICorDebugHandleValue` verwaltet seinen Verweis durch Zeilenumbrüche und Fortsetzungen sein, bis sie explizit freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-113">An `ICorDebugHandleValue` maintains its reference through breaks and continuations, until it is explicitly released.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0eaaf-114">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0eaaf-114">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0eaaf-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0eaaf-115">Requirements</span></span>  
 <span data-ttu-id="0eaaf-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0eaaf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0eaaf-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0eaaf-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0eaaf-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0eaaf-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0eaaf-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0eaaf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0eaaf-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0eaaf-120">See Also</span></span>  
 [<span data-ttu-id="0eaaf-121">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="0eaaf-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
