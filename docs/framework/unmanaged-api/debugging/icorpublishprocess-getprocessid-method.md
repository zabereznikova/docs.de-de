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
ms.openlocfilehash: bb785c84436e2b0c6848c8af2540e8efada38e6f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="5b07c-102">ICorPublishProcess::GetProcessID-Methode</span><span class="sxs-lookup"><span data-stu-id="5b07c-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="5b07c-103">Ruft den Bezeichner des Betriebssystems für diesen Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="5b07c-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b07c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b07c-104">Syntax</span></span>  
  
```  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5b07c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b07c-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="5b07c-106">[out] Ein Zeiger auf den Bezeichner des Prozesses, der von diesem dargestellt [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="5b07c-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b07c-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5b07c-107">Requirements</span></span>  
 <span data-ttu-id="5b07c-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b07c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b07c-109">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="5b07c-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="5b07c-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b07c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b07c-111">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b07c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b07c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b07c-112">See Also</span></span>  
 [<span data-ttu-id="5b07c-113">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5b07c-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
