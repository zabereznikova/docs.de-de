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
ms.openlocfilehash: 8137d5477b75b864e223852cf524ac8c5b6c0f2b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792094"
---
# <a name="icordebugregistersetgetthreadcontext-method"></a><span data-ttu-id="af195-102">ICorDebugRegisterSet::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="af195-102">ICorDebugRegisterSet::GetThreadContext Method</span></span>
<span data-ttu-id="af195-103">Ruft den Kontext des aktuellen Threads ab.</span><span class="sxs-lookup"><span data-stu-id="af195-103">Gets the context of the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af195-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af195-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize),  
        size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="af195-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="af195-105">Parameters</span></span>  
 `contextSize`  
 <span data-ttu-id="af195-106">in Die Größe des `context` Arrays in Bytes.</span><span class="sxs-lookup"><span data-stu-id="af195-106">[in] The size, in bytes, of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="af195-107">[in, out] Ein Bytearray, das die Win32-`CONTEXT`-Struktur für die aktuelle Plattform zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="af195-107">[in, out] An array of bytes that compose the Win32 `CONTEXT` structure for the current platform.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="af195-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af195-108">Remarks</span></span>  
 <span data-ttu-id="af195-109">Der Debugger sollte diese Funktion anstelle der Win32-`GetThreadContext`-Funktion aufgerufen werden, da sich der Thread möglicherweise in einem "geversteckten" Zustand befindet, in dem der Kontext vorübergehend geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="af195-109">The debugger should call this function instead of the Win32 `GetThreadContext` function, because the thread may be in a "hijacked" state where its context has been temporarily changed.</span></span> <span data-ttu-id="af195-110">Die zurückgegebenen Daten sind eine Win32-`CONTEXT` Struktur für die aktuelle Plattform.</span><span class="sxs-lookup"><span data-stu-id="af195-110">The data returned is a Win32 `CONTEXT` structure for the current platform.</span></span>  
  
 <span data-ttu-id="af195-111">Für nicht blattrahmen sollten Clients überprüfen, welche Register gültig sind, indem Sie [icorunbugregisterset:: GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="af195-111">For non-leaf frames, clients should check which registers are valid by using [ICorDebugRegisterSet::GetRegistersAvailable](icordebugregisterset-getregistersavailable-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af195-112">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af195-112">Requirements</span></span>  
 <span data-ttu-id="af195-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af195-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af195-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af195-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af195-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af195-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af195-116">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af195-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af195-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af195-117">See also</span></span>

- [<span data-ttu-id="af195-118">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af195-118">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
- [<span data-ttu-id="af195-119">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af195-119">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
