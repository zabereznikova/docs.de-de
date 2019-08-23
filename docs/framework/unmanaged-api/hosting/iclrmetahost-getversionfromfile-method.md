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
ms.openlocfilehash: dd5d2e820bd1d733bb4ab968a89174124bc91357
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962942"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="e94db-102">ICLRMetaHost::GetVersionFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="e94db-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="e94db-103">Ruft die ursprüngliche .NET Framework Kompilierungs Version einer Assembly ab (gespeichert in den Metadaten), wenn Ihr Dateipfad angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="e94db-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="e94db-104">Diese Methode löst die [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) -Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="e94db-104">This method supersedes the [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e94db-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e94db-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e94db-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="e94db-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="e94db-107">in Der vollständige assemblydateipfad.</span><span class="sxs-lookup"><span data-stu-id="e94db-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="e94db-108">vorgenommen Die in den Metadaten gespeicherte .NET Framework Kompilierungs Version im Format "v*A*. *B* [. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="e94db-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="e94db-109">*A*, *B*und *X* sind Dezimalzahlen, die der Hauptversion, der neben Version und der Buildnummer entsprechen.</span><span class="sxs-lookup"><span data-stu-id="e94db-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="e94db-110">Die Länge dieser Zeichenfolge ist auf MAX_PATH beschränkt.</span><span class="sxs-lookup"><span data-stu-id="e94db-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e94db-111">Diese Ausgabe entspricht dem Verzeichnisnamen für die .NET Framework Version, wie Sie unter "c:\WINDOWS\Microsoft.NET\Framework" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="e94db-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="e94db-112">Beispiel Werte sind "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" und "v 4.0". *X*", wobei *x* von der installierten Buildnummer abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="e94db-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="e94db-113">Beachten Sie, dass das Präfix "v" erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e94db-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="e94db-114">[in, out] Die Größe von `pwzbuffer` , um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="e94db-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e94db-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e94db-115">Return Value</span></span>  
 <span data-ttu-id="e94db-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e94db-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e94db-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e94db-117">HRESULT</span></span>|<span data-ttu-id="e94db-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e94db-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e94db-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="e94db-119">S_OK</span></span>|<span data-ttu-id="e94db-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="e94db-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="e94db-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e94db-121">E_POINTER</span></span>|<span data-ttu-id="e94db-122">`pwzbuffer` oder `pcchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="e94db-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="e94db-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="e94db-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="e94db-124">Der Puffer ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="e94db-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e94db-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e94db-125">Requirements</span></span>  
 <span data-ttu-id="e94db-126">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e94db-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e94db-127">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e94db-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e94db-128">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e94db-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e94db-129">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e94db-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e94db-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e94db-130">See also</span></span>

- [<span data-ttu-id="e94db-131">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e94db-131">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="e94db-132">Hosting</span><span class="sxs-lookup"><span data-stu-id="e94db-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
