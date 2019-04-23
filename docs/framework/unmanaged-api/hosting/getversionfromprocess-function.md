---
title: GetVersionFromProcess-Funktion
ms.date: 03/30/2017
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 452104939acf5de7bb151cba00d65fb6631c98d5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124084"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="0c871-102">GetVersionFromProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="0c871-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="0c871-103">Ruft die Versionsnummer der die common Language Runtime (CLR), die dem angegebenen Prozesshandle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="0c871-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="0c871-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="0c871-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c871-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c871-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c871-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="0c871-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="0c871-107">[in] Ein Handle für einen Prozess.</span><span class="sxs-lookup"><span data-stu-id="0c871-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="0c871-108">[out] Ein Puffer, der die Versionsnummer-Zeichenfolge nach dem erfolgreichen Abschluss der Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="0c871-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="0c871-109">[in] Die Länge des Versionspuffers.</span><span class="sxs-lookup"><span data-stu-id="0c871-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="0c871-110">[out] Ein Zeiger auf die Länge der die Versionsnummer-Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0c871-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c871-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0c871-111">Return Value</span></span>  
 <span data-ttu-id="0c871-112">Diese Methode gibt Component Object Model (COM) Standardfehlercodes in "Winerror.h", zusätzlich zu den folgenden Werten definiert.</span><span class="sxs-lookup"><span data-stu-id="0c871-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="0c871-113">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="0c871-113">Return code</span></span>|<span data-ttu-id="0c871-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0c871-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="0c871-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c871-115">S_OK</span></span>|<span data-ttu-id="0c871-116">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0c871-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="0c871-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0c871-117">E_INVALIDARG</span></span>|<span data-ttu-id="0c871-118">`pVersion` ist null und `cchBuffer` ist nicht null ist, oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="0c871-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="0c871-119">- oder - </span><span class="sxs-lookup"><span data-stu-id="0c871-119">-or-</span></span><br /><br /> <span data-ttu-id="0c871-120">`hProcess` ist kein gültiges Handle an einen Prozess.</span><span class="sxs-lookup"><span data-stu-id="0c871-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="0c871-121">- oder - </span><span class="sxs-lookup"><span data-stu-id="0c871-121">-or-</span></span><br /><br /> <span data-ttu-id="0c871-122">Die CLR wird nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="0c871-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="0c871-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="0c871-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="0c871-124">`cchBuffer` ist null oder kleiner als die Länge der Versionszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="0c871-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="0c871-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="0c871-125">E_NOTIMPL</span></span>|<span data-ttu-id="0c871-126">Diese Methode ist nicht auf das Betriebssystem Microsoft Windows 95, Microsoft Windows 98 oder Microsoft Windows Millennium Edition verfügbar.</span><span class="sxs-lookup"><span data-stu-id="0c871-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c871-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0c871-127">Requirements</span></span>  
 <span data-ttu-id="0c871-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c871-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c871-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0c871-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0c871-130">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0c871-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c871-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c871-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c871-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c871-132">See also</span></span>

- [<span data-ttu-id="0c871-133">GetRequestedRuntimeInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="0c871-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="0c871-134">GetRequestedRuntimeVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="0c871-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="0c871-135">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="0c871-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
