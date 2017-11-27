---
title: GetRealProcAddress-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRealProcAddress
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetRealProcAddress
helpviewer_keywords: GetRealProcAddress function [.NET Framework hosting]
ms.assetid: f1f2fab1-400b-488f-95f2-d49c4fca3556
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 53e51bcf72f1a59f5c471564022d0d8c415381a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="getrealprocaddress-function"></a><span data-ttu-id="f2ce8-102">GetRealProcAddress-Funktion</span><span class="sxs-lookup"><span data-stu-id="f2ce8-102">GetRealProcAddress Function</span></span>
<span data-ttu-id="f2ce8-103">Ruft die Adresse der angegebenen Funktion, die aus der zuletzt installierten Version der common Language Runtime (CLR) exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="f2ce8-103">Gets the address of the specified function that is exported from the latest installed version of the common language runtime (CLR).</span></span>  
  
 <span data-ttu-id="f2ce8-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="f2ce8-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f2ce8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f2ce8-105">Syntax</span></span>  
  
```  
HRESULT GetRealProcAddress (  
    [in]  LPCSTR  pwszProcName,   
    [out] VOID  **ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f2ce8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f2ce8-106">Parameters</span></span>  
 `pwszProcName`  
 <span data-ttu-id="f2ce8-107">[in] Der Name der Funktion.</span><span class="sxs-lookup"><span data-stu-id="f2ce8-107">[in] The name of the function.</span></span>  
  
 `ppv`  
 <span data-ttu-id="f2ce8-108">[out] Der Speicherort, der einen Zeiger auf die Adresse der Funktion empfängt.</span><span class="sxs-lookup"><span data-stu-id="f2ce8-108">[out] The location that receives a pointer to the address of the function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f2ce8-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f2ce8-109">Return Value</span></span>  
 <span data-ttu-id="f2ce8-110">Diese Methode gibt Component Object Model (COM) Standardfehlercodes in WinError.h definiert, zusätzlich zu den folgenden Werten in WinError.h definiert.</span><span class="sxs-lookup"><span data-stu-id="f2ce8-110">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values defined in CorError.h.</span></span>  
  
|<span data-ttu-id="f2ce8-111">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="f2ce8-111">Return code</span></span>|<span data-ttu-id="f2ce8-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f2ce8-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f2ce8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="f2ce8-113">S_OK</span></span>|<span data-ttu-id="f2ce8-114">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f2ce8-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="f2ce8-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f2ce8-115">E_POINTER</span></span>|<span data-ttu-id="f2ce8-116">`ppv` ist nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="f2ce8-116">`ppv` is not valid.</span></span>|  
|<span data-ttu-id="f2ce8-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="f2ce8-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="f2ce8-118">Die Funktion wird von der Laufzeit nicht exportiert.</span><span class="sxs-lookup"><span data-stu-id="f2ce8-118">The function is not exported from the runtime.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f2ce8-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f2ce8-119">Requirements</span></span>  
 <span data-ttu-id="f2ce8-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f2ce8-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f2ce8-121">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f2ce8-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f2ce8-122">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="f2ce8-122">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f2ce8-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f2ce8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ce8-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2ce8-124">See Also</span></span>  
 [<span data-ttu-id="f2ce8-125">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="f2ce8-125">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
