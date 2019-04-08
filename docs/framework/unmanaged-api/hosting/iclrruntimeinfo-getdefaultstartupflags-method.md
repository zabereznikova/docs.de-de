---
title: ICLRRuntimeInfo::GetDefaultStartupFlags-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c39ad4638c7db45c481bd3dfccb0a82759397aa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072576"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="bbff8-102">ICLRRuntimeInfo::GetDefaultStartupFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="bbff8-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>
<span data-ttu-id="bbff8-103">Ruft die Startflags und Host-Konfigurationsdatei, die zum Starten der Laufzeit verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bbff8-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbff8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bbff8-104">Syntax</span></span>  
  
```  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbff8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bbff8-105">Parameters</span></span>  
 `pdwStartupFlags`  
 <span data-ttu-id="bbff8-106">[out] Ein Zeiger auf die Host-Start-Flags, die momentan festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="bbff8-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="bbff8-107">[out] Ein Zeiger auf den Verzeichnispfad der die aktuelle Konfigurationsdatei für den Host.</span><span class="sxs-lookup"><span data-stu-id="bbff8-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="bbff8-108">[in, out] Bei Eingabe, die Größe des `pwzHostConfigFile`, um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="bbff8-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="bbff8-109">Wenn `pwzHostConfigFile` ist null, die Methode zurückgibt, die erforderliche Größe des `pwzHostConfigFile` für vorab-Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="bbff8-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bbff8-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bbff8-110">Return Value</span></span>  
 <span data-ttu-id="bbff8-111">Diese Methode gibt zurück, die folgende spezifischen HRESULT sowie HRESULT-Fehler, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bbff8-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="bbff8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bbff8-112">HRESULT</span></span>|<span data-ttu-id="bbff8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bbff8-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bbff8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="bbff8-114">S_OK</span></span>|<span data-ttu-id="bbff8-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bbff8-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbff8-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bbff8-116">Remarks</span></span>  
 <span data-ttu-id="bbff8-117">Diese Methode gibt die Standardwerte für das Flag zurück (`STARTUP_CONCURRENT_GC` und `NULL`), oder die Beispielwerte durch einen vorherigen Aufruf der [ICLRRuntimeInfo:: SetDefaultStartupFlags-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), oder von einem festgelegten Werte die `CorBind*` Methoden, wenn sie für diese Runtime gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="bbff8-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbff8-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bbff8-118">Requirements</span></span>  
 <span data-ttu-id="bbff8-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbff8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbff8-120">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="bbff8-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bbff8-121">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bbff8-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="bbff8-122">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="bbff8-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bbff8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bbff8-123">See also</span></span>

- [<span data-ttu-id="bbff8-124">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bbff8-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="bbff8-125">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="bbff8-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="bbff8-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="bbff8-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
