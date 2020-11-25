---
title: ICLRRuntimeInfo::GetDefaultStartupFlags-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::GetDefaultStartupFlags method [.NET Framework hosting]
- GetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 35c2173e-3b0b-4b2a-950d-e0a01c6df052
topic_type:
- apiref
ms.openlocfilehash: 2f828a3720f7313ee9cb851c6adae78bd5ea4fe8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732090"
---
# <a name="iclrruntimeinfogetdefaultstartupflags-method"></a><span data-ttu-id="3eaf7-102">ICLRRuntimeInfo::GetDefaultStartupFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="3eaf7-102">ICLRRuntimeInfo::GetDefaultStartupFlags Method</span></span>

<span data-ttu-id="3eaf7-103">Ruft die startflags und die Host Konfigurationsdatei ab, die zum Starten der Laufzeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3eaf7-103">Gets the startup flags and host configuration file that will be used to start the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eaf7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3eaf7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDefaultStartupFlags(  
     [out]  DWORD *pdwStartupFlags,  
     [out, size_is(*pcchHostConfigFile)] LPWSTR pwzHostConfigFile,  
     [in, out]  DWORD *pcchHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3eaf7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3eaf7-105">Parameters</span></span>  

 `pdwStartupFlags`  
 <span data-ttu-id="3eaf7-106">vorgenommen Ein Zeiger auf die hoststartflags, die derzeit festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="3eaf7-106">[out] A pointer to the host startup flags that are currently set.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="3eaf7-107">vorgenommen Ein Zeiger auf den Verzeichnispfad der aktuellen Host Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="3eaf7-107">[out] A pointer to the directory path of the current host configuration file.</span></span>  
  
 `pcchHostConfigFile`  
 <span data-ttu-id="3eaf7-108">[in, out] Bei Eingabe die Größe von `pwzHostConfigFile` , um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="3eaf7-108">[in, out] On input, the size of `pwzHostConfigFile`, to avoid buffer overruns.</span></span> <span data-ttu-id="3eaf7-109">Wenn `pwzHostConfigFile` NULL ist, gibt die Methode die erforderliche Größe von `pwzHostConfigFile` für die vorab Zuordnung zurück.</span><span class="sxs-lookup"><span data-stu-id="3eaf7-109">If `pwzHostConfigFile` is null, the method returns the required size of `pwzHostConfigFile` for pre-allocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3eaf7-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3eaf7-110">Return Value</span></span>  

 <span data-ttu-id="3eaf7-111">Diese Methode gibt die folgenden spezifischen HRESULT-und HRESULT-Fehler zurück, die auf Methoden Fehler hinweisen.</span><span class="sxs-lookup"><span data-stu-id="3eaf7-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3eaf7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3eaf7-112">HRESULT</span></span>|<span data-ttu-id="3eaf7-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3eaf7-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3eaf7-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="3eaf7-114">S_OK</span></span>|<span data-ttu-id="3eaf7-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3eaf7-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3eaf7-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3eaf7-116">Remarks</span></span>  

 <span data-ttu-id="3eaf7-117">Diese Methode gibt die standardflagwerte ( `STARTUP_CONCURRENT_GC` und `NULL` ) oder die Werte zurück, die durch einen vorherigen Aufrufen der [ICLRRuntimeInfo:: SetDefaultStartupFlags-Methode](iclrruntimeinfo-setdefaultstartupflags-method.md)bereitgestellt werden, oder die Werte, die von einer der-Methoden festgelegt werden, `CorBind*` Wenn Sie an diese Laufzeit gebunden sind.</span><span class="sxs-lookup"><span data-stu-id="3eaf7-117">This method returns the default flag values (`STARTUP_CONCURRENT_GC` and `NULL`), or the values provided by a previous call to the [ICLRRuntimeInfo::SetDefaultStartupFlags method](iclrruntimeinfo-setdefaultstartupflags-method.md), or the values set by any of the `CorBind*` methods if they are bound to this runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eaf7-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3eaf7-118">Requirements</span></span>  

 <span data-ttu-id="3eaf7-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eaf7-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eaf7-120">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="3eaf7-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3eaf7-121">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3eaf7-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3eaf7-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eaf7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3eaf7-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3eaf7-123">See also</span></span>

- [<span data-ttu-id="3eaf7-124">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3eaf7-124">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="3eaf7-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3eaf7-125">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="3eaf7-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="3eaf7-126">Hosting</span></span>](index.md)
