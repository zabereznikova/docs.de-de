---
title: ICorDebugRegisterSet::SetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetThreadContext
helpviewer_keywords:
- ICorDebugRegisterSet::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugRegisterSet interface [.NET Framework debugging]
ms.assetid: 73afa930-32cb-4c40-81f8-83e8e6fbe213
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff1365ddb46ca28cbcaa4f1383b293681e6ec214
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956769"
---
# <a name="icordebugregistersetsetthreadcontext-method"></a><span data-ttu-id="aec18-102">ICorDebugRegisterSet::SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="aec18-102">ICorDebugRegisterSet::SetThreadContext Method</span></span>
<span data-ttu-id="aec18-103">`SetThreadContext`ist nicht in der .NET Framework Version 2,0 implementiert.</span><span class="sxs-lookup"><span data-stu-id="aec18-103">`SetThreadContext` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="aec18-104">Diese Methode nicht aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="aec18-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="aec18-105">Verwenden Sie den übergeordneten Vorgang [ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) , um den Kontext eines Threads festzulegen.</span><span class="sxs-lookup"><span data-stu-id="aec18-105">Use the higher-level operation [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) to set the context of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aec18-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="aec18-106">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext (  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize),  
         size_is(contextSize)] BYTE context[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="aec18-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aec18-107">Requirements</span></span>  
 <span data-ttu-id="aec18-108">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aec18-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aec18-109">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="aec18-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aec18-110">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aec18-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aec18-111">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="aec18-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec18-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aec18-112">See also</span></span>

- [<span data-ttu-id="aec18-113">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aec18-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="aec18-114">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aec18-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
