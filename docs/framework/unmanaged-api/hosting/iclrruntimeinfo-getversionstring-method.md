---
title: ICLRRuntimeInfo::GetVersionString-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6e320936430307dab066eecc835ac5c84bd22bc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202325"
---
# <a name="iclrruntimeinfogetversionstring-method"></a><span data-ttu-id="9eda6-102">ICLRRuntimeInfo::GetVersionString-Methode</span><span class="sxs-lookup"><span data-stu-id="9eda6-102">ICLRRuntimeInfo::GetVersionString Method</span></span>
<span data-ttu-id="9eda6-103">Ruft zur common Language Runtime (CLR) Version verknüpft ist, mit einer angegebenen [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="9eda6-103">Gets common language runtime (CLR) version information associated with a given [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="9eda6-104">Diese Methode ersetzt die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="9eda6-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="9eda6-105">GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="9eda6-105">GetRequestedRuntimeInfo</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
  
-   [<span data-ttu-id="9eda6-106">GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="9eda6-106">GetRequestedRuntimeVersion</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="9eda6-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="9eda6-107">Syntax</span></span>  
  
```  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9eda6-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="9eda6-108">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="9eda6-109">[out] Die Version des .NET Framework-Kompilierung im Format "V*ein*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="9eda6-109">[out] The .NET Framework compilation version in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="9eda6-110">*Ein*, *B*, und *X* sind Dezimalzahlen, die die Hauptversion, Nebenversion und die Nummer des Builds entsprechen.</span><span class="sxs-lookup"><span data-stu-id="9eda6-110">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="9eda6-111">*X* ist optional.</span><span class="sxs-lookup"><span data-stu-id="9eda6-111">*X* is optional.</span></span> <span data-ttu-id="9eda6-112">Wenn *X* ist nicht vorhanden ist, nicht mit einem Punkt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="9eda6-112">If *X* is not present, there is no trailing period.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9eda6-113">Dieser Parameter muss den Verzeichnisnamen für die .NET Framework-Version übereinstimmen, wie er unter C:\Windows\Microsoft.NET\Framework angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="9eda6-113">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="9eda6-114">Beispielwerte sind "Version 1.0.3705", "v1.1.4322", "v2.0.50727" und "v4. 0. *x*", wobei *x* hängt von der Nummer des Builds installiert.</span><span class="sxs-lookup"><span data-stu-id="9eda6-114">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*x*", where *x* depends on the build number installed.</span></span> <span data-ttu-id="9eda6-115">Beachten Sie, dass das Präfix "V" erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="9eda6-115">Note that the "v" prefix is mandatory.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="9eda6-116">[in, out] Gibt die Größe des `pwzBuffer` um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="9eda6-116">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="9eda6-117">Wenn `pwzBuffer` ist `null`, `pchBuffer` gibt zurück, die erforderliche Größe des `pwzBuffer` um die Vorabbelegung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9eda6-117">If `pwzBuffer` is `null`, `pchBuffer` returns the required size of `pwzBuffer` to allow preallocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9eda6-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9eda6-118">Return Value</span></span>  
 <span data-ttu-id="9eda6-119">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="9eda6-119">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9eda6-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9eda6-120">HRESULT</span></span>|<span data-ttu-id="9eda6-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9eda6-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9eda6-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="9eda6-122">S_OK</span></span>|<span data-ttu-id="9eda6-123">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="9eda6-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="9eda6-124">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="9eda6-124">E_POINTER</span></span>|<span data-ttu-id="9eda6-125">`pwzBuffer` oder `pchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="9eda6-125">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9eda6-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9eda6-126">Requirements</span></span>  
 <span data-ttu-id="9eda6-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9eda6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9eda6-128">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="9eda6-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="9eda6-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9eda6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9eda6-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9eda6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eda6-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9eda6-131">See also</span></span>

- [<span data-ttu-id="9eda6-132">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9eda6-132">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="9eda6-133">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9eda6-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="9eda6-134">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="9eda6-134">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="9eda6-135">Hosting</span><span class="sxs-lookup"><span data-stu-id="9eda6-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
