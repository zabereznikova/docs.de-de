---
title: IHostSecurityManager::SetThreadToken-Methode
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
ms.openlocfilehash: 7891ddc5085eedd2a9010023f119d08f101e2fa3
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803777"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a><span data-ttu-id="fa442-102">IHostSecurityManager::SetThreadToken-Methode</span><span class="sxs-lookup"><span data-stu-id="fa442-102">IHostSecurityManager::SetThreadToken Method</span></span>
<span data-ttu-id="fa442-103">Legt ein Handle für den aktuell ausgeführten Thread fest.</span><span class="sxs-lookup"><span data-stu-id="fa442-103">Sets a handle for the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa442-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa442-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fa442-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fa442-105">Parameters</span></span>  
 `hToken`  
 <span data-ttu-id="fa442-106">in Ein Handle für das Token, das für den aktuell ausgeführten Thread festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fa442-106">[in] A handle to the token to set for the currently executing thread.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fa442-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="fa442-107">Return Value</span></span>  
  
|<span data-ttu-id="fa442-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="fa442-108">HRESULT</span></span>|<span data-ttu-id="fa442-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fa442-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="fa442-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="fa442-110">S_OK</span></span>|<span data-ttu-id="fa442-111">`SetThreadToken`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fa442-111">`SetThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="fa442-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="fa442-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="fa442-113">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="fa442-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="fa442-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="fa442-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="fa442-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="fa442-115">The call timed out.</span></span>|  
|<span data-ttu-id="fa442-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="fa442-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="fa442-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="fa442-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="fa442-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="fa442-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="fa442-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="fa442-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="fa442-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="fa442-120">E_FAIL</span></span>|<span data-ttu-id="fa442-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="fa442-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="fa442-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="fa442-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="fa442-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="fa442-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa442-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa442-124">Remarks</span></span>  
 <span data-ttu-id="fa442-125">`IHostSecurityManager::SetThreadToken`verhält sich ähnlich wie die entsprechende Win32-Funktion desselben Namens, mit der Ausnahme, dass die Win32-Funktion dem Aufrufer ermöglicht, ein Handle an einen beliebigen Thread zu übergeben, während `IHostSecurityManager::SetThreadToken` ein Token nur dem aktuell ausgeführten Thread zuordnen kann.</span><span class="sxs-lookup"><span data-stu-id="fa442-125">`IHostSecurityManager::SetThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::SetThreadToken` can associate a token only with the currently executing thread.</span></span>  
  
 <span data-ttu-id="fa442-126">Der `HANDLE` Typ ist nicht com-kompatibel, d. h. seine Größe ist für ein betriebssystemspezifisch und erfordert ein benutzerdefiniertes Marshalling.</span><span class="sxs-lookup"><span data-stu-id="fa442-126">The `HANDLE` type is not COM-compliant; that is, its size is specific to an operating system and it requires custom marshaling.</span></span> <span data-ttu-id="fa442-127">Daher ist dieses Token nur für die Verwendung innerhalb des Prozesses zwischen der CLR und dem Host vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="fa442-127">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fa442-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fa442-128">Requirements</span></span>  
 <span data-ttu-id="fa442-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa442-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa442-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="fa442-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa442-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="fa442-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa442-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa442-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa442-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fa442-133">See also</span></span>

- [<span data-ttu-id="fa442-134">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa442-134">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
- [<span data-ttu-id="fa442-135">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fa442-135">IHostThreadPoolManager Interface</span></span>](ihostthreadpoolmanager-interface.md)
