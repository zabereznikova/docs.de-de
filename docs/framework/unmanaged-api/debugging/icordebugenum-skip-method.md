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
ms.openlocfilehash: 2c5cd7435ec34e852b80031cfe0310ee517b7bc5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73103472"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="a896f-102">ICorDebugEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="a896f-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="a896f-103">Verschiebt den Cursor in der-Enumeration um die angegebene Anzahl von Elementen vorwärts.</span><span class="sxs-lookup"><span data-stu-id="a896f-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a896f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a896f-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a896f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a896f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a896f-106">in Die Anzahl der Elemente, um die der Cursor vorwärts verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="a896f-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a896f-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a896f-107">Requirements</span></span>  
 <span data-ttu-id="a896f-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a896f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a896f-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a896f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a896f-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a896f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a896f-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a896f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a896f-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a896f-112">See also</span></span>

- [<span data-ttu-id="a896f-113">ICorDebugEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a896f-113">ICorDebugEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
