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
ms.openlocfilehash: 34f996f4efe9c0db4c3f0f5277e30f53e91ec47f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696790"
---
# <a name="iclrruntimeinfogetversionstring-method"></a><span data-ttu-id="5840f-102">ICLRRuntimeInfo::GetVersionString-Methode</span><span class="sxs-lookup"><span data-stu-id="5840f-102">ICLRRuntimeInfo::GetVersionString Method</span></span>

<span data-ttu-id="5840f-103">Ruft die einer bestimmten [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) -Schnittstelle zugeordneten Common Language Runtime (CLR) ab.</span><span class="sxs-lookup"><span data-stu-id="5840f-103">Gets common language runtime (CLR) version information associated with a given [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="5840f-104">Diese Methode ersetzt die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="5840f-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="5840f-105">GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="5840f-105">GetRequestedRuntimeInfo</span></span>](getrequestedruntimeinfo-function.md)  
  
- [<span data-ttu-id="5840f-106">GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="5840f-106">GetRequestedRuntimeVersion</span></span>](getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="5840f-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5840f-107">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5840f-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="5840f-108">Parameters</span></span>  

 `pwzBuffer`  
 <span data-ttu-id="5840f-109">vorgenommen Die .NET Framework Kompilierungs Version im Format "v *A*. *B*[.*X*] ".</span><span class="sxs-lookup"><span data-stu-id="5840f-109">[out] The .NET Framework compilation version in the format "v *A*.*B*[.*X*]".</span></span> <span data-ttu-id="5840f-110">*A*, *B* und *X* sind Dezimalzahlen, die der Hauptversion, der neben Version und der Buildnummer entsprechen.</span><span class="sxs-lookup"><span data-stu-id="5840f-110">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="5840f-111">*X* ist optional.</span><span class="sxs-lookup"><span data-stu-id="5840f-111">*X* is optional.</span></span> <span data-ttu-id="5840f-112">Wenn *X* nicht vorhanden ist, gibt es keinen nachfolgenden Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="5840f-112">If *X* is not present, there is no trailing period.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5840f-113">Dieser Parameter muss dem Verzeichnisnamen für die .NET Framework Version entsprechen, wie er unter "c:\WINDOWS\Microsoft.NET\Framework" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="5840f-113">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="5840f-114">Beispiel Werte sind "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" und "v 4.0". *x*", wobei *x* von der installierten Buildnummer abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="5840f-114">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*x*", where *x* depends on the build number installed.</span></span> <span data-ttu-id="5840f-115">Beachten Sie, dass das Präfix "v" obligatorisch ist.</span><span class="sxs-lookup"><span data-stu-id="5840f-115">Note that the "v" prefix is mandatory.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="5840f-116">[in, out] Gibt die Größe von `pwzBuffer` an, um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="5840f-116">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="5840f-117">Wenn `pwzBuffer` ist `null` , wird `pchBuffer` die erforderliche Größe von zurückgegeben `pwzBuffer` , um die vorab Zuordnung zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="5840f-117">If `pwzBuffer` is `null`, `pchBuffer` returns the required size of `pwzBuffer` to allow preallocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5840f-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5840f-118">Return Value</span></span>  

 <span data-ttu-id="5840f-119">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5840f-119">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5840f-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5840f-120">HRESULT</span></span>|<span data-ttu-id="5840f-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5840f-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5840f-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="5840f-122">S_OK</span></span>|<span data-ttu-id="5840f-123">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5840f-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="5840f-124">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="5840f-124">E_POINTER</span></span>|<span data-ttu-id="5840f-125">`pwzBuffer` oder `pchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="5840f-125">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5840f-126">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5840f-126">Requirements</span></span>  

 <span data-ttu-id="5840f-127">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5840f-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5840f-128">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="5840f-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5840f-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5840f-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5840f-130">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5840f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5840f-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5840f-131">See also</span></span>

- [<span data-ttu-id="5840f-132">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5840f-132">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="5840f-133">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5840f-133">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="5840f-134">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="5840f-134">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="5840f-135">Hosting</span><span class="sxs-lookup"><span data-stu-id="5840f-135">Hosting</span></span>](index.md)
