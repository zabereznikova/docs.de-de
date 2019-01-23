---
title: ICLRRuntimeInfo::GetRuntimeDirectory-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetRuntimeDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetRuntimeDirectory
helpviewer_keywords:
- GetRuntimeDirectory method [.NET Framework hosting]
- ICLRRuntimeInfo::GetRuntimeDirectory method [.NET Framework hosting]
ms.assetid: 4401546e-4d48-453f-a1fb-b2ebda54df5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 26bee605724fd69d972a7e07c6fe6be2fbcabfa3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563859"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="6ae2b-102">ICLRRuntimeInfo::GetRuntimeDirectory-Methode</span><span class="sxs-lookup"><span data-stu-id="6ae2b-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="6ae2b-103">Ruft das Installationsverzeichnis von dieser Schnittstelle zugeordnet die common Language Runtime (CLR) ab.</span><span class="sxs-lookup"><span data-stu-id="6ae2b-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="6ae2b-104">Diese Methode ersetzt die [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) Funktion, die in .NET Framework, Version 2.0, 3.0 und 3.5 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6ae2b-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ae2b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="6ae2b-105">Syntax</span></span>  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6ae2b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="6ae2b-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="6ae2b-107">[out] Gibt das Installationsverzeichnis der CLR zurück.</span><span class="sxs-lookup"><span data-stu-id="6ae2b-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="6ae2b-108">Der Installationspfad ist vollqualifiziert. z. B. "c:\windows\microsoft.net\framework\v1.0.3705\\".</span><span class="sxs-lookup"><span data-stu-id="6ae2b-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="6ae2b-109">[in, out] Gibt die Größe des `pwzBuffer` um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="6ae2b-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="6ae2b-110">Wenn `pwzBuffer` null ist, `pchBuffer` gibt zurück, die erforderliche Größe des `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="6ae2b-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6ae2b-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6ae2b-111">Return Value</span></span>  
 <span data-ttu-id="6ae2b-112">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6ae2b-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6ae2b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6ae2b-113">HRESULT</span></span>|<span data-ttu-id="6ae2b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6ae2b-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6ae2b-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ae2b-115">S_OK</span></span>|<span data-ttu-id="6ae2b-116">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="6ae2b-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="6ae2b-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6ae2b-117">E_POINTER</span></span>|<span data-ttu-id="6ae2b-118">`pwzBuffer` oder `pchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="6ae2b-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ae2b-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6ae2b-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6ae2b-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6ae2b-120">Requirements</span></span>  
 <span data-ttu-id="6ae2b-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6ae2b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6ae2b-122">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6ae2b-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6ae2b-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="6ae2b-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6ae2b-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6ae2b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ae2b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ae2b-125">See also</span></span>
- [<span data-ttu-id="6ae2b-126">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6ae2b-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="6ae2b-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="6ae2b-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
