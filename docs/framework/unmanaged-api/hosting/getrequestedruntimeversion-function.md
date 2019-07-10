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
ms.openlocfilehash: 4083440903e6147ae645f2d6420f19160471841c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779571"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="a6e84-102">GetRequestedRuntimeVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="a6e84-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="a6e84-103">Ruft die Versionsnummer der von der angegebenen Anwendung angeforderten die common Language Runtime (CLR) ab.</span><span class="sxs-lookup"><span data-stu-id="a6e84-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="a6e84-104">Wenn diese Version nicht installiert ist, wird die letzte installierte Version vor der angeforderten Version abgerufen.</span><span class="sxs-lookup"><span data-stu-id="a6e84-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="a6e84-105">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="a6e84-105">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6e84-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6e84-106">Syntax</span></span>  
  
```cpp  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6e84-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="a6e84-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="a6e84-108">[in] Der Name der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="a6e84-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="a6e84-109">[out] Ein Puffer, der die Versionsnummer-Zeichenfolge nach dem erfolgreichen Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="a6e84-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="a6e84-110">[in] Die Länge des Versionspuffers.</span><span class="sxs-lookup"><span data-stu-id="a6e84-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="a6e84-111">[out] Ein Zeiger auf die Länge der die Versionsnummer-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a6e84-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6e84-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a6e84-112">Return Value</span></span>  
 <span data-ttu-id="a6e84-113">Diese Methode gibt Component Object Model (COM) Standardfehlercodes in "Winerror.h", zusätzlich zu den folgenden Werten definiert.</span><span class="sxs-lookup"><span data-stu-id="a6e84-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="a6e84-114">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="a6e84-114">Return code</span></span>|<span data-ttu-id="a6e84-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6e84-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="a6e84-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="a6e84-116">S_OK</span></span>|<span data-ttu-id="a6e84-117">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a6e84-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="a6e84-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="a6e84-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="a6e84-119">Die Version-Puffer ist nicht groß genug zum Speichern der Versionszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a6e84-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="a6e84-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="a6e84-120">E_POINTER</span></span>|<span data-ttu-id="a6e84-121">`pdwLength` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="a6e84-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a6e84-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a6e84-122">Requirements</span></span>  
 <span data-ttu-id="a6e84-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6e84-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6e84-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a6e84-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a6e84-125">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a6e84-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a6e84-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6e84-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6e84-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6e84-127">See also</span></span>

- [<span data-ttu-id="a6e84-128">GetRequestedRuntimeInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="a6e84-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="a6e84-129">GetVersionFromProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="a6e84-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="a6e84-130">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="a6e84-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
