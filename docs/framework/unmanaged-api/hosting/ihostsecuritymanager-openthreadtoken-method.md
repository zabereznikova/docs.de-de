---
title: IHostSecurityManager::OpenThreadToken-Methode
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.OpenThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::OpenThreadToken
helpviewer_keywords:
- IHostSecurityManager::OpenThreadToken method [.NET Framework hosting]
- OpenThreadToken method [.NET Framework hosting]
ms.assetid: d5999052-8bf0-4a9e-8621-da6284406b18
topic_type:
- apiref
ms.openlocfilehash: 30ec8cc8bbbd6d49f89cd67371c3326c0cb0df9a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680611"
---
# <a name="ihostsecuritymanageropenthreadtoken-method"></a><span data-ttu-id="45efe-102">IHostSecurityManager::OpenThreadToken-Methode</span><span class="sxs-lookup"><span data-stu-id="45efe-102">IHostSecurityManager::OpenThreadToken Method</span></span>

<span data-ttu-id="45efe-103">Öffnet das freigegebene Zugriffs Token, das dem aktuell ausgeführten Thread zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="45efe-103">Opens the discretionary access token associated with the currently executing thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45efe-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45efe-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenThreadToken (  
    [in]  DWORD    dwDesiredAccess,
    [in]  BOOL     bOpenAsSelf,
    [out] HANDLE   *phThreadToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45efe-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="45efe-105">Parameters</span></span>  

 `dwDesiredAccess`  
 <span data-ttu-id="45efe-106">in Eine Maske von Zugriffs Werten, die die angeforderten Zugriffs Typen für das Thread Token angeben.</span><span class="sxs-lookup"><span data-stu-id="45efe-106">[in] A mask of access values that specify the requested types of access to the thread token.</span></span> <span data-ttu-id="45efe-107">Diese Werte werden in der Win32- `OpenThreadToken` Funktion definiert.</span><span class="sxs-lookup"><span data-stu-id="45efe-107">These values are defined in the Win32 `OpenThreadToken` function.</span></span> <span data-ttu-id="45efe-108">Die angeforderten Zugriffs Typen werden mit der Zugriffs Steuerungs Liste (DACL) des Tokens abgestimmt, um zu bestimmen, welche Typen von Zugriff erteilt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="45efe-108">The requested access types are reconciled against the token's discretionary access control list (DACL) to determine which types of access to grant or deny.</span></span>  
  
 `bOpenAsSelf`  
 <span data-ttu-id="45efe-109">[in] `true` , um anzugeben, dass die Zugriffs Überprüfung mithilfe des Sicherheits Kontexts des Prozesses für den aufrufenden Thread durchgeführt werden soll. `false` , um anzugeben, dass die Zugriffs Überprüfung mithilfe des Sicherheits Kontexts für den aufrufenden Thread selbst durchgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="45efe-109">[in] `true` to specify that the access check should be made using the security context of the process for the calling thread; `false` to specify that the access check should be performed using the security context for the calling thread itself.</span></span> <span data-ttu-id="45efe-110">Wenn der Thread die Identität eines Clients annimmt, kann der Sicherheitskontext der eines Client Prozesses sein.</span><span class="sxs-lookup"><span data-stu-id="45efe-110">If the thread is impersonating a client, the security context can be that of a client process.</span></span>  
  
 `phThreadToken`  
 <span data-ttu-id="45efe-111">vorgenommen Ein Zeiger auf das neu geöffnete Zugriffs Token.</span><span class="sxs-lookup"><span data-stu-id="45efe-111">[out] A pointer to the newly opened access token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45efe-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="45efe-112">Return Value</span></span>  
  
|<span data-ttu-id="45efe-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="45efe-113">HRESULT</span></span>|<span data-ttu-id="45efe-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="45efe-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="45efe-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="45efe-115">S_OK</span></span>|<span data-ttu-id="45efe-116">`OpenThreadToken` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="45efe-116">`OpenThreadToken` returned successfully.</span></span>|  
|<span data-ttu-id="45efe-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="45efe-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="45efe-118">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="45efe-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="45efe-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="45efe-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="45efe-120">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="45efe-120">The call timed out.</span></span>|  
|<span data-ttu-id="45efe-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="45efe-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="45efe-122">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="45efe-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="45efe-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="45efe-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="45efe-124">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="45efe-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="45efe-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="45efe-125">E_FAIL</span></span>|<span data-ttu-id="45efe-126">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="45efe-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="45efe-127">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="45efe-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="45efe-128">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="45efe-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="45efe-129">Hinweise</span><span class="sxs-lookup"><span data-stu-id="45efe-129">Remarks</span></span>  

 <span data-ttu-id="45efe-130">`IHostSecurityManager::OpenThreadToken` verhält sich ähnlich wie die entsprechende Win32-Funktion mit dem gleichen Namen, mit der Ausnahme, dass die Win32-Funktion dem Aufrufer ermöglicht, ein Handle an einen beliebigen Thread zu übergeben, während `IHostSecurityManager::OpenThreadToken` nur das Token öffnet, das dem aufrufenden Thread zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="45efe-130">`IHostSecurityManager::OpenThreadToken` behaves similarly to the corresponding Win32 function of the same name, except that the Win32 function allows the caller to pass in a handle to an arbitrary thread, while `IHostSecurityManager::OpenThreadToken` opens only the token associated with the calling thread.</span></span>  
  
 <span data-ttu-id="45efe-131">Der `HANDLE` Typ ist nicht com-kompatibel, d. h. seine Größe ist für das betriebssystemspezifisch und erfordert ein benutzerdefiniertes Marshalling.</span><span class="sxs-lookup"><span data-stu-id="45efe-131">The `HANDLE` type is not COM-compliant, that is, its size is specific to the operating system, and it requires custom marshaling.</span></span> <span data-ttu-id="45efe-132">Daher ist dieses Token nur für die Verwendung innerhalb des Prozesses zwischen der CLR und dem Host vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="45efe-132">Thus, this token is for use only within the process, between the CLR and the host.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45efe-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="45efe-133">Requirements</span></span>  

 <span data-ttu-id="45efe-134">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45efe-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45efe-135">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="45efe-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="45efe-136">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="45efe-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45efe-137">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45efe-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45efe-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45efe-138">See also</span></span>

- [<span data-ttu-id="45efe-139">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45efe-139">IHostSecurityContext Interface</span></span>](ihostsecuritycontext-interface.md)
- [<span data-ttu-id="45efe-140">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="45efe-140">IHostSecurityManager Interface</span></span>](ihostsecuritymanager-interface.md)
