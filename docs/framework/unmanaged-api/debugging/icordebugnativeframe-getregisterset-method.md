---
title: ICorDebugNativeFrame::GetRegisterSet-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetRegisterSet
helpviewer_keywords:
- ICorDebugNativeFrame::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 6f309b5f-5556-4f1e-b1dd-4fe97fc81d01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6029ac8c9ab988efa78bbfaf0843154ac656671
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765803"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="55f53-102">ICorDebugNativeFrame::GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="55f53-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="55f53-103">Ruft das Register, legen Sie für diesen Stapelrahmen ab.</span><span class="sxs-lookup"><span data-stu-id="55f53-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55f53-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="55f53-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55f53-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="55f53-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="55f53-106">[out] Ein Zeiger auf die Adresse einer [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) -Objekt, das Register darstellt, die für dieses Stapelrahmens festgelegt.</span><span class="sxs-lookup"><span data-stu-id="55f53-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55f53-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="55f53-107">Requirements</span></span>  
 <span data-ttu-id="55f53-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55f53-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55f53-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55f53-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55f53-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55f53-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55f53-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55f53-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55f53-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55f53-112">See also</span></span>
