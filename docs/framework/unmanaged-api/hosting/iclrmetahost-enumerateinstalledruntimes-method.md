---
title: ICLRMetaHost::EnumerateInstalledRuntimes-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 900ad908229b7881dfa9ba55732e20926c912d7c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469078"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="bf544-102">ICLRMetaHost::EnumerateInstalledRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="bf544-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="bf544-103">Gibt eine Enumeration, die eine gültige enthält [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstelle für jede Version von die common Language Runtime (CLR), die auf einem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="bf544-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf544-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf544-104">Syntax</span></span>  
  
```  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf544-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bf544-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="bf544-106">[out] Eine Enumeration von [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) Schnittstellen, die für jede Version der CLR, die auf dem Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="bf544-106">[out] An enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bf544-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bf544-107">Return Value</span></span>  
 <span data-ttu-id="bf544-108">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bf544-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="bf544-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bf544-109">HRESULT</span></span>|<span data-ttu-id="bf544-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bf544-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bf544-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="bf544-111">S_OK</span></span>|<span data-ttu-id="bf544-112">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="bf544-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="bf544-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="bf544-113">E_POINTER</span></span>|<span data-ttu-id="bf544-114">`ppEnumerator` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="bf544-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bf544-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bf544-115">Requirements</span></span>  
 <span data-ttu-id="bf544-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf544-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf544-117">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="bf544-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bf544-118">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="bf544-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bf544-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf544-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf544-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bf544-120">See also</span></span>
- [<span data-ttu-id="bf544-121">ICLRMetaHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bf544-121">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="bf544-122">Hosting</span><span class="sxs-lookup"><span data-stu-id="bf544-122">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
