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
ms.openlocfilehash: aa02d42511a863434fef236f90afae2c5417a78d
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504016"
---
# <a name="iclrruntimeinfosetdefaultstartupflags-method"></a><span data-ttu-id="d4251-102">ICLRRuntimeInfo::SetDefaultStartupFlags-Methode</span><span class="sxs-lookup"><span data-stu-id="d4251-102">ICLRRuntimeInfo::SetDefaultStartupFlags Method</span></span>
<span data-ttu-id="d4251-103">Legt die startflags und die Host Konfigurationsdatei fest, die zum Starten der Laufzeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d4251-103">Sets the startup flags and the host configuration file that will be used to start the runtime.</span></span> <span data-ttu-id="d4251-104">Diese Methode ersetzt die Verwendung des `startupFlags` -Parameters in den [CorBindToRuntimeEx](corbindtoruntimeex-function.md) -und [CorBindToRuntimeHost](corbindtoruntimehost-function.md) -Funktionen.</span><span class="sxs-lookup"><span data-stu-id="d4251-104">This method supersedes the use of the `startupFlags` parameter in the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4251-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4251-105">Syntax</span></span>  
  
```cpp  
HRESULT SetDefaultStartupFlags(  
           [in]  DWORD dwStartupFlags,  
           [in]  LPCWSTR pwzHostConfigFile);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4251-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d4251-106">Parameters</span></span>  
 `dwStartupFlags`  
 <span data-ttu-id="d4251-107">in Die festzulegenden hoststartflags.</span><span class="sxs-lookup"><span data-stu-id="d4251-107">[in] The host startup flags to set.</span></span> <span data-ttu-id="d4251-108">Verwenden Sie die gleichen Flags wie die [CorBindToRuntimeEx](corbindtoruntimeex-function.md) -Funktion und die [CorBindToRuntimeHost](corbindtoruntimehost-function.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="d4251-108">Use the same flags as with the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) and [CorBindToRuntimeHost](corbindtoruntimehost-function.md) functions.</span></span>  
  
 `pwzHostConfigFile`  
 <span data-ttu-id="d4251-109">in Der Verzeichnispfad der festzulegenden Host Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="d4251-109">[in] The directory path of the host configuration file to set.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4251-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d4251-110">Return Value</span></span>  
 <span data-ttu-id="d4251-111">Diese Methode gibt die folgenden spezifischen HRESULT-und HRESULT-Fehler zurück, die auf Methoden Fehler hinweisen.</span><span class="sxs-lookup"><span data-stu-id="d4251-111">This method returns the following specific HRESULT as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d4251-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d4251-112">HRESULT</span></span>|<span data-ttu-id="d4251-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d4251-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d4251-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d4251-114">S_OK</span></span>|<span data-ttu-id="d4251-115">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="d4251-115">The method completed successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4251-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d4251-116">Remarks</span></span>  
 <span data-ttu-id="d4251-117">Ein Multithread-Host sollte Aufrufe dieser Methode synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="d4251-117">A multithreaded host should synchronize calls to this method.</span></span> <span data-ttu-id="d4251-118">Andernfalls ruft Thread A möglicherweise die `SetStartupFlags` -Methode auf, nachdem Thread b einen-Aufrufvorgang abgeschlossen hat `SetStartupFlags` und bevor Thread b die Laufzeit startet.</span><span class="sxs-lookup"><span data-stu-id="d4251-118">Otherwise, thread A might call the `SetStartupFlags` method after thread B completes a call to `SetStartupFlags` and before thread B starts the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4251-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d4251-119">Requirements</span></span>  
 <span data-ttu-id="d4251-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4251-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4251-121">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="d4251-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d4251-122">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d4251-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d4251-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4251-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4251-124">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="d4251-124">See also</span></span>

- [<span data-ttu-id="d4251-125">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d4251-125">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="d4251-126">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d4251-126">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="d4251-127">Hosting</span><span class="sxs-lookup"><span data-stu-id="d4251-127">Hosting</span></span>](index.md)
