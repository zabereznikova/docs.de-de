---
title: DestroyICeeFileGen-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- DestroyICeeFileGen
api_location:
- mscoree.dll
- mscorpehost.dll
- mscorpe.dll
api_type:
- COM
f1_keywords:
- DestroyICeeFileGen
helpviewer_keywords:
- DestroyICeeFileGen function [.NET Framework hosting]
ms.assetid: dc1e2235-e721-4cb2-a0b8-6b0c030d7bab
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d6c3e326aa71adc1bc9abe350cfc0528c88905cf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="e103f-102">DestroyICeeFileGen-Funktion</span><span class="sxs-lookup"><span data-stu-id="e103f-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="e103f-103">Zerstört ein [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="e103f-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="e103f-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="e103f-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e103f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e103f-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e103f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e103f-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="e103f-107">[in] Die `ICeeFileGen` Objekt zu zerstören.</span><span class="sxs-lookup"><span data-stu-id="e103f-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e103f-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e103f-108">Return Value</span></span>  
 <span data-ttu-id="e103f-109">Diese Methode gibt die standard-COM-Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="e103f-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e103f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e103f-110">Remarks</span></span>  
 <span data-ttu-id="e103f-111">`DestroyICeeFileGen`zerstört die `ICeeFileGen` Objekt erstellt, indem die [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="e103f-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e103f-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e103f-112">Requirements</span></span>  
 <span data-ttu-id="e103f-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e103f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e103f-114">**Header:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="e103f-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="e103f-115">**Bibliothek:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="e103f-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="e103f-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e103f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e103f-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e103f-117">See Also</span></span>  
 [<span data-ttu-id="e103f-118">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="e103f-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
