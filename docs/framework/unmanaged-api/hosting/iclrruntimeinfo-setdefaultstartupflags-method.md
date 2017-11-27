---
title: ICLRRuntimeInfo::SetDefaultStartupFlags-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.SetDefaultStartupFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1732073b9799453bd32447e7a688b0280e66f1ae
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="b911d-102">ICLRRuntimeInfo::SetDefaultStartupFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="b911d-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="b911d-103">Legt die Startflags und der Host-Konfigurationsdatei, die zum Starten von der Laufzeitmoduls verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b911d-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="b911d-104">Diese Methode ersetzt die Verwendung der `startupFlags` Parameter in der [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) und [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) Funktionen.</span><span class="sxs-lookup"><span data-stu-id="b911d-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b911d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b911d-105">Syntax</span></span>  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b911d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b911d-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="b911d-107">[in] Die Host-Start-Flags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b911d-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="b911d-108">Verwenden Sie die gleichen Flags als mit der [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) und [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) Funktionen.</span><span class="sxs-lookup"><span data-stu-id="b911d-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="b911d-109">[in] Der Verzeichnispfad der Hostkonfigurationsdatei festlegen.</span><span class="sxs-lookup"><span data-stu-id="b911d-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b911d-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b911d-110">Return Value</span></span>  
 <span data-ttu-id="b911d-111">Diese Methode gibt die folgenden spezifischen HRESULT sowie HRESULT-Fehler, die Methodenfehler.</span><span class="sxs-lookup"><span data-stu-id="b911d-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b911d-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b911d-112">HRESULT</span></span>|<span data-ttu-id="b911d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b911d-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b911d-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b911d-114">S_OK</span></span>|<span data-ttu-id="b911d-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b911d-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b911d-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b911d-116">Remarks</span></span>  
 <span data-ttu-id="b911d-117">Ein Multithread-Host muss Aufrufe dieser Methode synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="b911d-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="b911d-118">Andernfalls Thread A aufrufen kann die `SetStartupFlags` -Methode nach Abschluss der Thread B einen Aufruf von `SetStartupFlags` und bevor Thread B die Laufzeit gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="b911d-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b911d-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b911d-119">Requirements</span></span>  
 <span data-ttu-id="b911d-120">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b911d-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b911d-121">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="b911d-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b911d-122">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b911d-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b911d-123">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b911d-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b911d-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b911d-124">See Also</span></span>  
 [<span data-ttu-id="b911d-125">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b911d-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="b911d-126">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="b911d-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="b911d-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="b911d-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
