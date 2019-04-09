---
title: ICorPublishProcess::IsManaged-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.IsManaged
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::IsManaged
helpviewer_keywords:
- IsManaged method, ICorPublishProcess interface [.NET Framework debugging]
- ICorPublishProcess::IsManaged method [.NET Framework debugging]
ms.assetid: 06b1f7cc-acdf-47a6-9d53-d9dec2424152
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29c5f96bab374d6e2d43424370bff2a4a2ab6df3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218289"
---
# <a name="icorpublishprocessismanaged-method"></a><span data-ttu-id="21acf-102">ICorPublishProcess::IsManaged-Methode</span><span class="sxs-lookup"><span data-stu-id="21acf-102">ICorPublishProcess::IsManaged Method</span></span>
<span data-ttu-id="21acf-103">Ruft einen Wert, der angibt, ob von dieser vom Prozess verwiesen [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) ist bekannt, dass verwalteter Code haben.</span><span class="sxs-lookup"><span data-stu-id="21acf-103">Gets a value that indicates whether the process referenced by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) is known to have managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21acf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21acf-104">Syntax</span></span>  
  
```  
HRESULT IsManaged (  
    [out] BOOL   *pbManaged  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21acf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="21acf-105">Parameters</span></span>  
 `pbManaged`  
 <span data-ttu-id="21acf-106">[out] Ein Zeiger auf einen booleschen Wert, der angibt, ob der Prozess über verwalteten Code hat.</span><span class="sxs-lookup"><span data-stu-id="21acf-106">[out] A pointer to a Boolean value that indicates whether the process has managed code.</span></span> <span data-ttu-id="21acf-107">Der Wert ist `true` Wenn der Prozess über verwalteten Code; aufweist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="21acf-107">The value is `true` if the process has managed code; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21acf-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="21acf-108">Remarks</span></span>  
 <span data-ttu-id="21acf-109">Da die aktuelle Version der `ICorPublishProcess` ermöglicht den Zugriff nur für Prozesse, die von Code verwaltetem, `IsManaged` gibt immer `true`.</span><span class="sxs-lookup"><span data-stu-id="21acf-109">Since the current version of `ICorPublishProcess` allows access only to processes that have managed code, `IsManaged` always returns `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21acf-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="21acf-110">Requirements</span></span>  
 <span data-ttu-id="21acf-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21acf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21acf-112">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="21acf-112">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="21acf-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="21acf-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="21acf-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="21acf-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="21acf-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21acf-115">See also</span></span>

- [<span data-ttu-id="21acf-116">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21acf-116">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
