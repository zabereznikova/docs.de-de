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
ms.openlocfilehash: afd16f1f31be9148422dd6d0be748036a8e5d99a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790658"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="f8e35-102">ICorPublishEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="f8e35-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="f8e35-103">Erstellt eine Kopie dieses [ICorPublishEnum](icorpublishenum-interface.md) -Objekts.</span><span class="sxs-lookup"><span data-stu-id="f8e35-103">Creates a copy of this [ICorPublishEnum](icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8e35-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8e35-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8e35-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f8e35-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f8e35-106">vorgenommen Ein Zeiger auf die Adresse eines `ICorPublishEnum` Objekts, das eine Kopie dieses `ICorPublishEnum` Objekts ist.</span><span class="sxs-lookup"><span data-stu-id="f8e35-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8e35-107">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8e35-107">Requirements</span></span>  
 <span data-ttu-id="f8e35-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8e35-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8e35-109">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="f8e35-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f8e35-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8e35-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8e35-111">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8e35-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8e35-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8e35-112">See also</span></span>

- [<span data-ttu-id="f8e35-113">ICorPublishEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8e35-113">ICorPublishEnum Interface</span></span>](icorpublishenum-interface.md)
