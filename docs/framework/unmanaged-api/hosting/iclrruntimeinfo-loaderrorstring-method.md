---
title: ICLRRuntimeInfo::LoadErrorString-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b485811b0e7d2f657ff2d2c1d7a2aa135e48a335
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154686"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="657e8-102">ICLRRuntimeInfo::LoadErrorString-Methode</span><span class="sxs-lookup"><span data-stu-id="657e8-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="657e8-103">Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.</span><span class="sxs-lookup"><span data-stu-id="657e8-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="657e8-104">Diese Methode ersetzt die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="657e8-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="657e8-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="657e8-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
-   [<span data-ttu-id="657e8-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="657e8-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="657e8-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="657e8-107">Syntax</span></span>  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="657e8-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="657e8-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="657e8-109">[in] Das HRESULT, um zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="657e8-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="657e8-110">[out] Die Meldungszeichenfolge, die dem angegebenen HRESULT zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="657e8-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="657e8-111">[in, out] Die Größe des `pwzbuffer` um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="657e8-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="657e8-112">Wenn `pwzbuffer` null ist, `pcchBuffer` bietet die geforderte Größe des `pwzbuffer` um die Vorabbelegung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="657e8-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="657e8-113">[in] Der Kulturbezeichner.</span><span class="sxs-lookup"><span data-stu-id="657e8-113">[in] The culture identifier.</span></span> <span data-ttu-id="657e8-114">Um die Standardkultur verwenden zu können, müssen Sie-1 angeben.</span><span class="sxs-lookup"><span data-stu-id="657e8-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="657e8-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="657e8-115">Return Value</span></span>  
 <span data-ttu-id="657e8-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="657e8-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="657e8-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="657e8-117">HRESULT</span></span>|<span data-ttu-id="657e8-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="657e8-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="657e8-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="657e8-119">S_OK</span></span>|<span data-ttu-id="657e8-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="657e8-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="657e8-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="657e8-121">E_POINTER</span></span>|<span data-ttu-id="657e8-122">`pcchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="657e8-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="657e8-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="657e8-123">E_INVALIDARG</span></span>|<span data-ttu-id="657e8-124">`pwzBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="657e8-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="657e8-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="657e8-125">Requirements</span></span>  
 <span data-ttu-id="657e8-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="657e8-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="657e8-127">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="657e8-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="657e8-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="657e8-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="657e8-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="657e8-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="657e8-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="657e8-130">See also</span></span>

- [<span data-ttu-id="657e8-131">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="657e8-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="657e8-132">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="657e8-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="657e8-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="657e8-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
