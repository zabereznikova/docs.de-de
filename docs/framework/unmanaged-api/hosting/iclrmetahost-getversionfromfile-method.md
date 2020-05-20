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
ms.openlocfilehash: 40efc256dde13d645d43f50bb574d73b5668919c
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703739"
---
# <a name="iclrmetahostgetversionfromfile-method"></a><span data-ttu-id="a7b11-102">ICLRMetaHost::GetVersionFromFile-Methode</span><span class="sxs-lookup"><span data-stu-id="a7b11-102">ICLRMetaHost::GetVersionFromFile Method</span></span>
<span data-ttu-id="a7b11-103">Ruft die ursprüngliche .NET Framework Kompilierungs Version einer Assembly ab (gespeichert in den Metadaten), wenn Ihr Dateipfad angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="a7b11-103">Gets an assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="a7b11-104">Diese Methode löst die [GetFileVersion](getfileversion-function.md) -Funktion aus.</span><span class="sxs-lookup"><span data-stu-id="a7b11-104">This method supersedes the [GetFileVersion](getfileversion-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7b11-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a7b11-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7b11-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a7b11-106">Parameters</span></span>  
 `pwzFilePath`  
 <span data-ttu-id="a7b11-107">in Der vollständige assemblydateipfad.</span><span class="sxs-lookup"><span data-stu-id="a7b11-107">[in] The complete assembly file path.</span></span>  
  
 `pwzbuffer`  
 <span data-ttu-id="a7b11-108">vorgenommen Die in den Metadaten gespeicherte .NET Framework Kompilierungs Version im Format "v*A*. *B*[.\* X\*] ".</span><span class="sxs-lookup"><span data-stu-id="a7b11-108">[out] The .NET Framework compilation version stored in the metadata, in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="a7b11-109">*A*, *B*und *X* sind Dezimalzahlen, die der Hauptversion, der neben Version und der Buildnummer entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a7b11-109">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="a7b11-110">Die Länge dieser Zeichenfolge ist auf MAX_PATH beschränkt.</span><span class="sxs-lookup"><span data-stu-id="a7b11-110">The length of this string is limited to MAX_PATH.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a7b11-111">Diese Ausgabe entspricht dem Verzeichnisnamen für die .NET Framework Version, wie Sie unter "c:\WINDOWS\Microsoft.NET\Framework" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="a7b11-111">This output matches the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="a7b11-112">Beispiel Werte sind "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" und "v 4.0". *X*", wobei *x* von der installierten Buildnummer abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="a7b11-112">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*X*", where *X* depends on the build number installed.</span></span> <span data-ttu-id="a7b11-113">Beachten Sie, dass das Präfix "v" erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a7b11-113">Note that the "v" prefix is required.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="a7b11-114">[in, out] Die Größe von `pwzbuffer` , um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="a7b11-114">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7b11-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a7b11-115">Return Value</span></span>  
 <span data-ttu-id="a7b11-116">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a7b11-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a7b11-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a7b11-117">HRESULT</span></span>|<span data-ttu-id="a7b11-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a7b11-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a7b11-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="a7b11-119">S_OK</span></span>|<span data-ttu-id="a7b11-120">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a7b11-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="a7b11-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="a7b11-121">E_POINTER</span></span>|<span data-ttu-id="a7b11-122">`pwzbuffer` oder `pcchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="a7b11-122">`pwzbuffer` or `pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="a7b11-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="a7b11-123">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="a7b11-124">Der Puffer ist zu klein.</span><span class="sxs-lookup"><span data-stu-id="a7b11-124">The buffer is too small.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7b11-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7b11-125">Requirements</span></span>  
 <span data-ttu-id="a7b11-126">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7b11-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7b11-127">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="a7b11-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a7b11-128">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a7b11-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7b11-129">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7b11-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7b11-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7b11-130">See also</span></span>

- [<span data-ttu-id="a7b11-131">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7b11-131">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="a7b11-132">Hosting</span><span class="sxs-lookup"><span data-stu-id="a7b11-132">Hosting</span></span>](index.md)
