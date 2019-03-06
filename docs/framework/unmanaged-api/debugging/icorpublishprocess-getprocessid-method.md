---
title: ICorPublishProcess::GetProcessID-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61c67e074fc32098fa0d8326ea2f0ecfb1efa952
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471768"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="7573b-102">ICorPublishProcess::GetProcessID-Methode</span><span class="sxs-lookup"><span data-stu-id="7573b-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="7573b-103">Ruft den Bezeichner für diesen Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="7573b-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7573b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7573b-104">Syntax</span></span>  
  
```  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7573b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7573b-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="7573b-106">[out] Ein Zeiger auf den Bezeichner des Prozesses, der von diesem dargestellt [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="7573b-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7573b-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7573b-107">Requirements</span></span>  
 <span data-ttu-id="7573b-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7573b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7573b-109">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="7573b-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="7573b-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7573b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7573b-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7573b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7573b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7573b-112">See also</span></span>
- [<span data-ttu-id="7573b-113">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7573b-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
