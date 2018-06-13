---
title: PreBindAssemblyEx-Funktion
ms.date: 03/30/2017
api_name:
- PreBindAssemblyEx
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- PreBindAssemblyEx
helpviewer_keywords:
- PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d3e2535851d39be642de56a86b78c328ecaf446
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432000"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="143c4-102">PreBindAssemblyEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="143c4-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="143c4-103">Ruft den Anzeigenamen nach der Richtlinie für eine Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="143c4-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="143c4-104">Diese Funktion unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="143c4-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="143c4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="143c4-105">Syntax</span></span>  
  
```  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="143c4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="143c4-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="143c4-107">[in] Gibt den Anwendungskontext.</span><span class="sxs-lookup"><span data-stu-id="143c4-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="143c4-108">[in] Identifiziert den Assemblynamen.</span><span class="sxs-lookup"><span data-stu-id="143c4-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="143c4-109">[in] Identifiziert die übergeordnete Assembly.</span><span class="sxs-lookup"><span data-stu-id="143c4-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="143c4-110">Dieser Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="143c4-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="143c4-111">[in] Identifiziert die Laufzeitversion an.</span><span class="sxs-lookup"><span data-stu-id="143c4-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="143c4-112">[out] Enthält den Anzeigenamen nach der Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="143c4-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="143c4-113">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="143c4-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="143c4-114">`pvReserved` ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="143c4-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="143c4-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="143c4-115">Remarks</span></span>  
 <span data-ttu-id="143c4-116">Die `ppNamePostPolicy` Output-Parameter festgelegt ist, nur, wenn die Funktion HRESULT FUSION_E_REF_DEF_MISMATCH zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="143c4-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="143c4-117">Es ist, andernfalls null.</span><span class="sxs-lookup"><span data-stu-id="143c4-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="143c4-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="143c4-118">Requirements</span></span>  
 <span data-ttu-id="143c4-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="143c4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="143c4-120">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="143c4-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="143c4-121">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="143c4-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="143c4-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="143c4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="143c4-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="143c4-123">See Also</span></span>  
 [<span data-ttu-id="143c4-124">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="143c4-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
