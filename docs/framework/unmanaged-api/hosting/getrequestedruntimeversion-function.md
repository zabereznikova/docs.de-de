---
title: GetRequestedRuntimeVersion-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeVersion
helpviewer_keywords: GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 13309a7362f468d3711176db2adc7a82e3b949d3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="7e1f2-102">GetRequestedRuntimeVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="7e1f2-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="7e1f2-103">Ruft die Versionsnummer der von der angegebenen Anwendung angefordert der common Language Runtime (CLR) ab.</span><span class="sxs-lookup"><span data-stu-id="7e1f2-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="7e1f2-104">Wenn diese Version nicht installiert ist, wird die letzte installierte Version vor der angeforderten Version abgerufen.</span><span class="sxs-lookup"><span data-stu-id="7e1f2-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="7e1f2-105">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="7e1f2-105">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7e1f2-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7e1f2-106">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *pdwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7e1f2-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="7e1f2-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="7e1f2-108">[in] Der Name der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="7e1f2-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="7e1f2-109">[out] Ein Puffer, der nach dem erfolgreichen Abschluss die Versionsnummernzeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="7e1f2-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="7e1f2-110">[in] Die Länge des Versionspuffers.</span><span class="sxs-lookup"><span data-stu-id="7e1f2-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="7e1f2-111">[out] Ein Zeiger auf die Länge der Versionsnummernzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7e1f2-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7e1f2-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7e1f2-112">Return Value</span></span>  
 <span data-ttu-id="7e1f2-113">Diese Methode gibt Component Object Model (COM) Standardfehlercodes in WinError.h definiert, zusätzlich zu den folgenden Werten zurück.</span><span class="sxs-lookup"><span data-stu-id="7e1f2-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="7e1f2-114">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="7e1f2-114">Return code</span></span>|<span data-ttu-id="7e1f2-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7e1f2-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="7e1f2-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="7e1f2-116">S_OK</span></span>|<span data-ttu-id="7e1f2-117">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7e1f2-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="7e1f2-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="7e1f2-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="7e1f2-119">Die Version Puffer ist nicht groß genug zum Speichern der Versionszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7e1f2-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="7e1f2-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="7e1f2-120">E_POINTER</span></span>|<span data-ttu-id="7e1f2-121">`pdwLength` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="7e1f2-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7e1f2-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7e1f2-122">Requirements</span></span>  
 <span data-ttu-id="7e1f2-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7e1f2-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e1f2-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7e1f2-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7e1f2-125">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="7e1f2-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7e1f2-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7e1f2-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e1f2-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7e1f2-127">See Also</span></span>  
 [<span data-ttu-id="7e1f2-128">GetRequestedRuntimeInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="7e1f2-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [<span data-ttu-id="7e1f2-129">GetVersionFromProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="7e1f2-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 [<span data-ttu-id="7e1f2-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="7e1f2-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
