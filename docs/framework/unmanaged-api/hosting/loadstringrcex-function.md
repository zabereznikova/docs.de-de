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
ms.openlocfilehash: 68332aee895f012bcf6ab6a72936c8dddc7f28a0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122038"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="aba51-102">LoadStringRCEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="aba51-102">LoadStringRCEx Function</span></span>
<span data-ttu-id="aba51-103">Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.</span><span class="sxs-lookup"><span data-stu-id="aba51-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="aba51-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="aba51-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aba51-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="aba51-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="aba51-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="aba51-106">Parameters</span></span>  
 `lcid`  
 <span data-ttu-id="aba51-107">in Ein Kultur Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="aba51-107">[in] A culture identifier.</span></span> <span data-ttu-id="aba51-108">Übergeben Sie den Wert-1 für `lcid`, um die Standard Kultur zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="aba51-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="aba51-109">in Ein HRESULT.</span><span class="sxs-lookup"><span data-stu-id="aba51-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="aba51-110">vorgenommen Ein Puffer, der die Fehlermeldung nach erfolgreichem Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="aba51-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="aba51-111">in Die Größe des Fehlermeldungs Puffers.</span><span class="sxs-lookup"><span data-stu-id="aba51-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="aba51-112">in Erten.</span><span class="sxs-lookup"><span data-stu-id="aba51-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="aba51-113">vorgenommen Ein Zeiger auf die Länge der Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="aba51-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aba51-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="aba51-114">Return Value</span></span>  
 <span data-ttu-id="aba51-115">Diese Methode gibt neben den folgenden Werten Standard-COM-Fehlercodes zurück, die in WinError. h definiert sind.</span><span class="sxs-lookup"><span data-stu-id="aba51-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="aba51-116">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="aba51-116">Return code</span></span>|<span data-ttu-id="aba51-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aba51-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="aba51-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="aba51-118">S_OK</span></span>|<span data-ttu-id="aba51-119">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="aba51-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="aba51-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="aba51-120">E_INVALIDARG</span></span>|<span data-ttu-id="aba51-121">`szBuffer` ist NULL, oder `iMax` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="aba51-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="aba51-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="aba51-122">Remarks</span></span>  
 <span data-ttu-id="aba51-123">Wenn die Methode nicht erfolgreich abgeschlossen wird, enthält `szBuffer` eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="aba51-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aba51-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aba51-124">Requirements</span></span>  
 <span data-ttu-id="aba51-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aba51-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aba51-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="aba51-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aba51-127">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="aba51-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aba51-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aba51-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aba51-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aba51-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="aba51-130">LoadStringRC-Funktion</span><span class="sxs-lookup"><span data-stu-id="aba51-130">LoadStringRC Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)
- [<span data-ttu-id="aba51-131">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="aba51-131">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
