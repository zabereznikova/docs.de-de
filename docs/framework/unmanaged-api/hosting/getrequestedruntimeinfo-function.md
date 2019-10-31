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
ms.openlocfilehash: cd1d9e768698115bee22e35699b044e0c3526d2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136323"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="5879d-102">GetRequestedRuntimeInfo-Funktion</span><span class="sxs-lookup"><span data-stu-id="5879d-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="5879d-103">Ruft Informationen zur Version und zum Verzeichnis der von einer Anwendung angeforderten Common Language Runtime (CLR) ab.</span><span class="sxs-lookup"><span data-stu-id="5879d-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="5879d-104">Diese Funktion wurde im .NET Framework 4 als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="5879d-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5879d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5879d-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5879d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5879d-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="5879d-107">in Der Name der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="5879d-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="5879d-108">in Eine Zeichenfolge, die die Versionsnummer der Laufzeit angibt.</span><span class="sxs-lookup"><span data-stu-id="5879d-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="5879d-109">in Der Name der Konfigurationsdatei, die `pExe`zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="5879d-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="5879d-110">in Mindestens ein [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) -Enumerationswert.</span><span class="sxs-lookup"><span data-stu-id="5879d-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="5879d-111">in Mindestens ein [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) -Enumerationswert.</span><span class="sxs-lookup"><span data-stu-id="5879d-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="5879d-112">vorgenommen Ein Puffer, der nach erfolgreichem Abschluss den Verzeichnispfad zur Laufzeit enthält.</span><span class="sxs-lookup"><span data-stu-id="5879d-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="5879d-113">in Die Länge des Verzeichnis Puffers.</span><span class="sxs-lookup"><span data-stu-id="5879d-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="5879d-114">vorgenommen Ein Zeiger auf die Länge der Verzeichnispfad Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5879d-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="5879d-115">vorgenommen Ein Puffer, der die Versionsnummer der Laufzeit nach erfolgreichem Abschluss enthält.</span><span class="sxs-lookup"><span data-stu-id="5879d-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="5879d-116">in Die Länge des Versions Zeichen folgen Puffers.</span><span class="sxs-lookup"><span data-stu-id="5879d-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="5879d-117">vorgenommen Ein Zeiger auf die Länge der Versions Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5879d-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5879d-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5879d-118">Return Value</span></span>  
 <span data-ttu-id="5879d-119">Diese Methode gibt zusätzlich zu den folgenden Werten in WinError. h definierte Standard-Component Object Model (com)-Fehlercodes zurück.</span><span class="sxs-lookup"><span data-stu-id="5879d-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="5879d-120">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="5879d-120">Return code</span></span>|<span data-ttu-id="5879d-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5879d-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="5879d-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="5879d-122">S_OK</span></span>|<span data-ttu-id="5879d-123">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5879d-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="5879d-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="5879d-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="5879d-125">Der Verzeichnis Puffer ist nicht groß genug zum Speichern des Verzeichnis Pfads.</span><span class="sxs-lookup"><span data-stu-id="5879d-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="5879d-126">- oder -</span><span class="sxs-lookup"><span data-stu-id="5879d-126">- or -</span></span><br /><br /> <span data-ttu-id="5879d-127">Der Versions Puffer ist nicht groß genug, um die Versions Zeichenfolge zu speichern.</span><span class="sxs-lookup"><span data-stu-id="5879d-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5879d-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5879d-128">Remarks</span></span>  
 <span data-ttu-id="5879d-129">Die `GetRequestedRuntimeInfo`-Methode gibt Laufzeitinformationen über die Version zurück, die in den Prozess geladen wurde. Dies ist nicht notwendigerweise die neueste Version, die auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="5879d-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="5879d-130">In der .NET Framework Version 2,0 können Sie Informationen zur neuesten installierten Version erhalten, indem Sie die `GetRequestedRuntimeInfo`-Methode wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="5879d-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="5879d-131">Geben Sie die Parameter `pExe`, `pwszVersion`und `pConfigurationFile` als NULL an.</span><span class="sxs-lookup"><span data-stu-id="5879d-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="5879d-132">Geben Sie das RUNTIME_INFO_UPGRADE_VERSION-Flag in den `RUNTIME_INFO_FLAGS` Enumerationen für den `runtimeInfoFlags`-Parameter an.</span><span class="sxs-lookup"><span data-stu-id="5879d-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="5879d-133">Die `GetRequestedRuntimeInfo`-Methode gibt in den folgenden Situationen nicht die neueste CLR-Version zurück:</span><span class="sxs-lookup"><span data-stu-id="5879d-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="5879d-134">Es ist eine Anwendungs Konfigurationsdatei vorhanden, die das Laden einer bestimmten CLR-Version angibt.</span><span class="sxs-lookup"><span data-stu-id="5879d-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="5879d-135">Beachten Sie, dass die .NET Framework die Konfigurationsdatei auch dann verwendet, wenn Sie für den Parameter `pConfigurationFile` NULL angeben.</span><span class="sxs-lookup"><span data-stu-id="5879d-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="5879d-136">Die [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) -Methode wurde aufgerufen, um eine frühere CLR-Version anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5879d-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="5879d-137">Eine Anwendung, die für eine frühere CLR-Version kompiliert wurde, wird zurzeit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5879d-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="5879d-138">Für den `runtimeInfoFlags`-Parameter können Sie jeweils nur eine der Architektur Konstanten der `RUNTIME_INFO_FLAGS` Enumeration angeben:</span><span class="sxs-lookup"><span data-stu-id="5879d-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="5879d-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="5879d-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="5879d-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="5879d-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="5879d-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="5879d-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5879d-142">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5879d-142">Requirements</span></span>  
 <span data-ttu-id="5879d-143">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5879d-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5879d-144">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="5879d-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5879d-145">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5879d-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5879d-146">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5879d-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5879d-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5879d-147">See also</span></span>

- [<span data-ttu-id="5879d-148">GetRequestedRuntimeVersion-Funktion</span><span class="sxs-lookup"><span data-stu-id="5879d-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="5879d-149">GetVersionFromProcess-Funktion</span><span class="sxs-lookup"><span data-stu-id="5879d-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="5879d-150">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="5879d-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
