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
ms.openlocfilehash: a23d3c4fd8eef2e361abf1602157cb4fbb820b48
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773857"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="bd3cf-102">PreBindAssemblyEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="bd3cf-102">PreBindAssemblyEx Function</span></span>
<span data-ttu-id="bd3cf-103">Ruft den Anzeigenamen für die nach der Richtlinie für eine Assembly ab.</span><span class="sxs-lookup"><span data-stu-id="bd3cf-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="bd3cf-104">Diese Funktion unterstützt die .NET Framework-Infrastruktur und nicht direkt aus Ihrem Code verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="bd3cf-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd3cf-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd3cf-105">Syntax</span></span>  
  
```cpp  
HRESULT PreBindAssemblyEx (  
    [in]  IApplicationContext *pAppCtx,  
    [in]  IAssemblyName       *pName,  
    [in]  IAssembly           *pAsmParent,  
    [in]  LPCWSTR             pwzRuntimeVersion,  
    [out] IAssemblyName       **ppNamePostPolicy,  
    [in]  LPVOID              pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd3cf-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd3cf-106">Parameters</span></span>  
 `pAppCtx`  
 <span data-ttu-id="bd3cf-107">[in] Gibt den Anwendungskontext.</span><span class="sxs-lookup"><span data-stu-id="bd3cf-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="bd3cf-108">[in] Bezeichnet den Assemblynamen an.</span><span class="sxs-lookup"><span data-stu-id="bd3cf-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="bd3cf-109">[in] Identifiziert die übergeordnete Assembly.</span><span class="sxs-lookup"><span data-stu-id="bd3cf-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="bd3cf-110">Konvertiert die Zeichenfolgendarstellung einer Zahl in einem angegebenen Stil und einem kulturspezifischen Format in die entsprechende 32-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="bd3cf-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="bd3cf-111">[in] Identifiziert die Runtimeversion der Common Language.</span><span class="sxs-lookup"><span data-stu-id="bd3cf-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="bd3cf-112">[out] Enthält den Anzeigenamen nach der Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="bd3cf-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="bd3cf-113">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="bd3cf-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="bd3cf-114">`pvReserved` ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="bd3cf-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd3cf-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd3cf-115">Remarks</span></span>  
 <span data-ttu-id="bd3cf-116">Die `ppNamePostPolicy` Output-Parameter wird nur festgelegt, wenn die Funktion HRESULT FUSION_E_REF_DEF_MISMATCH zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bd3cf-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="bd3cf-117">Es ist, andernfalls null.</span><span class="sxs-lookup"><span data-stu-id="bd3cf-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd3cf-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd3cf-118">Requirements</span></span>  
 <span data-ttu-id="bd3cf-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd3cf-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd3cf-120">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="bd3cf-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="bd3cf-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bd3cf-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd3cf-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd3cf-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd3cf-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd3cf-123">See also</span></span>

- [<span data-ttu-id="bd3cf-124">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="bd3cf-124">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
