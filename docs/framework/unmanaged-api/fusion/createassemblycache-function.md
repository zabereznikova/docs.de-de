---
title: CreateAssemblyCache-Funktion
ms.date: 03/30/2017
api_name:
- CreateAssemblyCache
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyCache
helpviewer_keywords:
- CreateAssemblyCache function [.NET Framework fusion]
ms.assetid: 348c7c8c-8578-46ae-97cf-480d6015c3c6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bf78ded62f11b336d9f5fe0f3a205275ae37189b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157403"
---
# <a name="createassemblycache-function"></a><span data-ttu-id="49862-102">CreateAssemblyCache-Funktion</span><span class="sxs-lookup"><span data-stu-id="49862-102">CreateAssemblyCache Function</span></span>
<span data-ttu-id="49862-103">Ruft einen Zeiger auf ein neues [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) Instanz, die im globalen Assemblycache darstellt.</span><span class="sxs-lookup"><span data-stu-id="49862-103">Gets a pointer to a new [IAssemblyCache](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md) instance that represents the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49862-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49862-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCache (  
    [out] IAssemblyCache  **ppAsmCache,  
    [in]  DWORD           dwReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="49862-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="49862-105">Parameters</span></span>  
 `ppAsmCache`  
 <span data-ttu-id="49862-106">[out] Das zurückgegebene `IAssemblyCache` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="49862-106">[out] The returned `IAssemblyCache` pointer.</span></span>  
  
 `dwReserved`  
 <span data-ttu-id="49862-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="49862-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="49862-108">`dwReserved` 0 (null) muss sein.</span><span class="sxs-lookup"><span data-stu-id="49862-108">`dwReserved` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49862-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49862-109">Requirements</span></span>  
 <span data-ttu-id="49862-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49862-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49862-111">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="49862-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="49862-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="49862-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49862-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49862-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49862-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49862-114">See also</span></span>

- [<span data-ttu-id="49862-115">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49862-115">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="49862-116">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="49862-116">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [<span data-ttu-id="49862-117">Globaler Assemblycache</span><span class="sxs-lookup"><span data-stu-id="49862-117">Global Assembly Cache</span></span>](../../../../docs/framework/app-domains/gac.md)
