---
title: ICLRRuntimeInfo::GetVersionString-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetVersionString
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ae6f21fac359006b6d2e56fdd4ba50fb18bb972
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfogetversionstring-method"></a><span data-ttu-id="10392-102">ICLRRuntimeInfo::GetVersionString-Methode</span><span class="sxs-lookup"><span data-stu-id="10392-102">ICLRRuntimeInfo::GetVersionString Method</span></span>
<span data-ttu-id="10392-103">Ruft die common Language Runtime (CLR)-Versionsinformationen zugeordneten ab einer angegebenen [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="10392-103">Gets common language runtime (CLR) version information associated with a given [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="10392-104">Diese Methode ersetzt die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="10392-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="10392-105">GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="10392-105">GetRequestedRuntimeInfo</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
  
-   [<span data-ttu-id="10392-106">GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="10392-106">GetRequestedRuntimeVersion</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="10392-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="10392-107">Syntax</span></span>  
  
```  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10392-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="10392-108">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="10392-109">[out] Die Version des .NET Framework-Kompilierung im Format "V*ein*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="10392-109">[out] The .NET Framework compilation version in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="10392-110">*Ein*, *B*, und *X* sind Dezimalzahlen, die die Hauptversion, die Nebenversion und die Nummer des Builds entsprechen.</span><span class="sxs-lookup"><span data-stu-id="10392-110">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="10392-111">*X* ist optional.</span><span class="sxs-lookup"><span data-stu-id="10392-111">*X* is optional.</span></span> <span data-ttu-id="10392-112">Wenn *X* ist nicht vorhanden ist, kein Punkt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="10392-112">If *X* is not present, there is no trailing period.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="10392-113">Dieser Parameter muss mit den Namen des Verzeichnisses für die .NET Framework-Version unter C:\Windows\Microsoft.NET\Framework übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="10392-113">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="10392-114">Beispielwerte sind "Version 1.0.3705", "v1.1.4322", "v2.0.50727" und "v4. 0. *x*", wobei *x* richtet sich nach die Buildnummer installiert.</span><span class="sxs-lookup"><span data-stu-id="10392-114">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*x*", where *x* depends on the build number installed.</span></span> <span data-ttu-id="10392-115">Beachten Sie, dass das Präfix "V" erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="10392-115">Note that the "v" prefix is mandatory.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="10392-116">[in, out] Gibt die Größe des `pwzBuffer` um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="10392-116">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="10392-117">Wenn `pwzBuffer` ist `null`, `pchBuffer` gibt die erforderliche Größe des `pwzBuffer` um die Vorabbelegung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="10392-117">If `pwzBuffer` is `null`, `pchBuffer` returns the required size of `pwzBuffer` to allow preallocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10392-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="10392-118">Return Value</span></span>  
 <span data-ttu-id="10392-119">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="10392-119">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="10392-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="10392-120">HRESULT</span></span>|<span data-ttu-id="10392-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="10392-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="10392-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="10392-122">S_OK</span></span>|<span data-ttu-id="10392-123">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="10392-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="10392-124">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="10392-124">E_POINTER</span></span>|<span data-ttu-id="10392-125">`pwzBuffer` oder `pchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="10392-125">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10392-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="10392-126">Requirements</span></span>  
 <span data-ttu-id="10392-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10392-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10392-128">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="10392-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="10392-129">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="10392-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="10392-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10392-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10392-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="10392-131">See Also</span></span>  
 [<span data-ttu-id="10392-132">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="10392-132">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="10392-133">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="10392-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="10392-134">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="10392-134">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)  
 [<span data-ttu-id="10392-135">Hosting</span><span class="sxs-lookup"><span data-stu-id="10392-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
