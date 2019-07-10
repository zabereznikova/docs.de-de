---
title: ICorRuntimeHost::Start-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ac86fdc0852c701b66986b6a304695fbdc8e755
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780396"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="0a4a3-102">ICorRuntimeHost::Start-Methode</span><span class="sxs-lookup"><span data-stu-id="0a4a3-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="0a4a3-103">Startet die common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="0a4a3-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a4a3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a4a3-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="0a4a3-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0a4a3-105">Return Value</span></span>  
  
|<span data-ttu-id="0a4a3-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0a4a3-106">HRESULT</span></span>|<span data-ttu-id="0a4a3-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a4a3-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0a4a3-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="0a4a3-108">S_OK</span></span>|<span data-ttu-id="0a4a3-109">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="0a4a3-109">The operation was successful.</span></span>|  
|<span data-ttu-id="0a4a3-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0a4a3-110">S_FALSE</span></span>|<span data-ttu-id="0a4a3-111">Der Vorgang konnte nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0a4a3-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="0a4a3-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0a4a3-112">E_FAIL</span></span>|<span data-ttu-id="0a4a3-113">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="0a4a3-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="0a4a3-114">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0a4a3-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="0a4a3-115">Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="0a4a3-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="0a4a3-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0a4a3-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0a4a3-117">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="0a4a3-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a4a3-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0a4a3-118">Remarks</span></span>  
 <span data-ttu-id="0a4a3-119">Es ist in der Regel nicht erforderlich, rufen Sie die `Start` -Methode, da die CLR automatisch bei der ersten Anforderung zum Ausführen von verwalteten Codes gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="0a4a3-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a4a3-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0a4a3-120">Requirements</span></span>  
 <span data-ttu-id="0a4a3-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a4a3-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a4a3-122">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="0a4a3-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0a4a3-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0a4a3-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0a4a3-124">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="0a4a3-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a4a3-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a4a3-125">See also</span></span>

- [<span data-ttu-id="0a4a3-126">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0a4a3-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
