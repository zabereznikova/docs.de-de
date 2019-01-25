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
ms.openlocfilehash: ea34c4087014091b92d6227177a2f08209cc2e10
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54570878"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="73890-102">PreBindAssemblyEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="73890-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="73890-103">Ruft den Anzeigenamen für die nach der Richtlinie für eine Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="73890-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="73890-104">Diese Funktion unterstützt die .NET Framework-Infrastruktur und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="73890-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73890-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="73890-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="73890-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="73890-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="73890-107">[in] Gibt den Anwendungskontext.</span><span class="sxs-lookup"><span data-stu-id="73890-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="73890-108">[in] Bezeichnet den Assemblynamen an.</span><span class="sxs-lookup"><span data-stu-id="73890-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="73890-109">[in] Identifiziert die übergeordnete Assembly.</span><span class="sxs-lookup"><span data-stu-id="73890-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="73890-110">Dieser Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="73890-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="73890-111">[in] Identifiziert die Runtimeversion der Common Language.</span><span class="sxs-lookup"><span data-stu-id="73890-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="73890-112">[out] Enthält den Anzeigenamen nach der Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="73890-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="73890-113">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="73890-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="73890-114">`pvReserved` ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="73890-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="73890-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="73890-115">Remarks</span></span>  
 <span data-ttu-id="73890-116">Die `ppNamePostPolicy` Output-Parameter wird nur festgelegt, wenn die Funktion HRESULT FUSION_E_REF_DEF_MISMATCH zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="73890-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="73890-117">Es ist, andernfalls null.</span><span class="sxs-lookup"><span data-stu-id="73890-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73890-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73890-118">Requirements</span></span>  
 <span data-ttu-id="73890-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73890-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73890-120">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="73890-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="73890-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="73890-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="73890-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73890-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73890-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73890-123">See also</span></span>
- [<span data-ttu-id="73890-124">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="73890-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
