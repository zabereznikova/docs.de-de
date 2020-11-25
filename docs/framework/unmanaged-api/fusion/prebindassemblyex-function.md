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
ms.openlocfilehash: a729249f7b0681941a0b1a478dbe2c0d9d6cd01c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723960"
---
# <a name="prebindassemblyex-function"></a><span data-ttu-id="3d446-102">PreBindAssemblyEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="3d446-102">PreBindAssemblyEx Function</span></span>

<span data-ttu-id="3d446-103">Ruft den anzeigen Amen für eine Assembly nach der Richtlinie ab.</span><span class="sxs-lookup"><span data-stu-id="3d446-103">Gets the post-policy display name for an assembly.</span></span>  
  
 <span data-ttu-id="3d446-104">Diese Funktion unterstützt die .NET Framework-Infrastruktur und ist nicht für die direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="3d446-104">This function supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d446-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="3d446-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="3d446-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="3d446-106">Parameters</span></span>  

 `pAppCtx`  
 <span data-ttu-id="3d446-107">in Identifiziert den Anwendungskontext.</span><span class="sxs-lookup"><span data-stu-id="3d446-107">[in] Identifies the application context.</span></span>  
  
 `pName`  
 <span data-ttu-id="3d446-108">in Identifiziert den Assemblynamen.</span><span class="sxs-lookup"><span data-stu-id="3d446-108">[in] Identifies the assembly name.</span></span>  
  
 `pAsmParent`  
 <span data-ttu-id="3d446-109">in Identifiziert die übergeordnete Assembly.</span><span class="sxs-lookup"><span data-stu-id="3d446-109">[in] Identifies the parent assembly.</span></span> <span data-ttu-id="3d446-110">Konvertiert die Zeichenfolgendarstellung einer Zahl in einem angegebenen Stil und einem kulturspezifischen Format in die entsprechende 32-Bit-Ganzzahl mit Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="3d446-110">This parameter is ignored.</span></span>  
  
 `pwzRuntimeVersion`  
 <span data-ttu-id="3d446-111">in Identifiziert die Laufzeitversion.</span><span class="sxs-lookup"><span data-stu-id="3d446-111">[in] Identifies the runtime version.</span></span>  
  
 `ppNamePostPolicy`  
 <span data-ttu-id="3d446-112">vorgenommen Enthält den anzeigen Amen nach der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="3d446-112">[out] Contains the post-policy display name.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="3d446-113">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="3d446-113">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="3d446-114">`pvReserved` muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="3d446-114">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d446-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3d446-115">Remarks</span></span>  

 <span data-ttu-id="3d446-116">Der `ppNamePostPolicy` Output-Parameter wird nur festgelegt, wenn die Funktion HRESULT FUSION_E_REF_DEF_MISMATCH zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3d446-116">The `ppNamePostPolicy` output parameter is set only if the function returns HRESULT FUSION_E_REF_DEF_MISMATCH.</span></span> <span data-ttu-id="3d446-117">Andernfalls ist der Wert null.</span><span class="sxs-lookup"><span data-stu-id="3d446-117">Otherwise, it is null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d446-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3d446-118">Requirements</span></span>  

 <span data-ttu-id="3d446-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d446-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d446-120">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="3d446-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3d446-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3d446-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3d446-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d446-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d446-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3d446-123">See also</span></span>

- [<span data-ttu-id="3d446-124">Fusion – Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="3d446-124">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
