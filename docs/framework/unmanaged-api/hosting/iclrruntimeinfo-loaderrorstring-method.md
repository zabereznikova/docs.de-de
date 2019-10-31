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
ms.openlocfilehash: 20f2041599e85b8df20a7a9cf44680da9f17244e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195926"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="2fa0e-102">ICLRRuntimeInfo::LoadErrorString-Methode</span><span class="sxs-lookup"><span data-stu-id="2fa0e-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="2fa0e-103">Übersetzt einen HRESULT-Wert in eine entsprechende Fehlermeldung für die angegebene Kultur.</span><span class="sxs-lookup"><span data-stu-id="2fa0e-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="2fa0e-104">Diese Methode ersetzt die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="2fa0e-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="2fa0e-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="2fa0e-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
- [<span data-ttu-id="2fa0e-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="2fa0e-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="2fa0e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fa0e-107">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fa0e-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="2fa0e-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="2fa0e-109">in Das zu über setzende HRESULT.</span><span class="sxs-lookup"><span data-stu-id="2fa0e-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="2fa0e-110">vorgenommen Die dem angegebenen HRESULT zugeordnete Meldungs Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2fa0e-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="2fa0e-111">[in, out] Die Größe der `pwzbuffer`, um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="2fa0e-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="2fa0e-112">Wenn `pwzbuffer` NULL ist, stellt `pcchBuffer` die erwartete Größe `pwzbuffer` bereit, um die vorab Zuordnung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="2fa0e-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="2fa0e-113">in Der Kultur Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="2fa0e-113">[in] The culture identifier.</span></span> <span data-ttu-id="2fa0e-114">Wenn Sie die Standard Kultur verwenden möchten, müssen Sie-1 angeben.</span><span class="sxs-lookup"><span data-stu-id="2fa0e-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fa0e-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2fa0e-115">Return Value</span></span>  
 <span data-ttu-id="2fa0e-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2fa0e-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2fa0e-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2fa0e-117">HRESULT</span></span>|<span data-ttu-id="2fa0e-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2fa0e-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2fa0e-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="2fa0e-119">S_OK</span></span>|<span data-ttu-id="2fa0e-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2fa0e-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="2fa0e-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="2fa0e-121">E_POINTER</span></span>|<span data-ttu-id="2fa0e-122">`pcchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="2fa0e-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="2fa0e-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="2fa0e-123">E_INVALIDARG</span></span>|<span data-ttu-id="2fa0e-124">`pwzBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="2fa0e-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2fa0e-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2fa0e-125">Requirements</span></span>  
 <span data-ttu-id="2fa0e-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fa0e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fa0e-127">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="2fa0e-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2fa0e-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2fa0e-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fa0e-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fa0e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fa0e-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fa0e-130">See also</span></span>

- [<span data-ttu-id="2fa0e-131">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2fa0e-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="2fa0e-132">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2fa0e-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="2fa0e-133">Hosting</span><span class="sxs-lookup"><span data-stu-id="2fa0e-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
