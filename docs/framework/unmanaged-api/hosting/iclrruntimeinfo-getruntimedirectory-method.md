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
ms.openlocfilehash: 24679118e4255282f7da3ff8be2ce9c08250e181
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732046"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="2b170-102">ICLRRuntimeInfo::GetRuntimeDirectory-Methode</span><span class="sxs-lookup"><span data-stu-id="2b170-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>

<span data-ttu-id="2b170-103">Ruft das Installationsverzeichnis der Common Language Runtime (CLR) ab, die dieser Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="2b170-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="2b170-104">Diese Methode ersetzt die [GetCORSystemDirectory](getcorsystemdirectory-function.md) -Funktion, die in den .NET Framework-Versionen 2,0, 3,0 und 3,5 bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2b170-104">This method supersedes the [GetCORSystemDirectory](getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b170-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b170-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b170-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b170-106">Parameters</span></span>  

 `pwzBuffer`  
 <span data-ttu-id="2b170-107">vorgenommen Gibt das CLR-Installationsverzeichnis zurück.</span><span class="sxs-lookup"><span data-stu-id="2b170-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="2b170-108">Der Installationspfad ist voll qualifiziert. Beispiel: "c:\WINDOWS\Microsoft.NET\Framework\v1.0.3705 \\ ".</span><span class="sxs-lookup"><span data-stu-id="2b170-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="2b170-109">[in, out] Gibt die Größe von `pwzBuffer` an, um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="2b170-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="2b170-110">Wenn `pwzBuffer` NULL ist, wird `pchBuffer` die erforderliche Größe von zurückgegeben `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="2b170-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b170-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2b170-111">Return Value</span></span>  

 <span data-ttu-id="2b170-112">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2b170-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="2b170-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b170-113">HRESULT</span></span>|<span data-ttu-id="2b170-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2b170-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b170-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b170-115">S_OK</span></span>|<span data-ttu-id="2b170-116">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="2b170-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="2b170-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="2b170-117">E_POINTER</span></span>|<span data-ttu-id="2b170-118">`pwzBuffer` oder `pchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="2b170-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2b170-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2b170-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b170-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2b170-120">Requirements</span></span>  

 <span data-ttu-id="2b170-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b170-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b170-122">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="2b170-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="2b170-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2b170-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b170-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b170-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b170-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b170-125">See also</span></span>

- [<span data-ttu-id="2b170-126">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b170-126">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="2b170-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="2b170-127">Hosting</span></span>](index.md)
