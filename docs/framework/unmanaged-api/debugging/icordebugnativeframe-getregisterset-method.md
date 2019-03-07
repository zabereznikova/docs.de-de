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
ms.openlocfilehash: 18db366bde4211afa0f65052affa0ab9639df122
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498925"
---
# <a name="icordebugnativeframegetregisterset-method"></a><span data-ttu-id="db1c8-102">ICorDebugNativeFrame::GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="db1c8-102">ICorDebugNativeFrame::GetRegisterSet Method</span></span>
<span data-ttu-id="db1c8-103">Ruft das Register, legen Sie für diesen Stapelrahmen ab.</span><span class="sxs-lookup"><span data-stu-id="db1c8-103">Gets the register set for this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db1c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db1c8-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db1c8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="db1c8-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="db1c8-106">[out] Ein Zeiger auf die Adresse einer [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) -Objekt, das Register darstellt, die für dieses Stapelrahmens festgelegt.</span><span class="sxs-lookup"><span data-stu-id="db1c8-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for this stack frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db1c8-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="db1c8-107">Requirements</span></span>  
 <span data-ttu-id="db1c8-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db1c8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db1c8-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db1c8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db1c8-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db1c8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db1c8-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db1c8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db1c8-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db1c8-112">See also</span></span>

