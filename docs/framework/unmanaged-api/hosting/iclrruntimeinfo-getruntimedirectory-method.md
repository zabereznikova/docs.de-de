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
ms.openlocfilehash: 5c09f57ad805b4ba17b4bdafd3ced533199277a0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59196683"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="51228-102">ICLRRuntimeInfo::GetRuntimeDirectory-Methode</span><span class="sxs-lookup"><span data-stu-id="51228-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="51228-103">Ruft das Installationsverzeichnis von dieser Schnittstelle zugeordnet die common Language Runtime (CLR) ab.</span><span class="sxs-lookup"><span data-stu-id="51228-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="51228-104">Diese Methode ersetzt die [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) Funktion, die in .NET Framework, Version 2.0, 3.0 und 3.5 bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="51228-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51228-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="51228-105">Syntax</span></span>  
  
```  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51228-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="51228-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="51228-107">[out] Gibt das Installationsverzeichnis der CLR zurück.</span><span class="sxs-lookup"><span data-stu-id="51228-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="51228-108">Der Installationspfad ist vollqualifiziert. z. B. "c:\windows\microsoft.net\framework\v1.0.3705\\".</span><span class="sxs-lookup"><span data-stu-id="51228-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="51228-109">[in, out] Gibt die Größe des `pwzBuffer` um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="51228-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="51228-110">Wenn `pwzBuffer` null ist, `pchBuffer` gibt zurück, die erforderliche Größe des `pwzBuffer`.</span><span class="sxs-lookup"><span data-stu-id="51228-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51228-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="51228-111">Return Value</span></span>  
 <span data-ttu-id="51228-112">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="51228-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="51228-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51228-113">HRESULT</span></span>|<span data-ttu-id="51228-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51228-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51228-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="51228-115">S_OK</span></span>|<span data-ttu-id="51228-116">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="51228-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="51228-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="51228-117">E_POINTER</span></span>|`pwzBuffer` <span data-ttu-id="51228-118">oder `pchBuffer` ist null.</span><span class="sxs-lookup"><span data-stu-id="51228-118">or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51228-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51228-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51228-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51228-120">Requirements</span></span>  
 <span data-ttu-id="51228-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51228-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51228-122">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="51228-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="51228-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="51228-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="51228-124">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="51228-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="51228-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51228-125">See also</span></span>

- [<span data-ttu-id="51228-126">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51228-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="51228-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="51228-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
