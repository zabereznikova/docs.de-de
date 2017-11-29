---
title: ICorDebugRegisterSet::GetThreadContext-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet.GetThreadContext
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 910bb09aa011efc9f81cf5c62a58d39236d723de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="98395-102">ICorDebugRegisterSet::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="98395-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="98395-103">Ruft den Kontext des aktuellen Threads ab.</span><span class="sxs-lookup"><span data-stu-id="98395-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98395-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="98395-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98395-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="98395-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="98395-106">[in] Die Größe in Bytes, der die `context` Array.</span><span class="sxs-lookup"><span data-stu-id="98395-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="98395-107">[in, out] Ein Array von Bytes, die von die Win32 `CONTEXT` Struktur für die aktuelle Plattform.</span><span class="sxs-lookup"><span data-stu-id="98395-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98395-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="98395-108">Remarks</span></span>  
 <span data-ttu-id="98395-109">Der Debugger sollte diese Funktion anstelle der Win32 Aufrufen `GetThreadContext` funktionsfähig, weil der Thread möglicherweise in einem "manipulierten" Zustand sein, in dessen Kontext vorübergehend geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="98395-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="98395-110">Die zurückgegebenen Daten sind eine Win32- `CONTEXT` Struktur für die aktuelle Plattform.</span><span class="sxs-lookup"><span data-stu-id="98395-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="98395-111">Für nichtblatt-Frames, sollten Clients überprüfen, welche Register gültig sind, mithilfe von [ICorDebugRegisterSet:: GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="98395-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98395-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="98395-112">Requirements</span></span>  
 <span data-ttu-id="98395-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98395-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98395-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98395-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98395-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98395-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98395-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98395-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98395-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98395-117">See Also</span></span>  
 [<span data-ttu-id="98395-118">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98395-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="98395-119">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="98395-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
