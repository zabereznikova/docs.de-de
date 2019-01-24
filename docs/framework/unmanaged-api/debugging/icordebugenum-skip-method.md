---
title: ICorDebugEnum::Skip-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a886d8ab8f2d59bb9c9b0b3ff00fd89f7c931ff8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54692820"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="6445f-102">ICorDebugEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="6445f-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="6445f-103">Verschiebt den Cursor vorwärts in der Enumeration, um die angegebene Anzahl von Elementen.</span><span class="sxs-lookup"><span data-stu-id="6445f-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6445f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6445f-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6445f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6445f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6445f-106">[in] Die Anzahl von Elementen, die den Cursor vorwärts bewegen.</span><span class="sxs-lookup"><span data-stu-id="6445f-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6445f-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6445f-107">Requirements</span></span>  
 <span data-ttu-id="6445f-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6445f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6445f-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6445f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6445f-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6445f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6445f-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6445f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6445f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6445f-112">See also</span></span>
- [<span data-ttu-id="6445f-113">ICorDebugEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="6445f-113">ICorDebugEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
