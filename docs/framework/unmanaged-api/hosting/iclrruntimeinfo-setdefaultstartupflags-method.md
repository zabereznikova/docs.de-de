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
ms.openlocfilehash: 2996acd9678557b08fcfa543ecc7648ed639b143
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67748342"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="5f6c1-102">ICLRRuntimeInfo::SetDefaultStartupFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="5f6c1-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="5f6c1-103">Legt fest, die Startflags und die Host-Konfigurationsdatei, die verwendet wird, um die Runtime zu starten.</span><span class="sxs-lookup"><span data-stu-id="5f6c1-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="5f6c1-104">Diese Methode ersetzt die Verwendung der `startupFlags` Parameter in der [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) und [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) Funktionen.</span><span class="sxs-lookup"><span data-stu-id="5f6c1-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f6c1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f6c1-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f6c1-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="5f6c1-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="5f6c1-107">[in] Die Host-Start-Flags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5f6c1-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="5f6c1-108">Verwenden Sie die gleichen Kennzeichen als mit der [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) und [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) Funktionen.</span><span class="sxs-lookup"><span data-stu-id="5f6c1-108">Use the same flags as with the [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="5f6c1-109">[in] Der Verzeichnispfad der Hostkonfigurationsdatei festlegen.</span><span class="sxs-lookup"><span data-stu-id="5f6c1-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5f6c1-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5f6c1-110">Return Value</span></span>  
 <span data-ttu-id="5f6c1-111">Diese Methode gibt zurück, die folgende spezifischen HRESULT sowie HRESULT-Fehler, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5f6c1-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5f6c1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5f6c1-112">HRESULT</span></span>|<span data-ttu-id="5f6c1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5f6c1-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5f6c1-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="5f6c1-114">S_OK</span></span>|<span data-ttu-id="5f6c1-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="5f6c1-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5f6c1-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f6c1-116">Remarks</span></span>  
 <span data-ttu-id="5f6c1-117">Ein Multithread-Host muss Aufrufe dieser Methode synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="5f6c1-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="5f6c1-118">Thread A möglicherweise rufen Sie andernfalls die `SetStartupFlags` Methode auf, nachdem Thread B einen Aufruf von `SetStartupFlags` und Thread B die Laufzeit startet.</span><span class="sxs-lookup"><span data-stu-id="5f6c1-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f6c1-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5f6c1-119">Requirements</span></span>  
 <span data-ttu-id="5f6c1-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f6c1-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f6c1-121">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="5f6c1-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5f6c1-122">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5f6c1-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f6c1-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f6c1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f6c1-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f6c1-124">See also</span></span>

- [<span data-ttu-id="5f6c1-125">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f6c1-125">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="5f6c1-126">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="5f6c1-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="5f6c1-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="5f6c1-127">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
