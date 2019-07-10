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
ms.openlocfilehash: ab4560774edce49341c86dd9446e38701db7fa62
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769832"
---
# <a name="destroyiceefilegen-function"></a><span data-ttu-id="096db-102">DestroyICeeFileGen-Funktion</span><span class="sxs-lookup"><span data-stu-id="096db-102">DestroyICeeFileGen Function</span></span>
<span data-ttu-id="096db-103">Zerstört ein [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="096db-103">Destroys an [ICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/iceefilegen-class.md) object.</span></span>  
  
 <span data-ttu-id="096db-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="096db-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="096db-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="096db-105">Syntax</span></span>  
  
```cpp  
HRESULT DestroyICeeFileGen (  
    [in] ICeeFileGen  **ceeFileGen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="096db-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="096db-106">Parameters</span></span>  
 `ceeFileGen`  
 <span data-ttu-id="096db-107">[in] Die `ICeeFileGen` Objekt zu zerstören.</span><span class="sxs-lookup"><span data-stu-id="096db-107">[in] The `ICeeFileGen` object to destroy.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="096db-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="096db-108">Return Value</span></span>  
 <span data-ttu-id="096db-109">Diese Methode gibt die standard-COM-Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="096db-109">This method returns standard COM error codes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="096db-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="096db-110">Remarks</span></span>  
 <span data-ttu-id="096db-111">`DestroyICeeFileGen` zerstört die `ICeeFileGen` Objekt erstellt wurde, indem die [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="096db-111">`DestroyICeeFileGen` destroys the `ICeeFileGen` object created by the [CreateICeeFileGen](../../../../docs/framework/unmanaged-api/hosting/createiceefilegen-function.md) function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="096db-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="096db-112">Requirements</span></span>  
 <span data-ttu-id="096db-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="096db-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="096db-114">**Header:** ICeeFileGen.h</span><span class="sxs-lookup"><span data-stu-id="096db-114">**Header:** ICeeFileGen.h</span></span>  
  
 <span data-ttu-id="096db-115">**Bibliothek:** MSCorPE.dll</span><span class="sxs-lookup"><span data-stu-id="096db-115">**Library:** MSCorPE.dll</span></span>  
  
 <span data-ttu-id="096db-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="096db-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="096db-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="096db-117">See also</span></span>

- [<span data-ttu-id="096db-118">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="096db-118">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
