---
title: ICorDebugRegisterSet::GetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::GetThreadContext
helpviewer_keywords:
- GetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::GetThreadContext method [.NET Framework debugging]
ms.assetid: 0f63400b-dc1c-48d6-b51a-75c3f7f28e03
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 632d3912bae28da22e701078bb47d2d8dbfd3644
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423402"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="13295-102">ICorDebugRegisterSet::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="13295-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="13295-103">Ruft den Kontext des aktuellen Threads ab.</span><span class="sxs-lookup"><span data-stu-id="13295-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13295-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13295-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13295-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="13295-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="13295-106">[in] Die Größe in Bytes, der die `context` Array.</span><span class="sxs-lookup"><span data-stu-id="13295-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="13295-107">[in, out] Ein Array von Bytes, die von die Win32 `CONTEXT` Struktur für die aktuelle Plattform.</span><span class="sxs-lookup"><span data-stu-id="13295-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13295-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="13295-108">Remarks</span></span>  
 <span data-ttu-id="13295-109">Der Debugger sollte diese Funktion anstelle der Win32 Aufrufen `GetThreadContext` funktionsfähig, weil der Thread möglicherweise in einem "manipulierten" Zustand sein, in dessen Kontext vorübergehend geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="13295-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="13295-110">Die zurückgegebenen Daten sind eine Win32- `CONTEXT` Struktur für die aktuelle Plattform.</span><span class="sxs-lookup"><span data-stu-id="13295-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="13295-111">Für nichtblatt-Frames, sollten Clients überprüfen, welche Register gültig sind, mithilfe von [ICorDebugRegisterSet:: GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span><span class="sxs-lookup"><span data-stu-id="13295-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13295-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="13295-112">Requirements</span></span>  
 <span data-ttu-id="13295-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13295-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13295-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="13295-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="13295-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="13295-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="13295-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13295-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13295-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13295-117">See Also</span></span>  
 [<span data-ttu-id="13295-118">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13295-118">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)  
 [<span data-ttu-id="13295-119">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13295-119">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
