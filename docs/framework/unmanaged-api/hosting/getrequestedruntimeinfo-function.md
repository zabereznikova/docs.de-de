---
title: GetRequestedRuntimeInfo-Funktion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51cd834b92dd595b5b3e7f668ef252462f4287de
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54695282"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="435d1-102">GetRequestedRuntimeInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="435d1-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="435d1-103">Ruft Version und Verzeichnisinformationen Informationen über die common Language Runtime (CLR), das von einer Anwendung angefordert.</span><span class="sxs-lookup"><span data-stu-id="435d1-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="435d1-104">Diese Funktion ist in [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] veraltet.</span><span class="sxs-lookup"><span data-stu-id="435d1-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="435d1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="435d1-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,   
    [in]  LPCWSTR  pwszVersion,   
    [in]  LPCWSTR  pConfigurationFile,   
    [in]  DWORD    startupFlags,   
    [in]  DWORD    runtimeInfoFlags,   
    [out] LPWSTR   pDirectory,   
    [in]  DWORD    dwDirectory,   
    [out] DWORD   *dwDirectoryLength,   
    [out] LPWSTR   pVersion,   
    [in]  DWORD    cchBuffer,   
    [out] DWORD   *dwlength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="435d1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="435d1-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="435d1-107">[in] Der Name der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="435d1-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="435d1-108">[in] Eine Zeichenfolge, die die Versionsnummer der Laufzeit angeben.</span><span class="sxs-lookup"><span data-stu-id="435d1-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="435d1-109">[in] Der Name der Konfigurationsdatei, die zugeordnet wird `pExe`.</span><span class="sxs-lookup"><span data-stu-id="435d1-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="435d1-110">[in] Mindestens eines der [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) -Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="435d1-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="435d1-111">[in] Mindestens eines der [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) -Enumerationswerte fest.</span><span class="sxs-lookup"><span data-stu-id="435d1-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="435d1-112">[out] Ein Puffer, der den Verzeichnispfad für die Laufzeit nach dem erfolgreichen Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="435d1-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="435d1-113">[in] Die Länge des Verzeichnispuffers.</span><span class="sxs-lookup"><span data-stu-id="435d1-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="435d1-114">[out] Ein Zeiger auf die Länge der Zeichenfolge für den Verzeichnispfad.</span><span class="sxs-lookup"><span data-stu-id="435d1-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="435d1-115">[out] Ein Puffer, der die Versionsnummer der Common Language Runtime nach dem erfolgreichen Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="435d1-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="435d1-116">[in] Die Länge des Puffers für die Versionszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="435d1-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="435d1-117">[out] Ein Zeiger auf die Länge der Versionszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="435d1-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="435d1-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="435d1-118">Return Value</span></span>  
 <span data-ttu-id="435d1-119">Diese Methode gibt Component Object Model (COM) Standardfehlercodes in "Winerror.h", zusätzlich zu den folgenden Werten definiert.</span><span class="sxs-lookup"><span data-stu-id="435d1-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="435d1-120">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="435d1-120">Return code</span></span>|<span data-ttu-id="435d1-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="435d1-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="435d1-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="435d1-122">S_OK</span></span>|<span data-ttu-id="435d1-123">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="435d1-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="435d1-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="435d1-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="435d1-125">Der Directory-Puffer ist nicht groß genug ist, um den Verzeichnispfad zu speichern.</span><span class="sxs-lookup"><span data-stu-id="435d1-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="435d1-126">- oder -</span><span class="sxs-lookup"><span data-stu-id="435d1-126">- or -</span></span><br /><br /> <span data-ttu-id="435d1-127">Die Version-Puffer ist nicht groß genug zum Speichern der Versionszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="435d1-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="435d1-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="435d1-128">Remarks</span></span>  
 <span data-ttu-id="435d1-129">Die `GetRequestedRuntimeInfo` Methodenrückgabe Laufzeitinformationen über die Version geladen, die in den Prozess, der nicht unbedingt die neueste Version auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="435d1-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="435d1-130">In .NET Framework, Version 2.0, erhalten Sie Informationen über die neueste installierte Version mithilfe der `GetRequestedRuntimeInfo` -Methode wie folgt:</span><span class="sxs-lookup"><span data-stu-id="435d1-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
-   <span data-ttu-id="435d1-131">Geben Sie die `pExe`, `pwszVersion`, und `pConfigurationFile` Parameter als Null.</span><span class="sxs-lookup"><span data-stu-id="435d1-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
-   <span data-ttu-id="435d1-132">Geben Sie das Flag RUNTIME_INFO_UPGRADE_VERSION in die `RUNTIME_INFO_FLAGS` Enumerationen für die `runtimeInfoFlags` Parameter.</span><span class="sxs-lookup"><span data-stu-id="435d1-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="435d1-133">Die `GetRequestedRuntimeInfo` Methode nicht die neueste Version der CLR in den folgenden Situationen zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="435d1-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
-   <span data-ttu-id="435d1-134">Die Konfigurationsdatei einer Anwendung, die angibt, laden eine bestimmte CLR-Version vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="435d1-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="435d1-135">Beachten Sie, dass .NET Framework die Konfigurationsdatei verwendet wird, auch wenn Sie null für angeben der `pConfigurationFile` Parameter.</span><span class="sxs-lookup"><span data-stu-id="435d1-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
-   <span data-ttu-id="435d1-136">Die [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) Methode wurde aufgerufen, die eine frühere Version der CLR angibt.</span><span class="sxs-lookup"><span data-stu-id="435d1-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
-   <span data-ttu-id="435d1-137">Eine Anwendung, die für eine frühere Version der CLR kompiliert wurde, wird derzeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="435d1-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="435d1-138">Für die `runtimeInfoFlags` -Parameters, können Sie angeben nur eine der Architekturkonstanten der `RUNTIME_INFO_FLAGS` Enumeration zu einem Zeitpunkt:</span><span class="sxs-lookup"><span data-stu-id="435d1-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
-   <span data-ttu-id="435d1-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="435d1-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
-   <span data-ttu-id="435d1-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="435d1-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
-   <span data-ttu-id="435d1-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="435d1-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="435d1-142">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="435d1-142">Requirements</span></span>  
 <span data-ttu-id="435d1-143">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="435d1-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="435d1-144">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="435d1-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="435d1-145">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="435d1-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="435d1-146">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="435d1-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="435d1-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="435d1-147">See also</span></span>
- [<span data-ttu-id="435d1-148">GetRequestedRuntimeVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="435d1-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="435d1-149">GetVersionFromProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="435d1-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="435d1-150">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="435d1-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
