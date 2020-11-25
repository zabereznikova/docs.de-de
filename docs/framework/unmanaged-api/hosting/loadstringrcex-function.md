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
ms.openlocfilehash: 1aa5c9f5dd7dd63e69c2eed1f6dd8ad6f007f01f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727535"
---
# <a name="loadstringrcex-function"></a><span data-ttu-id="7267e-102">LoadStringRCEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="7267e-102">LoadStringRCEx Function</span></span>

<span data-ttu-id="7267e-103">Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.</span><span class="sxs-lookup"><span data-stu-id="7267e-103">Translates an HRESULT value to an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="7267e-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="7267e-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7267e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7267e-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="7267e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7267e-106">Parameters</span></span>  

 `lcid`  
 <span data-ttu-id="7267e-107">in Ein Kultur Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="7267e-107">[in] A culture identifier.</span></span> <span data-ttu-id="7267e-108">Übergeben Sie den Wert-1 für `lcid` , um die Standard Kultur zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="7267e-108">Pass -1 for `lcid` to use the default culture.</span></span>  
  
 `iResourceID`  
 <span data-ttu-id="7267e-109">[in] Ein HRESULT.</span><span class="sxs-lookup"><span data-stu-id="7267e-109">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="7267e-110">vorgenommen Ein Puffer, der die Fehlermeldung nach erfolgreichem Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="7267e-110">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="7267e-111">in Die Größe des Fehlermeldungs Puffers.</span><span class="sxs-lookup"><span data-stu-id="7267e-111">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="7267e-112">in Erten.</span><span class="sxs-lookup"><span data-stu-id="7267e-112">[in] Ignored.</span></span>  
  
 `pcwchUsed`  
 <span data-ttu-id="7267e-113">vorgenommen Ein Zeiger auf die Länge der Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="7267e-113">[out] A pointer to the length of the error message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7267e-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7267e-114">Return Value</span></span>  

 <span data-ttu-id="7267e-115">Diese Methode gibt neben den folgenden Werten Standard-COM-Fehlercodes zurück, die in WinError. h definiert sind.</span><span class="sxs-lookup"><span data-stu-id="7267e-115">This method returns standard COM error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="7267e-116">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="7267e-116">Return code</span></span>|<span data-ttu-id="7267e-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="7267e-117">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="7267e-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="7267e-118">S_OK</span></span>|<span data-ttu-id="7267e-119">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7267e-119">The method completed successfully.</span></span>|  
|<span data-ttu-id="7267e-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="7267e-120">E_INVALIDARG</span></span>|<span data-ttu-id="7267e-121">`szBuffer` ist NULL, oder `iMax` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="7267e-121">`szBuffer` is null, or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7267e-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7267e-122">Remarks</span></span>  

 <span data-ttu-id="7267e-123">Wenn die Methode nicht erfolgreich abgeschlossen wird, `szBuffer` enthält eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7267e-123">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7267e-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7267e-124">Requirements</span></span>  

 <span data-ttu-id="7267e-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7267e-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7267e-126">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="7267e-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7267e-127">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7267e-127">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7267e-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7267e-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7267e-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7267e-129">See also</span></span>

- <xref:System.Globalization.CultureInfo.LCID%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7267e-130">LoadStringRC-Funktion</span><span class="sxs-lookup"><span data-stu-id="7267e-130">LoadStringRC Function</span></span>](loadstringrc-function.md)
- [<span data-ttu-id="7267e-131">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="7267e-131">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
