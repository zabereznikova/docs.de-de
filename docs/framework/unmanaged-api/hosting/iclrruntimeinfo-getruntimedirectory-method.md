---
title: ICLRRuntimeInfo::GetRuntimeDirectory-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetRuntimeDirectory
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ddaca8232f0b262377c7915852da89cecec09993
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="fbc8e-102">ICLRRuntimeInfo::GetRuntimeDirectory-Methode</span><span class="sxs-lookup"><span data-stu-id="fbc8e-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="fbc8e-103">Ruft das Installationsverzeichnis für die common Language Runtime (CLR), das diese Schnittstelle zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="fbc8e-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="fbc8e-104">Diese Methode hat Vorrang vor den [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) Funktion, die in .NET Framework, Version 2.0, 3.0 und 3.5 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fbc8e-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbc8e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fbc8e-105">Syntax</span></span>  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fbc8e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fbc8e-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="fbc8e-107">[out] Gibt das Installationsverzeichnis der CLR zurück.</span><span class="sxs-lookup"><span data-stu-id="fbc8e-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="fbc8e-108">Der Installationspfad ist vollqualifizierte; z. B. "c:\windows\microsoft.net\framework\v1.0.3705\\".</span><span class="sxs-lookup"><span data-stu-id="fbc8e-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="fbc8e-109">[in, out] Gibt die Größe des `pwzBuffer` um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="fbc8e-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="fbc8e-110">Wenn `pwzBuffer` ist null, `pchBuffer` gibt die erforderliche Größe des `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="fbc8e-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fbc8e-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fbc8e-111">Return Value</span></span>  
 <span data-ttu-id="fbc8e-112">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="fbc8e-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="fbc8e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fbc8e-113">HRESULT</span></span>|<span data-ttu-id="fbc8e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fbc8e-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fbc8e-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="fbc8e-115">S_OK</span></span>|<span data-ttu-id="fbc8e-116">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="fbc8e-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="fbc8e-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="fbc8e-117">E_POINTER</span></span>|<span data-ttu-id="fbc8e-118">`pwzBuffer` oder `pchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="fbc8e-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbc8e-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fbc8e-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbc8e-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fbc8e-120">Requirements</span></span>  
 <span data-ttu-id="fbc8e-121">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbc8e-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbc8e-122">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="fbc8e-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="fbc8e-123">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fbc8e-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbc8e-124">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbc8e-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbc8e-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fbc8e-125">See Also</span></span>  
 [<span data-ttu-id="fbc8e-126">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fbc8e-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="fbc8e-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="fbc8e-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
