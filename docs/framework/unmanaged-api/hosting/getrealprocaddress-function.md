---
title: GetRealProcAddress-Funktion
ms.date: 03/30/2017
api_name:
- GetRealProcAddress
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetRealProcAddress
helpviewer_keywords:
- GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type:
- apiref
ms.openlocfilehash: 4c914e00987053b1c1e9e00bf8e54632175e1de8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178158"
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="6a9f3-102">GetRealProcAddress-Funktion</span><span class="sxs-lookup"><span data-stu-id="6a9f3-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="6a9f3-103">Ruft die Adresse der angegebenen Funktion ab, die aus der zuletzt installierten Version der Common Language Runtime (CLR) exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="6a9f3-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="6a9f3-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="6a9f3-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a9f3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6a9f3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,
    [out] VOID  **ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a9f3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6a9f3-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="6a9f3-107">[in] Der Name der Funktion.</span><span class="sxs-lookup"><span data-stu-id="6a9f3-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="6a9f3-108">[out] Die Position, die einen Zeiger auf die Adresse der Funktion empfängt.</span><span class="sxs-lookup"><span data-stu-id="6a9f3-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a9f3-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6a9f3-109">Return Value</span></span>  
 <span data-ttu-id="6a9f3-110">Diese Methode gibt zusätzlich zu den in CorError.h definierten Standard-COM-Fehlercodes (Component Object Model) zurück, wie in WinError.h definiert.</span><span class="sxs-lookup"><span data-stu-id="6a9f3-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="6a9f3-111">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="6a9f3-111">Return code</span></span>|<span data-ttu-id="6a9f3-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6a9f3-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="6a9f3-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6a9f3-113">S_OK</span></span>|<span data-ttu-id="6a9f3-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6a9f3-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="6a9f3-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6a9f3-115">E_POINTER</span></span>|<span data-ttu-id="6a9f3-116">`ppv` ist nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="6a9f3-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="6a9f3-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="6a9f3-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="6a9f3-118">Die Funktion wird nicht aus der Laufzeit exportiert.</span><span class="sxs-lookup"><span data-stu-id="6a9f3-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6a9f3-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6a9f3-119">Requirements</span></span>  
 <span data-ttu-id="6a9f3-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a9f3-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a9f3-121">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6a9f3-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6a9f3-122">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6a9f3-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6a9f3-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a9f3-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a9f3-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6a9f3-124">See also</span></span>

- [<span data-ttu-id="6a9f3-125">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="6a9f3-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
