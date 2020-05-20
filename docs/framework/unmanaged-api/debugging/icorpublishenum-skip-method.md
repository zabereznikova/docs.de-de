---
title: ICorPublishEnum::Skip-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
ms.openlocfilehash: b68a9ec1e8fee4fdecd2114af28c75c4a236cb3a
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421144"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="9c33d-102">ICorPublishEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="9c33d-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="9c33d-103">Verschiebt den Cursor in der-Enumeration um die angegebene Anzahl von Elementen vorwärts.</span><span class="sxs-lookup"><span data-stu-id="9c33d-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c33d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c33d-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c33d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9c33d-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="9c33d-106">in Die Anzahl der Elemente, um die der Cursor vorwärts verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="9c33d-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c33d-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9c33d-107">Requirements</span></span>  
 <span data-ttu-id="9c33d-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c33d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c33d-109">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="9c33d-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="9c33d-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c33d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c33d-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c33d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c33d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c33d-112">See also</span></span>

- [<span data-ttu-id="9c33d-113">ICorPublishEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9c33d-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
