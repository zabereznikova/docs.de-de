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
ms.openlocfilehash: 349f71691e166561d677e0ae792fa12fc5bb1fc5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624306"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="3e70a-102">ICorRuntimeHost::Start-Methode</span><span class="sxs-lookup"><span data-stu-id="3e70a-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="3e70a-103">Startet die common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="3e70a-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e70a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3e70a-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="3e70a-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3e70a-105">Return Value</span></span>  
  
|<span data-ttu-id="3e70a-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3e70a-106">HRESULT</span></span>|<span data-ttu-id="3e70a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3e70a-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3e70a-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="3e70a-108">S_OK</span></span>|<span data-ttu-id="3e70a-109">Der Vorgang war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="3e70a-109">The operation was successful.</span></span>|  
|<span data-ttu-id="3e70a-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="3e70a-110">S_FALSE</span></span>|<span data-ttu-id="3e70a-111">Der Vorgang konnte nicht abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3e70a-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="3e70a-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3e70a-112">E_FAIL</span></span>|<span data-ttu-id="3e70a-113">Ein Unbekannter, schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3e70a-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="3e70a-114">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3e70a-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="3e70a-115">Nachfolgende Aufrufe von hosting-APIs HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="3e70a-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="3e70a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3e70a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3e70a-117">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3e70a-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e70a-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3e70a-118">Remarks</span></span>  
 <span data-ttu-id="3e70a-119">Es ist in der Regel nicht erforderlich, rufen Sie die `Start` -Methode, da die CLR automatisch bei der ersten Anforderung zum Ausführen von verwalteten Codes gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="3e70a-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e70a-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3e70a-120">Requirements</span></span>  
 <span data-ttu-id="3e70a-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e70a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e70a-122">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3e70a-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e70a-123">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3e70a-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e70a-124">**.NET Framework-Versionen:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="3e70a-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e70a-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3e70a-125">See also</span></span>
- [<span data-ttu-id="3e70a-126">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3e70a-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
