---
title: ICorDebugChain::GetRegisterSet-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetRegisterSet
helpviewer_keywords:
- ICorDebugChain::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: bc4288b6-3331-4ae3-990d-e1d6e62ecb67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f366a40e1e3cd196f480c5849c49419c7daeea9e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480987"
---
# <a name="icordebugchaingetregisterset-method"></a><span data-ttu-id="4e1de-102">ICorDebugChain::GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="4e1de-102">ICorDebugChain::GetRegisterSet Method</span></span>
<span data-ttu-id="4e1de-103">Ruft ab, das Register, die für den aktiven Teil des dieser Kette festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4e1de-103">Gets the register set for the active part of this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e1de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e1de-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e1de-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e1de-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="4e1de-106">[out] Ein Zeiger auf die Adresse einer [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) -Objekt, das Register darstellt, die für den aktiven Teil des dieser Kette festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4e1de-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for the active part of this chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e1de-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e1de-107">Requirements</span></span>  
 <span data-ttu-id="4e1de-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e1de-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e1de-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4e1de-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4e1de-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e1de-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e1de-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e1de-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
