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
ms.workload: dotnet
ms.openlocfilehash: d6253844e931b7b9126b2df28c7977eaa1d92d70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="e9be6-102">ICLRRuntimeInfo::LoadErrorString-Methode</span><span class="sxs-lookup"><span data-stu-id="e9be6-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="e9be6-103">Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.</span><span class="sxs-lookup"><span data-stu-id="e9be6-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="e9be6-104">Diese Methode ersetzt die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="e9be6-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="e9be6-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="e9be6-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
-   [<span data-ttu-id="e9be6-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="e9be6-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="e9be6-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9be6-107">Syntax</span></span>  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e9be6-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9be6-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="e9be6-109">[in] Das zu übersetzende HRESULT.</span><span class="sxs-lookup"><span data-stu-id="e9be6-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="e9be6-110">[out] Die Meldungszeichenfolge, die dem angegebenen HRESULT zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e9be6-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="e9be6-111">[in, out] Die Größe des `pwzbuffer` um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e9be6-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="e9be6-112">Wenn `pwzbuffer` ist null, `pcchBuffer` bietet die erwartete Größe von `pwzbuffer` um die Vorabbelegung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e9be6-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="e9be6-113">[in] Der Kulturbezeichner.</span><span class="sxs-lookup"><span data-stu-id="e9be6-113">[in] The culture identifier.</span></span> <span data-ttu-id="e9be6-114">Um die Standardkultur verwenden zu können, müssen Sie-1 angeben.</span><span class="sxs-lookup"><span data-stu-id="e9be6-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e9be6-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e9be6-115">Return Value</span></span>  
 <span data-ttu-id="e9be6-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e9be6-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e9be6-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e9be6-117">HRESULT</span></span>|<span data-ttu-id="e9be6-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e9be6-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e9be6-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="e9be6-119">S_OK</span></span>|<span data-ttu-id="e9be6-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e9be6-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="e9be6-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e9be6-121">E_POINTER</span></span>|<span data-ttu-id="e9be6-122">`pcchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="e9be6-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="e9be6-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="e9be6-123">E_INVALIDARG</span></span>|<span data-ttu-id="e9be6-124">`pwzBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="e9be6-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e9be6-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9be6-125">Requirements</span></span>  
 <span data-ttu-id="e9be6-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9be6-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9be6-127">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e9be6-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e9be6-128">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e9be6-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9be6-129">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9be6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9be6-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9be6-130">See Also</span></span>  
 [<span data-ttu-id="e9be6-131">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9be6-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="e9be6-132">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e9be6-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="e9be6-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="e9be6-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
