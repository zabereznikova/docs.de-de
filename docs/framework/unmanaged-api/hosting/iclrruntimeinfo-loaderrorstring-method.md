---
title: ICLRRuntimeInfo::LoadErrorString-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.LoadErrorString
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26fa051e5c4735307edbb443e6615a57190c0ae5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="38cc8-102">ICLRRuntimeInfo::LoadErrorString-Methode</span><span class="sxs-lookup"><span data-stu-id="38cc8-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="38cc8-103">Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.</span><span class="sxs-lookup"><span data-stu-id="38cc8-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="38cc8-104">Diese Methode ersetzt die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="38cc8-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="38cc8-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="38cc8-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
-   [<span data-ttu-id="38cc8-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="38cc8-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="38cc8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="38cc8-107">Syntax</span></span>  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38cc8-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="38cc8-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="38cc8-109">[in] Das zu übersetzende HRESULT.</span><span class="sxs-lookup"><span data-stu-id="38cc8-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="38cc8-110">[out] Die Meldungszeichenfolge, die dem angegebenen HRESULT zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="38cc8-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="38cc8-111">[in, out] Die Größe des `pwzbuffer` um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="38cc8-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="38cc8-112">Wenn `pwzbuffer` ist null, `pcchBuffer` bietet die erwartete Größe von `pwzbuffer` um die Vorabbelegung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="38cc8-113">[in] Der Kulturbezeichner.</span><span class="sxs-lookup"><span data-stu-id="38cc8-113">[in] The culture identifier.</span></span> <span data-ttu-id="38cc8-114">Um die Standardkultur verwenden zu können, müssen Sie-1 angeben.</span><span class="sxs-lookup"><span data-stu-id="38cc8-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38cc8-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="38cc8-115">Return Value</span></span>  
 <span data-ttu-id="38cc8-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="38cc8-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="38cc8-117">HRESULT</span></span>|<span data-ttu-id="38cc8-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38cc8-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="38cc8-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="38cc8-119">S_OK</span></span>|<span data-ttu-id="38cc8-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="38cc8-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="38cc8-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="38cc8-121">E_POINTER</span></span>|<span data-ttu-id="38cc8-122">`pcchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="38cc8-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="38cc8-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="38cc8-123">E_INVALIDARG</span></span>|<span data-ttu-id="38cc8-124">`pwzBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="38cc8-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38cc8-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="38cc8-125">Requirements</span></span>  
 <span data-ttu-id="38cc8-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38cc8-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38cc8-127">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="38cc8-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="38cc8-128">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="38cc8-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38cc8-129">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38cc8-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38cc8-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38cc8-130">See Also</span></span>  
 [<span data-ttu-id="38cc8-131">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="38cc8-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="38cc8-132">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="38cc8-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="38cc8-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="38cc8-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
