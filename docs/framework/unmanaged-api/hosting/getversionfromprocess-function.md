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
ms.openlocfilehash: a04a0c5e6865c3664d2cb5fb341c3625e35d4d7c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178128"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="072df-102">GetVersionFromProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="072df-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="072df-103">Ruft die Versionsnummer der Common Language Runtime (CLR) ab, die dem angegebenen Prozesshandle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="072df-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="072df-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="072df-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="072df-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="072df-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,
    [out] LPWSTR  pVersion,
    [in]  DWORD   cchBuffer,
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="072df-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="072df-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="072df-107">[in] Ein Handle für einen Prozess.</span><span class="sxs-lookup"><span data-stu-id="072df-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="072df-108">[out] Ein Puffer, der die Versionsnummernzeichenfolge nach erfolgreichem Abschluss der Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="072df-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="072df-109">[in] Die Länge des Versionspuffers.</span><span class="sxs-lookup"><span data-stu-id="072df-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="072df-110">[out] Ein Zeiger auf die Länge der Versionsnummernzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="072df-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="072df-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="072df-111">Return Value</span></span>  
 <span data-ttu-id="072df-112">Diese Methode gibt zusätzlich zu den folgenden Werten Com-Fehlercodes (Standard Component Object Model, COM) zurück, wie in WinError.h definiert.</span><span class="sxs-lookup"><span data-stu-id="072df-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="072df-113">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="072df-113">Return code</span></span>|<span data-ttu-id="072df-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="072df-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="072df-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="072df-115">S_OK</span></span>|<span data-ttu-id="072df-116">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="072df-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="072df-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="072df-117">E_INVALIDARG</span></span>|<span data-ttu-id="072df-118">`pVersion`ist null `cchBuffer` und ist nicht null oder umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="072df-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="072df-119">Oder</span><span class="sxs-lookup"><span data-stu-id="072df-119">-or-</span></span><br /><br /> <span data-ttu-id="072df-120">`hProcess`ist kein gültiges Handle für einen Prozess.</span><span class="sxs-lookup"><span data-stu-id="072df-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="072df-121">Oder</span><span class="sxs-lookup"><span data-stu-id="072df-121">-or-</span></span><br /><br /> <span data-ttu-id="072df-122">Die CLR wird nicht geladen.</span><span class="sxs-lookup"><span data-stu-id="072df-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="072df-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="072df-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="072df-124">`cchBuffer`null oder kleiner als die Länge der Versionszeichenfolge ist.</span><span class="sxs-lookup"><span data-stu-id="072df-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="072df-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="072df-125">E_NOTIMPL</span></span>|<span data-ttu-id="072df-126">Diese Methode ist für das Betriebssystem Microsoft Windows 95, Microsoft Windows 98 oder Microsoft Windows Millennium Edition nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="072df-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="072df-127">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="072df-127">Requirements</span></span>  
 <span data-ttu-id="072df-128">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="072df-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="072df-129">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="072df-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="072df-130">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="072df-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="072df-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="072df-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="072df-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="072df-132">See also</span></span>

- [<span data-ttu-id="072df-133">GetRequestedRuntimeInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="072df-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="072df-134">GetRequestedRuntimeVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="072df-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="072df-135">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="072df-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
