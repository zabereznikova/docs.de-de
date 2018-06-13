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
ms.openlocfilehash: 0b57d04a8a49371872c679a331b5ae9c45dce797
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433072"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="f1142-102">GetVersionFromProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="f1142-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="f1142-103">Ruft die Versionsnummer der common Language Runtime (CLR), die dem angegebenen Prozesshandle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f1142-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="f1142-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="f1142-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1142-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f1142-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1142-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f1142-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="f1142-107">[in] Ein Handle für einen Prozess.</span><span class="sxs-lookup"><span data-stu-id="f1142-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="f1142-108">[out] Ein Puffer, der die Versionsnummer-Zeichenfolge nach erfolgreichem Abschluss der Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="f1142-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f1142-109">[in] Die Länge des Versionspuffers.</span><span class="sxs-lookup"><span data-stu-id="f1142-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="f1142-110">[out] Ein Zeiger auf die Länge der Versionsnummernzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f1142-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f1142-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f1142-111">Return Value</span></span>  
 <span data-ttu-id="f1142-112">Diese Methode gibt Component Object Model (COM) Standardfehlercodes in WinError.h definiert, zusätzlich zu den folgenden Werten zurück.</span><span class="sxs-lookup"><span data-stu-id="f1142-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="f1142-113">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="f1142-113">Return code</span></span>|<span data-ttu-id="f1142-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f1142-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f1142-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f1142-115">S_OK</span></span>|<span data-ttu-id="f1142-116">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f1142-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="f1142-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f1142-117">E_INVALIDARG</span></span>|<span data-ttu-id="f1142-118">`pVersion` ist null und `cchBuffer` ist ungleich null, oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="f1142-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="f1142-119">- oder - </span><span class="sxs-lookup"><span data-stu-id="f1142-119">-or-</span></span><br /><br /> <span data-ttu-id="f1142-120">`hProcess` ist kein gültiges Handle an einen Prozess.</span><span class="sxs-lookup"><span data-stu-id="f1142-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="f1142-121">- oder - </span><span class="sxs-lookup"><span data-stu-id="f1142-121">-or-</span></span><br /><br /> <span data-ttu-id="f1142-122">Die CLR wird nicht geladen werden.</span><span class="sxs-lookup"><span data-stu-id="f1142-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="f1142-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f1142-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f1142-124">`cchBuffer` ist null oder kleiner als die Länge der Versionszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f1142-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="f1142-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="f1142-125">E_NOTIMPL</span></span>|<span data-ttu-id="f1142-126">Diese Methode ist nicht auf dem Betriebssystem Microsoft Windows 95, Microsoft Windows 98 oder Microsoft Windows Millennium Edition verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f1142-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f1142-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f1142-127">Requirements</span></span>  
 <span data-ttu-id="f1142-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1142-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1142-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="f1142-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f1142-130">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="f1142-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f1142-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1142-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1142-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1142-132">See Also</span></span>  
 [<span data-ttu-id="f1142-133">GetRequestedRuntimeInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="f1142-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [<span data-ttu-id="f1142-134">GetRequestedRuntimeVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="f1142-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [<span data-ttu-id="f1142-135">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="f1142-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
