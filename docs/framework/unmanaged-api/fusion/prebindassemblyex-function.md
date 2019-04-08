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
ms.openlocfilehash: 8251d21fe535f85cc6abd0a7bc6c96ab320007f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59090237"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="3c41d-102">PreBindAssemblyEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="3c41d-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="3c41d-103">Ruft den Anzeigenamen für die nach der Richtlinie für eine Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="3c41d-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="3c41d-104">Diese Funktion unterstützt die .NET Framework-Infrastruktur und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3c41d-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c41d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c41d-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3c41d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3c41d-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="3c41d-107">[in] Gibt den Anwendungskontext.</span><span class="sxs-lookup"><span data-stu-id="3c41d-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="3c41d-108">[in] Bezeichnet den Assemblynamen an.</span><span class="sxs-lookup"><span data-stu-id="3c41d-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="3c41d-109">[in] Identifiziert die übergeordnete Assembly.</span><span class="sxs-lookup"><span data-stu-id="3c41d-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="3c41d-110">Konvertiert die Zeichenfolgendarstellung einer Zahl in einem angegebenen Stil und einem kulturspezifischen Format in die entsprechende 32-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="3c41d-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="3c41d-111">[in] Identifiziert die Runtimeversion der Common Language.</span><span class="sxs-lookup"><span data-stu-id="3c41d-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="3c41d-112">[out] Enthält den Anzeigenamen nach der Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="3c41d-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="3c41d-113">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="3c41d-113">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="3c41d-114">ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="3c41d-114">must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c41d-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c41d-115">Remarks</span></span>  
 <span data-ttu-id="3c41d-116">Die `ppNamePostPolicy` Output-Parameter wird nur festgelegt, wenn die Funktion HRESULT FUSION_E_REF_DEF_MISMATCH zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3c41d-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="3c41d-117">Es ist, andernfalls null.</span><span class="sxs-lookup"><span data-stu-id="3c41d-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c41d-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3c41d-118">Requirements</span></span>  
 <span data-ttu-id="3c41d-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c41d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c41d-120">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="3c41d-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3c41d-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3c41d-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="3c41d-122">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="3c41d-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3c41d-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c41d-123">See also</span></span>

- [<span data-ttu-id="3c41d-124">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="3c41d-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
