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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 733f776b5ef2a4e1a004070dc06e1dc9f7ed0a7f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481507"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="09171-102">ICorPublishEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="09171-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="09171-103">Erstellt eine Kopie dieses [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="09171-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09171-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="09171-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09171-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="09171-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="09171-106">[out] Ein Zeiger auf die Adresse einer `ICorPublishEnum` Objekt, das eine Kopie dieses `ICorPublishEnum` Objekt.</span><span class="sxs-lookup"><span data-stu-id="09171-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09171-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="09171-107">Requirements</span></span>  
 <span data-ttu-id="09171-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09171-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09171-109">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="09171-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="09171-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09171-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09171-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09171-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09171-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09171-112">See also</span></span>
- [<span data-ttu-id="09171-113">ICorPublishEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09171-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
