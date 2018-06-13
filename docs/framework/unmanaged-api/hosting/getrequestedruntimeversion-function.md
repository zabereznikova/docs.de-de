---
title: GetRequestedRuntimeVersion-Funktion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 977f63b58ccbc709fb9383acf64686fc92808da4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433301"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="4e40d-102">GetRequestedRuntimeVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="4e40d-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="4e40d-103">Ruft die Versionsnummer der von der angegebenen Anwendung angefordert der common Language Runtime (CLR) ab.</span><span class="sxs-lookup"><span data-stu-id="4e40d-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="4e40d-104">Wenn diese Version nicht installiert ist, wird die letzte installierte Version vor der angeforderten Version abgerufen.</span><span class="sxs-lookup"><span data-stu-id="4e40d-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="4e40d-105">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="4e40d-105">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e40d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e40d-106">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *pdwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e40d-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e40d-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="4e40d-108">[in] Der Name der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="4e40d-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="4e40d-109">[out] Ein Puffer, der nach dem erfolgreichen Abschluss die Versionsnummernzeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="4e40d-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="4e40d-110">[in] Die Länge des Versionspuffers.</span><span class="sxs-lookup"><span data-stu-id="4e40d-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="4e40d-111">[out] Ein Zeiger auf die Länge der Versionsnummernzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4e40d-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e40d-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4e40d-112">Return Value</span></span>  
 <span data-ttu-id="4e40d-113">Diese Methode gibt Component Object Model (COM) Standardfehlercodes in WinError.h definiert, zusätzlich zu den folgenden Werten zurück.</span><span class="sxs-lookup"><span data-stu-id="4e40d-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="4e40d-114">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="4e40d-114">Return code</span></span>|<span data-ttu-id="4e40d-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4e40d-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="4e40d-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="4e40d-116">S_OK</span></span>|<span data-ttu-id="4e40d-117">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="4e40d-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="4e40d-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4e40d-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4e40d-119">Die Version Puffer ist nicht groß genug zum Speichern der Versionszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4e40d-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="4e40d-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="4e40d-120">E_POINTER</span></span>|<span data-ttu-id="4e40d-121">`pdwLength` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="4e40d-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4e40d-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e40d-122">Requirements</span></span>  
 <span data-ttu-id="4e40d-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e40d-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e40d-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4e40d-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4e40d-125">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="4e40d-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4e40d-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e40d-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e40d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e40d-127">See Also</span></span>  
 [<span data-ttu-id="4e40d-128">GetRequestedRuntimeInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="4e40d-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [<span data-ttu-id="4e40d-129">GetVersionFromProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="4e40d-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)  
 [<span data-ttu-id="4e40d-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="4e40d-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
