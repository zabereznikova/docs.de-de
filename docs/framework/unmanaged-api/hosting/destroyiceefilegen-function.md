---
title: DestroyICeeFileGen-Funktion
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 37ff40e1c009b8e1e0509a4a3333d5a2a70bbfd2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59159886"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="e7ee6-102">DestroyICeeFileGen-Funktion</span><span class="sxs-lookup"><span data-stu-id="e7ee6-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="e7ee6-103">Zerstört ein [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="e7ee6-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="e7ee6-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="e7ee6-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7ee6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7ee6-105">Syntax</span></span>  
  
```  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7ee6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e7ee6-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="e7ee6-107">[in] Die `ICeeFileGen` Objekt zu zerstören.</span><span class="sxs-lookup"><span data-stu-id="e7ee6-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e7ee6-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e7ee6-108">Return Value</span></span>  
 <span data-ttu-id="e7ee6-109">Diese Methode gibt die standard-COM-Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="e7ee6-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7ee6-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e7ee6-110">Remarks</span></span>  
 `DestroyICeeFileGen` <span data-ttu-id="e7ee6-111">zerstört die `ICeeFileGen` Objekt erstellt wurde, indem die [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="e7ee6-111">destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7ee6-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7ee6-112">Requirements</span></span>  
 <span data-ttu-id="e7ee6-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7ee6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7ee6-114">**Header:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="e7ee6-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="e7ee6-115">**Bibliothek:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="e7ee6-115">**Library:** MSCorPE.dll</span></span>  
  
 **<span data-ttu-id="e7ee6-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e7ee6-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e7ee6-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7ee6-117">See also</span></span>

- [<span data-ttu-id="e7ee6-118">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="e7ee6-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
