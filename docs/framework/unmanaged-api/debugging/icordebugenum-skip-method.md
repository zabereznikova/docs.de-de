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
ms.openlocfilehash: ae88336b9640b68b97522d252b3e8334c20ed9bc
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705864"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="8554a-102">ICorDebugEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="8554a-102">ICorDebugEnum::Skip Method</span></span>

<span data-ttu-id="8554a-103">Verschiebt den Cursor in der-Enumeration um die angegebene Anzahl von Elementen vorwärts.</span><span class="sxs-lookup"><span data-stu-id="8554a-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8554a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8554a-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8554a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8554a-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="8554a-106">in Die Anzahl der Elemente, um die der Cursor vorwärts verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="8554a-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8554a-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8554a-107">Requirements</span></span>  

 <span data-ttu-id="8554a-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8554a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8554a-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8554a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8554a-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8554a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8554a-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8554a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8554a-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8554a-112">See also</span></span>

- [<span data-ttu-id="8554a-113">ICorDebugEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8554a-113">ICorDebugEnum Interface</span></span>](icordebugenum-interface1.md)
