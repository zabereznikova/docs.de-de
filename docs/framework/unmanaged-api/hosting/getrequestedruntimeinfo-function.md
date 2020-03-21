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
ms.openlocfilehash: db721e1ef774c87de0fa7da178463d832a3da756
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178155"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="449dc-102">GetRequestedRuntimeInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="449dc-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="449dc-103">Ruft Versions- und Verzeichnisinformationen über die von einer Anwendung angeforderte Common Language Runtime (CLR) ab.</span><span class="sxs-lookup"><span data-stu-id="449dc-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="449dc-104">Diese Funktion ist in .NET Framework 4 veraltet.</span><span class="sxs-lookup"><span data-stu-id="449dc-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="449dc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="449dc-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="449dc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="449dc-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="449dc-107">[in] Der Name der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="449dc-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="449dc-108">[in] Eine Zeichenfolge, die die Versionsnummer der Laufzeit angibt.</span><span class="sxs-lookup"><span data-stu-id="449dc-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="449dc-109">[in] Der Name der Konfigurationsdatei, `pExe`die mit verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="449dc-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="449dc-110">[in] Mindestens einer der [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) STARTUP_FLAGS-Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="449dc-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="449dc-111">[in] Mindestens einer der [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) RUNTIME_INFO_FLAGS-Enumerationswerte.</span><span class="sxs-lookup"><span data-stu-id="449dc-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="449dc-112">[out] Ein Puffer, der den Verzeichnispfad zur Laufzeit nach erfolgreichem Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="449dc-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="449dc-113">[in] Die Länge des Verzeichnispuffers.</span><span class="sxs-lookup"><span data-stu-id="449dc-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="449dc-114">[out] Ein Zeiger auf die Länge der Verzeichnispfadzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="449dc-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="449dc-115">[out] Ein Puffer, der die Versionsnummer der Laufzeit nach erfolgreichem Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="449dc-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="449dc-116">[in] Die Länge des Versionszeichenfolgenpuffers.</span><span class="sxs-lookup"><span data-stu-id="449dc-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="449dc-117">[out] Ein Zeiger auf die Länge der Versionszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="449dc-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="449dc-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="449dc-118">Return Value</span></span>  
 <span data-ttu-id="449dc-119">Diese Methode gibt zusätzlich zu den folgenden Werten Com-Fehlercodes (Standard Component Object Model, COM) zurück, wie in WinError.h definiert.</span><span class="sxs-lookup"><span data-stu-id="449dc-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="449dc-120">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="449dc-120">Return code</span></span>|<span data-ttu-id="449dc-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="449dc-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="449dc-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="449dc-122">S_OK</span></span>|<span data-ttu-id="449dc-123">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="449dc-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="449dc-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="449dc-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="449dc-125">Der Verzeichnispuffer ist nicht groß genug, um den Verzeichnispfad zu speichern.</span><span class="sxs-lookup"><span data-stu-id="449dc-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="449dc-126">- oder -</span><span class="sxs-lookup"><span data-stu-id="449dc-126">- or -</span></span><br /><br /> <span data-ttu-id="449dc-127">Der Versionspuffer ist nicht groß genug, um die Versionszeichenfolge zu speichern.</span><span class="sxs-lookup"><span data-stu-id="449dc-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="449dc-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="449dc-128">Remarks</span></span>  
 <span data-ttu-id="449dc-129">Die `GetRequestedRuntimeInfo` Methode gibt Laufzeitinformationen über die in den Prozess geladene Version zurück, die nicht unbedingt die neueste Version ist, die auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="449dc-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="449dc-130">In .NET Framework Version 2.0 können Sie Informationen über die `GetRequestedRuntimeInfo` neueste installierte Version abrufen, indem Sie die Methode wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="449dc-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="449dc-131">Geben `pExe`Sie `pwszVersion`die `pConfigurationFile` , und die Parameter als null an.</span><span class="sxs-lookup"><span data-stu-id="449dc-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="449dc-132">Geben Sie das `RUNTIME_INFO_FLAGS` RUNTIME_INFO_UPGRADE_VERSION-Flag in `runtimeInfoFlags` den Enumerationen für den Parameter an.</span><span class="sxs-lookup"><span data-stu-id="449dc-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="449dc-133">Die `GetRequestedRuntimeInfo` Methode gibt unter den folgenden Umständen nicht die neueste CLR-Version zurück:</span><span class="sxs-lookup"><span data-stu-id="449dc-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="449dc-134">Eine Anwendungskonfigurationsdatei, die das Laden einer bestimmten CLR-Version angibt, ist vorhanden.</span><span class="sxs-lookup"><span data-stu-id="449dc-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="449dc-135">Beachten Sie, dass .NET Framework die Konfigurationsdatei auch `pConfigurationFile` dann verwendet, wenn Sie null für den Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="449dc-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="449dc-136">Die [CorBindToRuntimeEx-Methode](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) wurde aufgerufen, die eine frühere CLR-Version angibt.</span><span class="sxs-lookup"><span data-stu-id="449dc-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="449dc-137">Eine Anwendung, die für eine frühere CLR-Version kompiliert wurde, wird derzeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="449dc-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="449dc-138">Für `runtimeInfoFlags` den Parameter können Sie jeweils nur eine `RUNTIME_INFO_FLAGS` der Architekturkonstanten der Enumeration angeben:</span><span class="sxs-lookup"><span data-stu-id="449dc-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="449dc-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="449dc-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="449dc-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="449dc-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="449dc-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="449dc-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="449dc-142">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="449dc-142">Requirements</span></span>  
 <span data-ttu-id="449dc-143">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="449dc-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="449dc-144">**Kopfzeile:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="449dc-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="449dc-145">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="449dc-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="449dc-146">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="449dc-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="449dc-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="449dc-147">See also</span></span>

- [<span data-ttu-id="449dc-148">GetRequestedRuntimeVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="449dc-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="449dc-149">GetVersionFromProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="449dc-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="449dc-150">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="449dc-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
