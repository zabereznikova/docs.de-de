---
title: ICLRRuntimeInfo::SetDefaultStartupFlags-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.SetDefaultStartupFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags
helpviewer_keywords:
- ICLRRuntimeInfo::SetDefaultStartupFlags method [.NET Framework hosting]
- SetDefaultStartupFlags method [.NET Framework hosting]
ms.assetid: 98ae174f-bff0-48f1-9e05-6cb63b451824
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d3174cf3b4f4f4ac4b2c8e69030357eb1e46cf3c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197827"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="74525-102">ICLRRuntimeInfo::SetDefaultStartupFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="74525-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="74525-103">Legt fest, die Startflags und die Host-Konfigurationsdatei, die verwendet wird, um die Runtime zu starten.</span><span class="sxs-lookup"><span data-stu-id="74525-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="74525-104">Diese Methode ersetzt die Verwendung der `startupFlags` Parameter in der [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) und [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) Funktionen.</span><span class="sxs-lookup"><span data-stu-id="74525-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74525-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="74525-105">Syntax</span></span>  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="74525-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="74525-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="74525-107">[in] Die Host-Start-Flags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="74525-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="74525-108">Verwenden Sie die gleichen Kennzeichen als mit der [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) und [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) Funktionen.</span><span class="sxs-lookup"><span data-stu-id="74525-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="74525-109">[in] Der Verzeichnispfad der Hostkonfigurationsdatei festlegen.</span><span class="sxs-lookup"><span data-stu-id="74525-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="74525-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="74525-110">Return Value</span></span>  
 <span data-ttu-id="74525-111">Diese Methode gibt zurück, die folgende spezifischen HRESULT sowie HRESULT-Fehler, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="74525-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="74525-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="74525-112">HRESULT</span></span>|<span data-ttu-id="74525-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="74525-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="74525-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="74525-114">S_OK</span></span>|<span data-ttu-id="74525-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="74525-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="74525-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="74525-116">Remarks</span></span>  
 <span data-ttu-id="74525-117">Ein Multithread-Host muss Aufrufe dieser Methode synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="74525-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="74525-118">Thread A möglicherweise rufen Sie andernfalls die `SetStartupFlags` Methode auf, nachdem Thread B einen Aufruf von `SetStartupFlags` und Thread B die Laufzeit startet.</span><span class="sxs-lookup"><span data-stu-id="74525-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74525-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="74525-119">Requirements</span></span>  
 <span data-ttu-id="74525-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74525-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74525-121">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="74525-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="74525-122">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="74525-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="74525-123">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="74525-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="74525-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="74525-124">See also</span></span>

- [<span data-ttu-id="74525-125">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="74525-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="74525-126">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="74525-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="74525-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="74525-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
