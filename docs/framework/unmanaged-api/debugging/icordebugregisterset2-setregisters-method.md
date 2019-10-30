---
title: ICorDebugRegisterSet2::SetRegisters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet2.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet2::SetRegisters
helpviewer_keywords:
- ICorDebugRegisterSet2::SetRegisters method [.NET Framework debugging]
- SetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: fe0ac7e7-c9e1-4ec1-9f4e-1c56d63d73ac
topic_type:
- apiref
ms.openlocfilehash: 66c10e5ecdd1610ee170b412c2778b8117d6c407
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131304"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="ade80-102">ICorDebugRegisterSet2::SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="ade80-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="ade80-103">`SetRegisters` ist in .NET Framework Version 2,0 nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="ade80-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="ade80-104">Diese Methode nicht aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="ade80-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ade80-105">Verwenden Sie die Vorgänge auf höherer Ebene, z. b. [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) oder [ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="ade80-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ade80-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ade80-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ade80-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ade80-107">Requirements</span></span>  
 <span data-ttu-id="ade80-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ade80-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ade80-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ade80-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ade80-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ade80-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ade80-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ade80-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ade80-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ade80-112">See also</span></span>

- [<span data-ttu-id="ade80-113">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ade80-113">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="ade80-114">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ade80-114">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
