---
title: LoadStringRCEx-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: LoadStringRCEx
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: LoadStringRCEx
helpviewer_keywords: LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9b046387b5ae365ece694509b302f7ac3a7e066a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="ac3af-102">LoadStringRCEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="ac3af-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="ac3af-103">Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.</span><span class="sxs-lookup"><span data-stu-id="ac3af-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="ac3af-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="ac3af-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac3af-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac3af-105">Syntax</span></span>  
  
```  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,   
    [in]  UINT    iResouceID,   
    [out] LPWSTR  szBuffer,   
    [in]  int     iMax,   
    [in]  int     bQuiet,   
    [out] int    *pcwchUsed  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac3af-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="ac3af-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="ac3af-107">[in] Eine Kultur-ID.</span><span class="sxs-lookup"><span data-stu-id="ac3af-107">[in] A culture identifier.</span></span> <span data-ttu-id="ac3af-108">Übergeben Sie – 1 für `lcid` die Standardkultur verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac3af-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="ac3af-109">[in] Ein HRESULT.</span><span class="sxs-lookup"><span data-stu-id="ac3af-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="ac3af-110">[out] Ein Puffer, der nach dem erfolgreichen Abschluss die Fehlermeldung enthält.</span><span class="sxs-lookup"><span data-stu-id="ac3af-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="ac3af-111">[in] Die Größe des Puffers für die Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="ac3af-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="ac3af-112">[in] Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="ac3af-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="ac3af-113">[out] Ein Zeiger auf die Länge der Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="ac3af-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac3af-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ac3af-114">Return Value</span></span>  
 <span data-ttu-id="ac3af-115">Diese Methode gibt COM-Standardfehlercodes in WinError.h definiert, zusätzlich zu den folgenden Werten zurück.</span><span class="sxs-lookup"><span data-stu-id="ac3af-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="ac3af-116">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="ac3af-116">Return code</span></span>|<span data-ttu-id="ac3af-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ac3af-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ac3af-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac3af-118">S_OK</span></span>|<span data-ttu-id="ac3af-119">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ac3af-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="ac3af-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="ac3af-120">E_INVALIDARG</span></span>|<span data-ttu-id="ac3af-121">`szBuffer`ist null, oder `iMax` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="ac3af-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac3af-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac3af-122">Remarks</span></span>  
 <span data-ttu-id="ac3af-123">Wenn die Methode nicht erfolgreich abgeschlossen wird `szBuffer` enthält eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ac3af-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac3af-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac3af-124">Requirements</span></span>  
 <span data-ttu-id="ac3af-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac3af-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac3af-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac3af-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac3af-127">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="ac3af-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac3af-128">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac3af-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac3af-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ac3af-129">See Also</span></span>  
 <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="ac3af-130">LoadStringRC-Funktion</span><span class="sxs-lookup"><span data-stu-id="ac3af-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
 [<span data-ttu-id="ac3af-131">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="ac3af-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
