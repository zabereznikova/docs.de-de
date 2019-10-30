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
ms.openlocfilehash: b0a2e5f259fe1ee566f9cc25152b2d2a1f740bea
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120343"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="f434d-102">ICLRRuntimeInfo::GetRuntimeDirectory-Methode</span><span class="sxs-lookup"><span data-stu-id="f434d-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="f434d-103">Ruft das Installationsverzeichnis der Common Language Runtime (CLR) ab, die dieser Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f434d-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="f434d-104">Diese Methode ersetzt die [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) -Funktion, die in den .NET Framework-Versionen 2,0, 3,0 und 3,5 bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f434d-104">This method supersedes the [GetCORSystemDirectory](../../../../docs/framework/unmanaged-api/hosting/getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f434d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f434d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f434d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="f434d-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="f434d-107">vorgenommen Gibt das CLR-Installationsverzeichnis zurück.</span><span class="sxs-lookup"><span data-stu-id="f434d-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="f434d-108">Der Installationspfad ist voll qualifiziert. Beispiel: "c:\WINDOWS\Microsoft.NET\Framework\v1.0.3705\\".</span><span class="sxs-lookup"><span data-stu-id="f434d-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="f434d-109">[in, out] Gibt die Größe der `pwzBuffer` an, um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f434d-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="f434d-110">Wenn `pwzBuffer` NULL ist, gibt `pchBuffer` die erforderliche Größe `pwzBuffer`zurück.</span><span class="sxs-lookup"><span data-stu-id="f434d-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f434d-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f434d-111">Return Value</span></span>  
 <span data-ttu-id="f434d-112">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="f434d-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f434d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f434d-113">HRESULT</span></span>|<span data-ttu-id="f434d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f434d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f434d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f434d-115">S_OK</span></span>|<span data-ttu-id="f434d-116">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f434d-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="f434d-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f434d-117">E_POINTER</span></span>|<span data-ttu-id="f434d-118">`pwzBuffer` oder `pchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="f434d-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f434d-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f434d-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f434d-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f434d-120">Requirements</span></span>  
 <span data-ttu-id="f434d-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f434d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f434d-122">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="f434d-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f434d-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f434d-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f434d-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f434d-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f434d-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f434d-125">See also</span></span>

- [<span data-ttu-id="f434d-126">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f434d-126">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="f434d-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="f434d-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
