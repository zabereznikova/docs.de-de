---
title: LoadStringRCEx-Funktion
ms.date: 03/30/2017
api_name:
- LoadStringRCEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- LoadStringRCEx
helpviewer_keywords:
- LoadStringRCEx function [.NET Framework hosting]
ms.assetid: bc789636-ca14-4f07-8f77-9305874d7495
topic_type:
- apiref
ms.openlocfilehash: a300c2679ef11a84edb2ab89c8dea96e445c9ee3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177984"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="1d4a2-102">LoadStringRCEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="1d4a2-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="1d4a2-103">Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.</span><span class="sxs-lookup"><span data-stu-id="1d4a2-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="1d4a2-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="1d4a2-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d4a2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d4a2-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRCEx (  
    [in]  LCID    lcid,
    [in]  UINT    iResouceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet,
    [out] int    *pcwchUsed  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d4a2-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="1d4a2-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="1d4a2-107">[in] Ein Kulturbezeichner.</span><span class="sxs-lookup"><span data-stu-id="1d4a2-107">[in] A culture identifier.</span></span> <span data-ttu-id="1d4a2-108">Übergeben Sie `lcid` -1, um die Standardkultur zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="1d4a2-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="1d4a2-109">[in] Ein HRESULT.</span><span class="sxs-lookup"><span data-stu-id="1d4a2-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="1d4a2-110">[out] Ein Puffer, der die Fehlermeldung nach erfolgreichem Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="1d4a2-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="1d4a2-111">[in] Die Größe des Fehlermeldungspuffers.</span><span class="sxs-lookup"><span data-stu-id="1d4a2-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="1d4a2-112">[in] Ignoriert.</span><span class="sxs-lookup"><span data-stu-id="1d4a2-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="1d4a2-113">[out] Ein Zeiger auf die Länge der Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="1d4a2-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d4a2-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1d4a2-114">Return Value</span></span>  
 <span data-ttu-id="1d4a2-115">Diese Methode gibt zusätzlich zu den folgenden Werten Standard-COM-Fehlercodes zurück, wie in WinError.h definiert.</span><span class="sxs-lookup"><span data-stu-id="1d4a2-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="1d4a2-116">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="1d4a2-116">Return code</span></span>|<span data-ttu-id="1d4a2-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1d4a2-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1d4a2-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="1d4a2-118">S_OK</span></span>|<span data-ttu-id="1d4a2-119">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="1d4a2-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="1d4a2-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="1d4a2-120">E_INVALIDARG</span></span>|<span data-ttu-id="1d4a2-121">`szBuffer`null oder `iMax` Null (0).</span><span class="sxs-lookup"><span data-stu-id="1d4a2-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1d4a2-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1d4a2-122">Remarks</span></span>  
 <span data-ttu-id="1d4a2-123">Wenn die Methode nicht `szBuffer` erfolgreich abgeschlossen wird, enthält eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1d4a2-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d4a2-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1d4a2-124">Requirements</span></span>  
 <span data-ttu-id="1d4a2-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d4a2-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d4a2-126">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1d4a2-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1d4a2-127">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1d4a2-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d4a2-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d4a2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d4a2-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1d4a2-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1d4a2-130">LoadStringRC-Funktion</span><span class="sxs-lookup"><span data-stu-id="1d4a2-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="1d4a2-131">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="1d4a2-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
