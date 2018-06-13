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
ms.openlocfilehash: c7d280cd20b8ff76efe977983e3e9f6da32990c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413958"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="e1a31-102">ICorDebugEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="e1a31-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="e1a31-103">Verschiebt den Cursor in der Enumeration, um die angegebene Anzahl von Elementen.</span><span class="sxs-lookup"><span data-stu-id="e1a31-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e1a31-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e1a31-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e1a31-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e1a31-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e1a31-106">[in] Die Anzahl von Elementen, die den Cursor vorwärts zu bewegen.</span><span class="sxs-lookup"><span data-stu-id="e1a31-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e1a31-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e1a31-107">Requirements</span></span>  
 <span data-ttu-id="e1a31-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1a31-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1a31-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e1a31-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e1a31-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e1a31-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e1a31-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e1a31-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1a31-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1a31-112">See Also</span></span>  
 [<span data-ttu-id="e1a31-113">ICorDebugEnum-Schnittstelle1</span><span class="sxs-lookup"><span data-stu-id="e1a31-113">ICorDebugEnum Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
