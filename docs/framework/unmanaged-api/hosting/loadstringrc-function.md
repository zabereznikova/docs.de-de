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
ms.openlocfilehash: 16f95f8fce20f2cf46d4cda214e4494bd288bf60
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727548"
---
# <a name="loadstringrc-function"></a><span data-ttu-id="5d3bc-102">LoadStringRC-Funktion</span><span class="sxs-lookup"><span data-stu-id="5d3bc-102">LoadStringRC Function</span></span>

<span data-ttu-id="5d3bc-103">Übersetzt einen HRESULT-Wert in eine Fehlermeldung, wobei die Standardkultur des aktuellen Threads verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5d3bc-103">Translates an HRESULT value into an error message by using the default culture of the current thread.</span></span>  
  
 <span data-ttu-id="5d3bc-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="5d3bc-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d3bc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d3bc-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadStringRC (  
    [in]  UINT    iResourceID,
    [out] LPWSTR  szBuffer,
    [in]  int     iMax,
    [in]  int     bQuiet  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d3bc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d3bc-106">Parameters</span></span>  

 `iResourceID`  
 <span data-ttu-id="5d3bc-107">[in] Ein HRESULT.</span><span class="sxs-lookup"><span data-stu-id="5d3bc-107">[in] An HRESULT.</span></span>  
  
 `szBuffer`  
 <span data-ttu-id="5d3bc-108">vorgenommen Ein Puffer, der die Fehlermeldung nach erfolgreichem Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="5d3bc-108">[out] A buffer that contains the error message upon successful completion.</span></span>  
  
 `iMax`  
 <span data-ttu-id="5d3bc-109">in Die Größe des Fehlermeldungs Puffers.</span><span class="sxs-lookup"><span data-stu-id="5d3bc-109">[in] The size of the error message buffer.</span></span>  
  
 `bQuiet`  
 <span data-ttu-id="5d3bc-110">in Erten.</span><span class="sxs-lookup"><span data-stu-id="5d3bc-110">[in] Ignored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5d3bc-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5d3bc-111">Return Value</span></span>  

 <span data-ttu-id="5d3bc-112">Diese Methode gibt zusätzlich zu den folgenden Werten in WinError. h definierte Standard-Component Object Model (com)-Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="5d3bc-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="5d3bc-113">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="5d3bc-113">Return code</span></span>|<span data-ttu-id="5d3bc-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5d3bc-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5d3bc-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="5d3bc-115">S_OK</span></span>|<span data-ttu-id="5d3bc-116">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5d3bc-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="5d3bc-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="5d3bc-117">E_INVALIDARG</span></span>|<span data-ttu-id="5d3bc-118">`szBuffer` ist NULL oder `iMax` ist NULL (0).</span><span class="sxs-lookup"><span data-stu-id="5d3bc-118">`szBuffer` is null or `iMax` is zero (0).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d3bc-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5d3bc-119">Remarks</span></span>  

 <span data-ttu-id="5d3bc-120">Wenn die Methode nicht erfolgreich abgeschlossen wird, `szBuffer` enthält eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5d3bc-120">If the method does not complete successfully, `szBuffer` contains an empty string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d3bc-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5d3bc-121">Requirements</span></span>  

 <span data-ttu-id="5d3bc-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d3bc-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d3bc-123">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="5d3bc-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d3bc-124">**Bibliothek:** MSCorEE.dll und Mscorwks.dll.</span><span class="sxs-lookup"><span data-stu-id="5d3bc-124">**Library:** MSCorEE.dll and Mscorwks.dll.</span></span> <span data-ttu-id="5d3bc-125">Verwenden Sie MSCorEE.dll anstelle von Mscorwks.dll, um sicherzustellen, dass Sie die richtige Version der .NET Framework als Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="5d3bc-125">Use MSCorEE.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 <span data-ttu-id="5d3bc-126">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d3bc-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d3bc-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5d3bc-127">See also</span></span>

- [<span data-ttu-id="5d3bc-128">LoadStringRCEx-Funktion</span><span class="sxs-lookup"><span data-stu-id="5d3bc-128">LoadStringRCEx Function</span></span>](loadstringrcex-function.md)
- [<span data-ttu-id="5d3bc-129">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="5d3bc-129">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
