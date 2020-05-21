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
ms.openlocfilehash: d744abf5c502e9b9510cf9fd6479149b6c2177cc
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762213"
---
# <a name="iclrruntimeinfogetruntimedirectory-method"></a><span data-ttu-id="a7544-102">ICLRRuntimeInfo::GetRuntimeDirectory-Methode</span><span class="sxs-lookup"><span data-stu-id="a7544-102">ICLRRuntimeInfo::GetRuntimeDirectory Method</span></span>
<span data-ttu-id="a7544-103">Ruft das Installationsverzeichnis der Common Language Runtime (CLR) ab, die dieser Schnittstelle zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="a7544-103">Gets the installation directory of the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="a7544-104">Diese Methode ersetzt die [GetCORSystemDirectory](getcorsystemdirectory-function.md) -Funktion, die in den .NET Framework-Versionen 2,0, 3,0 und 3,5 bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a7544-104">This method supersedes the [GetCORSystemDirectory](getcorsystemdirectory-function.md) function provided in the .NET Framework versions 2.0, 3.0, and 3.5.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7544-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7544-105">Syntax</span></span>  
  
```cpp  
HRESULT GetRuntimeDirectory(  
[out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
[in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7544-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7544-106">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="a7544-107">vorgenommen Gibt das CLR-Installationsverzeichnis zurück.</span><span class="sxs-lookup"><span data-stu-id="a7544-107">[out] Returns the CLR installation directory.</span></span> <span data-ttu-id="a7544-108">Der Installationspfad ist voll qualifiziert. Beispiel: "c:\WINDOWS\Microsoft.NET\Framework\v1.0.3705 \\ ".</span><span class="sxs-lookup"><span data-stu-id="a7544-108">The installation path is fully qualified; for example, "c:\windows\microsoft.net\framework\v1.0.3705\\".</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="a7544-109">[in, out] Gibt die Größe von `pwzBuffer` an, um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="a7544-109">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="a7544-110">Wenn `pwzBuffer` NULL ist, wird `pchBuffer` die erforderliche Größe von zurückgegeben `pwzBuffer` .</span><span class="sxs-lookup"><span data-stu-id="a7544-110">If `pwzBuffer` is null, `pchBuffer` returns the required size of `pwzBuffer`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7544-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a7544-111">Return Value</span></span>  
 <span data-ttu-id="a7544-112">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a7544-112">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a7544-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a7544-113">HRESULT</span></span>|<span data-ttu-id="a7544-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a7544-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a7544-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="a7544-115">S_OK</span></span>|<span data-ttu-id="a7544-116">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a7544-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="a7544-117">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="a7544-117">E_POINTER</span></span>|<span data-ttu-id="a7544-118">`pwzBuffer` oder `pchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="a7544-118">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7544-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a7544-119">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7544-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a7544-120">Requirements</span></span>  
 <span data-ttu-id="a7544-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7544-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7544-122">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="a7544-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a7544-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a7544-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7544-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7544-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7544-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a7544-125">See also</span></span>

- [<span data-ttu-id="a7544-126">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7544-126">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="a7544-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="a7544-127">Hosting</span></span>](index.md)
