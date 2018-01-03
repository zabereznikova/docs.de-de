---
title: ICLRMetaHost::GetVersionFromFile-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.GetVersionFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 61e6cd1c83cc369e06099c72a6012eb448d6d37a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="82cc6-102">ICLRMetaHost::GetVersionFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="82cc6-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="82cc6-103">Ruft eine Assembly .NET Framework Kompilierung Originalversion (in den Metadaten gespeichert), bei Angabe des Dateipfads ab.</span><span class="sxs-lookup"><span data-stu-id="82cc6-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="82cc6-104">Diese Methode hat Vorrang vor den [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="82cc6-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82cc6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="82cc6-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="82cc6-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="82cc6-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="82cc6-107">[in] Der vollständige Pfad der Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="82cc6-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="82cc6-108">[out] Version von .NET Framework Kompilierung gespeichert, die in den Metadaten, im Format "V*ein*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="82cc6-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="82cc6-109">*Ein*, *B*, und *X* sind Dezimalzahlen, die die Hauptversion, die Nebenversion und die Nummer des Builds entsprechen.</span><span class="sxs-lookup"><span data-stu-id="82cc6-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="82cc6-110">Die Länge dieser Zeichenfolge ist auf MAX_PATH beschränkt.</span><span class="sxs-lookup"><span data-stu-id="82cc6-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82cc6-111">Diese Ausgabe entspricht den Verzeichnisnamen für die .NET Framework-Version an, wie er unter C:\Windows\Microsoft.NET\Framework angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="82cc6-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="82cc6-112">Beispielwerte sind "Version 1.0.3705", "v1.1.4322", "v2.0.50727" und "v4. 0. *X*", wobei *X* richtet sich nach die Buildnummer installiert.</span><span class="sxs-lookup"><span data-stu-id="82cc6-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="82cc6-113">Beachten Sie, dass das Präfix "V" erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="82cc6-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="82cc6-114">[in, out] Die Größe des `pwzbuffer` um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="82cc6-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82cc6-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="82cc6-115">Return Value</span></span>  
 <span data-ttu-id="82cc6-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="82cc6-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="82cc6-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="82cc6-117">HRESULT</span></span>|<span data-ttu-id="82cc6-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="82cc6-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="82cc6-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="82cc6-119">S_OK</span></span>|<span data-ttu-id="82cc6-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="82cc6-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="82cc6-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="82cc6-121">E_POINTER</span></span>|<span data-ttu-id="82cc6-122">`pwzbuffer` oder `pcchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="82cc6-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="82cc6-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="82cc6-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="82cc6-124">Der Puffer ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="82cc6-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="82cc6-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="82cc6-125">Requirements</span></span>  
 <span data-ttu-id="82cc6-126">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="82cc6-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82cc6-127">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="82cc6-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="82cc6-128">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="82cc6-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82cc6-129">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82cc6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82cc6-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="82cc6-130">See Also</span></span>  
 [<span data-ttu-id="82cc6-131">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="82cc6-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="82cc6-132">Hosting</span><span class="sxs-lookup"><span data-stu-id="82cc6-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
