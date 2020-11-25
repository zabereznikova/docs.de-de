---
title: ICorPublishEnum::Clone-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
ms.openlocfilehash: 44ecba99999d04603477f411e68834548f6a7cda
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693553"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="5cce7-102">ICorPublishEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="5cce7-102">ICorPublishEnum::Clone Method</span></span>

<span data-ttu-id="5cce7-103">Erstellt eine Kopie dieses [ICorPublishEnum](icorpublishenum-interface.md) -Objekts.</span><span class="sxs-lookup"><span data-stu-id="5cce7-103">Creates a copy of this [ICorPublishEnum](icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cce7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5cce7-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cce7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5cce7-105">Parameters</span></span>  

 `ppEnum`  
 <span data-ttu-id="5cce7-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorPublishEnum` Objekts, das eine Kopie dieses Objekts ist `ICorPublishEnum` .</span><span class="sxs-lookup"><span data-stu-id="5cce7-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cce7-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5cce7-107">Requirements</span></span>  

 <span data-ttu-id="5cce7-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cce7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cce7-109">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="5cce7-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5cce7-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cce7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cce7-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cce7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cce7-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5cce7-112">See also</span></span>

- [<span data-ttu-id="5cce7-113">ICorPublishEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5cce7-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
