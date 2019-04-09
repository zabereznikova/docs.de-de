---
title: ICorPublishAppDomain::GetID-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishAppDomain.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishAppDomain::GetID
helpviewer_keywords:
- GetID method, ICorPublishAppDomain interface [.NET Framework debugging]
- ICorPublishAppDomain::GetID method [.NET Framework debugging]
ms.assetid: 229437e3-1465-4bd8-8846-9804b2488133
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44a2038af5d6ef46ad7cc661603e99b2f3dd67a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215923"
---
# <a name="icorpublishappdomaingetid-method"></a><span data-ttu-id="2800b-102">ICorPublishAppDomain::GetID-Methode</span><span class="sxs-lookup"><span data-stu-id="2800b-102">ICorPublishAppDomain::GetID Method</span></span>
<span data-ttu-id="2800b-103">Ruft den eindeutigen Bezeichner für diese [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span><span class="sxs-lookup"><span data-stu-id="2800b-103">Gets the unique identifier for this [ICorPublishAppDomain](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2800b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2800b-104">Syntax</span></span>  
  
```  
HRESULT GetID (  
    [out] ULONG32   *puId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2800b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2800b-105">Parameters</span></span>  
 `puId`  
 <span data-ttu-id="2800b-106">[out] Ein Zeiger auf den Bezeichner der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="2800b-106">[out] A pointer to the identifier of the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2800b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2800b-107">Remarks</span></span>  
 <span data-ttu-id="2800b-108">Der Bezeichner ist nur im Bereich des enthaltenden Prozesses eindeutig.</span><span class="sxs-lookup"><span data-stu-id="2800b-108">The identifier is unique only in the scope of the containing process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2800b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2800b-109">Requirements</span></span>  
 <span data-ttu-id="2800b-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2800b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2800b-111">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="2800b-111">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="2800b-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2800b-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="2800b-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="2800b-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2800b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2800b-114">See also</span></span>

- [<span data-ttu-id="2800b-115">ICorPublishAppDomain-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2800b-115">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)
