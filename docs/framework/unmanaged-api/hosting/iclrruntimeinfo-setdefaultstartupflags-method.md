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
ms.openlocfilehash: 440f2f7c542c697b3d817c988211303c60073979
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492360"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="8efc8-102">ICLRRuntimeInfo::SetDefaultStartupFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="8efc8-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="8efc8-103">Legt fest, die Startflags und die Host-Konfigurationsdatei, die verwendet wird, um die Runtime zu starten.</span><span class="sxs-lookup"><span data-stu-id="8efc8-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="8efc8-104">Diese Methode ersetzt die Verwendung der `startupFlags` Parameter in der [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) und [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) Funktionen.</span><span class="sxs-lookup"><span data-stu-id="8efc8-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8efc8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8efc8-105">Syntax</span></span>  
  
```  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8efc8-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8efc8-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="8efc8-107">[in] Die Host-Start-Flags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8efc8-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="8efc8-108">Verwenden Sie die gleichen Kennzeichen als mit der [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) und [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) Funktionen.</span><span class="sxs-lookup"><span data-stu-id="8efc8-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="8efc8-109">[in] Der Verzeichnispfad der Hostkonfigurationsdatei festlegen.</span><span class="sxs-lookup"><span data-stu-id="8efc8-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8efc8-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8efc8-110">Return Value</span></span>  
 <span data-ttu-id="8efc8-111">Diese Methode gibt zurück, die folgende spezifischen HRESULT sowie HRESULT-Fehler, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="8efc8-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8efc8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8efc8-112">HRESULT</span></span>|<span data-ttu-id="8efc8-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8efc8-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8efc8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="8efc8-114">S_OK</span></span>|<span data-ttu-id="8efc8-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8efc8-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8efc8-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8efc8-116">Remarks</span></span>  
 <span data-ttu-id="8efc8-117">Ein Multithread-Host muss Aufrufe dieser Methode synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="8efc8-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="8efc8-118">Thread A möglicherweise rufen Sie andernfalls die `SetStartupFlags` Methode auf, nachdem Thread B einen Aufruf von `SetStartupFlags` und Thread B die Laufzeit startet.</span><span class="sxs-lookup"><span data-stu-id="8efc8-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8efc8-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8efc8-119">Requirements</span></span>  
 <span data-ttu-id="8efc8-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8efc8-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8efc8-121">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8efc8-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8efc8-122">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8efc8-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8efc8-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8efc8-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8efc8-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8efc8-124">See also</span></span>
- [<span data-ttu-id="8efc8-125">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8efc8-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="8efc8-126">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="8efc8-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="8efc8-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="8efc8-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
