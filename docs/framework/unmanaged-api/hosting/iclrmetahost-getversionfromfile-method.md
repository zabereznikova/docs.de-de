---
title: ICLRMetaHost::GetVersionFromFile-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.GetVersionFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 83bd2f3b0c1d58528624ac730756fb3bcdf4ba47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744842"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="aa77e-102">ICLRMetaHost::GetVersionFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="aa77e-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="aa77e-103">Ruft die Version einer Assembly ursprünglichen .NET Framework-Kompilierung (gespeichert in den Metadaten), Angabe des Dateipfads ab.</span><span class="sxs-lookup"><span data-stu-id="aa77e-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="aa77e-104">Diese Methode ersetzt die [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="aa77e-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa77e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa77e-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa77e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa77e-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="aa77e-107">[in] Der vollständige Pfad der Assemblydatei.</span><span class="sxs-lookup"><span data-stu-id="aa77e-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="aa77e-108">[out] In den Metadaten, in dem Format gespeichert .NET Framework-Kompilierung, Version "V*ein*. *B*[. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="aa77e-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="aa77e-109">*Ein*, *B*, und *X* sind Dezimalzahlen, die die Hauptversion, Nebenversion und die Nummer des Builds entsprechen.</span><span class="sxs-lookup"><span data-stu-id="aa77e-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="aa77e-110">Die Länge dieser Zeichenfolge ist auf MAX_PATH beschränkt.</span><span class="sxs-lookup"><span data-stu-id="aa77e-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aa77e-111">Diese Ausgabe entspricht den Verzeichnisnamen für die .NET Framework-Version an, wie er unter C:\Windows\Microsoft.NET\Framework angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="aa77e-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="aa77e-112">Beispielwerte sind "Version 1.0.3705", "v1.1.4322", "v2.0.50727" und "v4. 0. *X*", wobei *X* hängt von der Nummer des Builds installiert.</span><span class="sxs-lookup"><span data-stu-id="aa77e-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="aa77e-113">Beachten Sie, dass das Präfix "V" erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="aa77e-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="aa77e-114">[in, out] Die Größe des `pwzbuffer` um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="aa77e-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aa77e-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="aa77e-115">Return Value</span></span>  
 <span data-ttu-id="aa77e-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="aa77e-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="aa77e-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="aa77e-117">HRESULT</span></span>|<span data-ttu-id="aa77e-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="aa77e-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="aa77e-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="aa77e-119">S_OK</span></span>|<span data-ttu-id="aa77e-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="aa77e-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="aa77e-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="aa77e-121">E_POINTER</span></span>|<span data-ttu-id="aa77e-122">`pwzbuffer` oder `pcchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="aa77e-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="aa77e-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="aa77e-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="aa77e-124">Der Puffer ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="aa77e-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="aa77e-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa77e-125">Requirements</span></span>  
 <span data-ttu-id="aa77e-126">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa77e-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa77e-127">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="aa77e-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="aa77e-128">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="aa77e-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aa77e-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa77e-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa77e-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa77e-130">See also</span></span>
- [<span data-ttu-id="aa77e-131">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa77e-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="aa77e-132">Hosting</span><span class="sxs-lookup"><span data-stu-id="aa77e-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
