---
title: ICorDebugRegisterSet2::SetRegisters-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRegisterSet2.SetRegisters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugRegisterSet2::SetRegisters
helpviewer_keywords:
- ICorDebugRegisterSet2::SetRegisters method [.NET Framework debugging]
- SetRegisters method, ICorDebugRegisterSet2 interface [.NET Framework debugging]
ms.assetid: fe0ac7e7-c9e1-4ec1-9f4e-1c56d63d73ac
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ebf58c209834e4df8435d40616ef3a571a7c0a1b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugregisterset2setregisters-method"></a><span data-ttu-id="aba90-102">ICorDebugRegisterSet2::SetRegisters-Methode</span><span class="sxs-lookup"><span data-stu-id="aba90-102">ICorDebugRegisterSet2::SetRegisters Method</span></span>
<span data-ttu-id="aba90-103">`SetRegisters`in .NET Framework, Version 2.0 ist nicht implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="aba90-103">`SetRegisters` is not implemented in the .NET Framework version 2.0.</span></span> <span data-ttu-id="aba90-104">Rufen Sie diese Methode nicht.</span><span class="sxs-lookup"><span data-stu-id="aba90-104">Do not call this method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aba90-105">Verwenden Sie die Vorgänge auf höherer Ebene wie [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) oder [ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span><span class="sxs-lookup"><span data-stu-id="aba90-105">Use the higher-level operations such as [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) or [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aba90-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="aba90-106">Syntax</span></span>  
  
```  
HRESULT SetRegisters (  
    [in] ULONG32 maskCount,  
    [in, size_is(maskCount)] BYTE mask[],  
    [in] ULONG32 regCount,  
    [in, size_is(regCount)] CORDB_REGISTER regBuffer[]  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="aba90-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aba90-107">Requirements</span></span>  
 <span data-ttu-id="aba90-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aba90-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aba90-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aba90-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aba90-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aba90-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aba90-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aba90-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aba90-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aba90-112">See Also</span></span>  
 [<span data-ttu-id="aba90-113">ICorDebugRegisterSet2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aba90-113">ICorDebugRegisterSet2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset2-interface.md)  
 [<span data-ttu-id="aba90-114">ICorDebugRegisterSet-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aba90-114">ICorDebugRegisterSet Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)
