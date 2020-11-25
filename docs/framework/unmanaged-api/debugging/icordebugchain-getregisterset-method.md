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
ms.openlocfilehash: a3f02af1a0de9fcd7b3db1e49ef0d78af3395d2f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719657"
---
# <a name="icordebugchaingetregisterset-method"></a><span data-ttu-id="5eefa-102">ICorDebugChain::GetRegisterSet-Methode</span><span class="sxs-lookup"><span data-stu-id="5eefa-102">ICorDebugChain::GetRegisterSet Method</span></span>

<span data-ttu-id="5eefa-103">Ruft den Register Satz für den aktiven Teil dieser Kette ab.</span><span class="sxs-lookup"><span data-stu-id="5eefa-103">Gets the register set for the active part of this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5eefa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5eefa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5eefa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5eefa-105">Parameters</span></span>  

 `ppRegisters`  
 <span data-ttu-id="5eefa-106">vorgenommen Ein Zeiger auf die Adresse eines [ICorDebugRegisterSet](icordebugregisterset-interface.md) -Objekts, das den Register Satz für den aktiven Teil dieser Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="5eefa-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) object that represents the register set for the active part of this chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5eefa-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5eefa-107">Requirements</span></span>  

 <span data-ttu-id="5eefa-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5eefa-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5eefa-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5eefa-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5eefa-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5eefa-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5eefa-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5eefa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
