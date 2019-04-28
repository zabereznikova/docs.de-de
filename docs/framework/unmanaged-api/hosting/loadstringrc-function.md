---
title: LoadStringRC-Funktion
ms.date: 03/30/2017
api_name:
- LoadStringRC
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRC
helpviewer_keywords:
- LoadStringRC function [.NET Framework hosting]
ms.assetid: 752e49b4-987c-4c28-a118-1a0c1ed510c5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f17ecfe683de0739e4e1e063d38836eecf949336
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765309"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="61c70-102">LoadStringRC-Funktion</span><span class="sxs-lookup"><span data-stu-id="61c70-102">LoadStringRC Function</span></span>
<span data-ttu-id="61c70-103">Übersetzt einen HRESULT-Wert in eine Fehlermeldung, wobei die Standardkultur des aktuellen Threads verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="61c70-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="61c70-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="61c70-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61c70-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="61c70-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61c70-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="61c70-106">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="61c70-107">[in] Ein HRESULT.</span><span class="sxs-lookup"><span data-stu-id="61c70-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="61c70-108">[out] Ein Puffer, der die Fehlermeldung nach dem erfolgreichen Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="61c70-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="61c70-109">[in] Die Größe des Puffers für die Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="61c70-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="61c70-110">[in] Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="61c70-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="61c70-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="61c70-111">Return Value</span></span>  
 <span data-ttu-id="61c70-112">Diese Methode gibt Component Object Model (COM) Standardfehlercodes in "Winerror.h", zusätzlich zu den folgenden Werten definiert.</span><span class="sxs-lookup"><span data-stu-id="61c70-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="61c70-113">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="61c70-113">Return code</span></span>|<span data-ttu-id="61c70-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61c70-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="61c70-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="61c70-115">S_OK</span></span>|<span data-ttu-id="61c70-116">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="61c70-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="61c70-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="61c70-117">E_INVALIDARG</span></span>|<span data-ttu-id="61c70-118">`szBuffer` ist null oder `iMax` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="61c70-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61c70-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="61c70-119">Remarks</span></span>  
 <span data-ttu-id="61c70-120">Wenn die Methode nicht erfolgreich abgeschlossen wird `szBuffer` enthält eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="61c70-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61c70-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="61c70-121">Requirements</span></span>  
 <span data-ttu-id="61c70-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61c70-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61c70-123">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="61c70-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61c70-124">**Bibliothek:** "Mscoree.dll" und "Mscorwks.dll".</span><span class="sxs-lookup"><span data-stu-id="61c70-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="61c70-125">Verwenden Sie "Mscoree.dll" anstelle von "Mscorwks.dll", um sicherzustellen, dass Sie die richtige Version von .NET Framework abzielen.</span><span class="sxs-lookup"><span data-stu-id="61c70-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="61c70-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61c70-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61c70-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61c70-127">See also</span></span>

- [<span data-ttu-id="61c70-128">LoadStringRCEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="61c70-128">LoadStringRCEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)
- [<span data-ttu-id="61c70-129">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="61c70-129">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
