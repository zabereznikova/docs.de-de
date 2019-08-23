---
title: ICorDebugRegisterSet::SetRegisters-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRegisterSet.SetRegisters
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugRegisterSet::SetRegisters
helpviewer_keywords:
- SetRegisters method, ICorDebugRegisterSet interface [.NET Framework debugging]
- ICorDebugRegisterSet::SetRegisters method [.NET Framework debugging]
ms.assetid: ac6244b9-54ba-475f-b72a-abed6afc46ec
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 200ea1b9c046b8743699a549c07c0baaf285be39
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965036"
---
# <a name="icordebugregistersetsetregisters-method"></a><span data-ttu-id="e4994-102">ICorDebugRegisterSet::SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="e4994-102">ICorDebugRegisterSet::SetRegisters Method</span></span>
<span data-ttu-id="e4994-103">`SetRegisters`ist nicht in der .NET Framework Version 2,0 implementiert.</span><span class="sxs-lookup"><span data-stu-id="e4994-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="e4994-104">Diese Methode nicht aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e4994-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4994-105">Verwenden Sie die Vorgänge auf höherer Ebene, z. b. [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) oder [ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="e4994-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4994-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4994-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG64   mask,  
    [in] ULONG32   regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e4994-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4994-107">Requirements</span></span>  
 <span data-ttu-id="e4994-108">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4994-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4994-109">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="e4994-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4994-110">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4994-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4994-111">**.NET Framework Versionen:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="e4994-111">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4994-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4994-112">See also</span></span>

- [<span data-ttu-id="e4994-113">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4994-113">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
- [<span data-ttu-id="e4994-114">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4994-114">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)
