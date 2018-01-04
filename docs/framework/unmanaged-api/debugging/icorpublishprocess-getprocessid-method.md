---
title: ICorPublishProcess::GetProcessID-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorPublishProcess.GetProcessID
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a048255e075b01f4c3c7635038b22ab581032524
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="f1456-102">ICorPublishProcess::GetProcessID-Methode</span><span class="sxs-lookup"><span data-stu-id="f1456-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="f1456-103">Ruft den Bezeichner des Betriebssystems für diesen Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="f1456-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1456-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1456-104">Syntax</span></span>  
  
```  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1456-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1456-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="f1456-106">[out] Ein Zeiger auf den Bezeichner des Prozesses, der von diesem dargestellt [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="f1456-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1456-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f1456-107">Requirements</span></span>  
 <span data-ttu-id="f1456-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1456-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1456-109">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="f1456-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f1456-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1456-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1456-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1456-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1456-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1456-112">See Also</span></span>  
 [<span data-ttu-id="f1456-113">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f1456-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
