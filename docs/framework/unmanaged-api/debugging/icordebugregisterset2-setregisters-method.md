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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3013a0bc0cdcfa0d714328bfe86a87f44a11e829
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935106"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="f1fb0-102">ICorDebugRegisterSet2::SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="f1fb0-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="f1fb0-103">`SetRegisters`ist nicht in der .NET Framework Version 2,0 implementiert.</span><span class="sxs-lookup"><span data-stu-id="f1fb0-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="f1fb0-104">Diese Methode nicht aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f1fb0-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f1fb0-105">Verwenden Sie die Vorgänge auf höherer Ebene, z. b. [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) oder [ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="f1fb0-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1fb0-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1fb0-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="f1fb0-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f1fb0-107">Requirements</span></span>  
 <span data-ttu-id="f1fb0-108">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1fb0-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1fb0-109">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="f1fb0-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1fb0-110">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1fb0-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1fb0-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1fb0-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1fb0-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1fb0-112">See also</span></span>

- [<span data-ttu-id="f1fb0-113">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1fb0-113">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
- [<span data-ttu-id="f1fb0-114">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1fb0-114">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
