---
title: PreBindAssemblyEx-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PreBindAssemblyEx
api_location: fusion.dll
api_type: DLLExport
f1_keywords: PreBindAssemblyEx
helpviewer_keywords: PreBindAssemblyEx function [.NET Framework fusion]
ms.assetid: bd285233-a4a2-4b52-bbca-0025a60e4864
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c9bd5cb6be2ccfd25d61a8a2f4347b384e1b2567
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="78af8-102">PreBindAssemblyEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="78af8-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="78af8-103">Ruft den Anzeigenamen nach der Richtlinie für eine Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="78af8-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="78af8-104">Diese Funktion unterstützt die .NET Framework-Infrastruktur und sollte nicht direkt aus Ihrem Code verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="78af8-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78af8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="78af8-105">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="78af8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="78af8-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="78af8-107">[in] Gibt den Anwendungskontext.</span><span class="sxs-lookup"><span data-stu-id="78af8-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="78af8-108">[in] Identifiziert den Assemblynamen.</span><span class="sxs-lookup"><span data-stu-id="78af8-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="78af8-109">[in] Identifiziert die übergeordnete Assembly.</span><span class="sxs-lookup"><span data-stu-id="78af8-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="78af8-110">Dieser Parameter wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="78af8-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="78af8-111">[in] Identifiziert die Laufzeitversion an.</span><span class="sxs-lookup"><span data-stu-id="78af8-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="78af8-112">[out] Enthält den Anzeigenamen nach der Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="78af8-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="78af8-113">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="78af8-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="78af8-114">`pvReserved`ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="78af8-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78af8-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="78af8-115">Remarks</span></span>  
 <span data-ttu-id="78af8-116">Die `ppNamePostPolicy` Output-Parameter festgelegt ist, nur, wenn die Funktion HRESULT FUSION_E_REF_DEF_MISMATCH zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="78af8-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="78af8-117">Es ist, andernfalls null.</span><span class="sxs-lookup"><span data-stu-id="78af8-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78af8-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="78af8-118">Requirements</span></span>  
 <span data-ttu-id="78af8-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78af8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78af8-120">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="78af8-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="78af8-121">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="78af8-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="78af8-122">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78af8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78af8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="78af8-123">See Also</span></span>  
 [<span data-ttu-id="78af8-124">Globale statische Fusionsfunktionen</span><span class="sxs-lookup"><span data-stu-id="78af8-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
