---
title: ICLRMetaHost::GetRuntime-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.GetRuntime
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::GetRuntime
helpviewer_keywords:
- GetRuntime method [.NET Framework hosting]
- ICLRMetaHost::GetRuntime method [.NET Framework hosting]
ms.assetid: a10749f1-ab91-47cf-982f-d8ccd2e81bd2
topic_type: apiref
caps.latest.revision: "31"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6ebfa1af4b824f4fcd4247cd7d0a667488f3e3ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostgetruntime-method"></a><span data-ttu-id="6981a-102">ICLRMetaHost::GetRuntime-Methode</span><span class="sxs-lookup"><span data-stu-id="6981a-102">ICLRMetaHost::GetRuntime Method</span></span>
<span data-ttu-id="6981a-103">Ruft die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle, die eine bestimmte Version der common Language Runtime (CLR) entspricht.</span><span class="sxs-lookup"><span data-stu-id="6981a-103">Gets the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to a particular version of the common language runtime (CLR).</span></span> <span data-ttu-id="6981a-104">Diese Methode hat Vorrang vor den [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) Funktion, mit der [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) Flag.</span><span class="sxs-lookup"><span data-stu-id="6981a-104">This method supersedes the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6981a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6981a-105">Syntax</span></span>  
  
```  
HRESULT GetRuntime (  
    [in] LPCWSTR pwzVersion,  
    [in, REFIID riid,  
    [out,iid_is(riid), retval] LPVOID *ppRuntime  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6981a-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6981a-106">Parameters</span></span>  
 `pwzVersion`  
 <span data-ttu-id="6981a-107">[in] Version von .NET Framework Kompilierung gespeichert, die in den Metadaten, im Format "V*ein*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="6981a-107">[in] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="6981a-108">*Ein*, *B*, und *X* sind Dezimalzahlen, die die Hauptversion, die Nebenversion und die Nummer des Builds entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6981a-108">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6981a-109">Dieser Parameter muss mit den Namen des Verzeichnisses für die .NET Framework-Version unter C:\Windows\Microsoft.NET\Framework oder C:\Windows\Microsoft.NET\Framework64 übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="6981a-109">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework or C:\Windows\Microsoft.NET\Framework64.</span></span>  
  
 <span data-ttu-id="6981a-110">Beispielwerte sind "Version 1.0.3705", "v1.1.4322", "v2.0.50727" und "v4. 0. *X*", wobei *X* richtet sich nach die Buildnummer installiert.</span><span class="sxs-lookup"><span data-stu-id="6981a-110">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="6981a-111">Das Präfix "V" ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6981a-111">The "v" prefix is required.</span></span>  
  
 `riid`  
 <span data-ttu-id="6981a-112">[in] Der Bezeichner für die gewünschte Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="6981a-112">[in] The identifier for the desired interface.</span></span> <span data-ttu-id="6981a-113">Derzeit ist der einzige gültige Wert für diesen Parameter "IID_ICLRRuntimeInfo".</span><span class="sxs-lookup"><span data-stu-id="6981a-113">Currently, the only valid value for this parameter is IID_ICLRRuntimeInfo.</span></span>  
  
 `ppRuntime`  
 <span data-ttu-id="6981a-114">[out] Ein Zeiger auf die [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle, die der angeforderten Laufzeit entspricht.</span><span class="sxs-lookup"><span data-stu-id="6981a-114">[out] A pointer to the [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface that corresponds to the requested runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6981a-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6981a-115">Return Value</span></span>  
 <span data-ttu-id="6981a-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6981a-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6981a-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6981a-117">HRESULT</span></span>|<span data-ttu-id="6981a-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6981a-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6981a-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="6981a-119">S_OK</span></span>|<span data-ttu-id="6981a-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6981a-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="6981a-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6981a-121">E_POINTER</span></span>|<span data-ttu-id="6981a-122">`pwzVersion` oder `ppRuntime` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="6981a-122">`pwzVersion` or `ppRuntime` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6981a-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6981a-123">Remarks</span></span>  
 <span data-ttu-id="6981a-124">Diese Methode interagiert konsistent mit älteren Schnittstellen wie z. B. die [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) Schnittstelle und Legacy-Funktionen wie z. B. die als veraltet markierten `CorBindTo*` Funktionen (finden Sie unter [veraltet CLR Hosting-Funktionen](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in .NET Framework 2.0 hosting-API).</span><span class="sxs-lookup"><span data-stu-id="6981a-124">This method interacts consistently with legacy interfaces such as the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) interface and legacy functions such as the deprecated `CorBindTo*` functions (see [Deprecated CLR Hosting Functions](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md) in the .NET Framework 2.0 hosting API).</span></span> <span data-ttu-id="6981a-125">D. h. Laufzeiten, die geladen werden, mit dem legacy-API für die neue API sichtbar sind, und Laufzeiten, die mit der neuen API geladen werden, die für die legacy-API sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="6981a-125">That is, runtimes that are loaded with the legacy API are visible to the new API, and runtimes that are loaded with the new API are visible to the legacy API.</span></span> <span data-ttu-id="6981a-126">.</span><span class="sxs-lookup"><span data-stu-id="6981a-126">.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6981a-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6981a-127">Requirements</span></span>  
 <span data-ttu-id="6981a-128">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6981a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6981a-129">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6981a-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6981a-130">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6981a-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6981a-131">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6981a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6981a-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6981a-132">See Also</span></span>  
 [<span data-ttu-id="6981a-133">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6981a-133">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="6981a-134">Veraltete CLR-Hostingschnittstellen und Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="6981a-134">Deprecated CLR Hosting Interfaces and Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-interfaces-and-coclasses.md)  
 [<span data-ttu-id="6981a-135">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="6981a-135">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="6981a-136">Veraltete CLR-Hostingfunktionen</span><span class="sxs-lookup"><span data-stu-id="6981a-136">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [<span data-ttu-id="6981a-137">Hosting</span><span class="sxs-lookup"><span data-stu-id="6981a-137">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
