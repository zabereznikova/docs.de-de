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
ms.openlocfilehash: eb9e5bdf85c6d487fd82422522854076c03e2288
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140450"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="633a2-102">ICorPublishEnum::Skip-Methode</span><span class="sxs-lookup"><span data-stu-id="633a2-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="633a2-103">Verschiebt den Cursor in der-Enumeration um die angegebene Anzahl von Elementen vorwärts.</span><span class="sxs-lookup"><span data-stu-id="633a2-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="633a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="633a2-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="633a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="633a2-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="633a2-106">in Die Anzahl der Elemente, um die der Cursor vorwärts verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="633a2-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="633a2-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="633a2-107">Requirements</span></span>  
 <span data-ttu-id="633a2-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="633a2-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="633a2-109">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="633a2-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="633a2-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="633a2-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="633a2-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="633a2-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="633a2-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="633a2-112">See also</span></span>

- [<span data-ttu-id="633a2-113">ICorPublishEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="633a2-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
