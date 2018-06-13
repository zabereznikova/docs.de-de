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
ms.openlocfilehash: bfdde1f29300fcdc0f4e267949fdc3f6fd9917ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401407"
---
# <a name="icordebugchaingetregisterset-method"></a><span data-ttu-id="05d07-102">ICorDebugChain::GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="05d07-102">ICorDebugChain::GetRegisterSet Method</span></span>
<span data-ttu-id="05d07-103">Ruft den Registersatz für den aktiven Teil dieser Kette ab.</span><span class="sxs-lookup"><span data-stu-id="05d07-103">Gets the register set for the active part of this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05d07-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05d07-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="05d07-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="05d07-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="05d07-106">[out] Ein Zeiger auf die Adresse des ein [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) Objekt, das Register darstellt, für den aktiven Teil dieser Kette festgelegt.</span><span class="sxs-lookup"><span data-stu-id="05d07-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) object that represents the register set for the active part of this chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05d07-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="05d07-107">Requirements</span></span>  
 <span data-ttu-id="05d07-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05d07-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05d07-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05d07-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05d07-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05d07-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05d07-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05d07-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
