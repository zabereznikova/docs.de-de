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
ms.openlocfilehash: ebbd8dc2b715541850ed3b3bc530c0dd28993e1d
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378128"
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="21048-102">ICorDebugRegisterSet2::SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="21048-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="21048-103">`SetRegisters`ist nicht in der .NET Framework Version 2,0 implementiert.</span><span class="sxs-lookup"><span data-stu-id="21048-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="21048-104">Rufen Sie diese Methode nicht auf.</span><span class="sxs-lookup"><span data-stu-id="21048-104">Do not call this method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="21048-105">Verwenden Sie die Vorgänge auf höherer Ebene, z. b. [ICorDebugILFrame:: SetIP](icordebugilframe-setip-method.md) oder [ICorDebugNativeFrame:: SetIP](icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="21048-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21048-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="21048-106">Syntax</span></span>  
  
```cpp  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="21048-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="21048-107">Requirements</span></span>  
 <span data-ttu-id="21048-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21048-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21048-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="21048-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="21048-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21048-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="21048-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21048-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21048-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21048-112">See also</span></span>

- [<span data-ttu-id="21048-113">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21048-113">ICorDebugRegisterSet2 Interface</span></span>](icordebugregisterset2-interface.md)
- [<span data-ttu-id="21048-114">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21048-114">ICorDebugRegisterSet Interface</span></span>](icordebugregisterset-interface.md)
