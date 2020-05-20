---
title: ICLRPolicyManager::SetUnhandledExceptionPolicy-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
ms.openlocfilehash: 7fa02c4c79da118543117aada7d1b9cca09c4cae
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703399"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="47287-102">ICLRPolicyManager::SetUnhandledExceptionPolicy-Methode</span><span class="sxs-lookup"><span data-stu-id="47287-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="47287-103">Gibt das Verhalten der Common Language Runtime (CLR) an, wenn eine nicht behandelte Ausnahme auftritt.</span><span class="sxs-lookup"><span data-stu-id="47287-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47287-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="47287-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47287-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="47287-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="47287-106">in Einer der [eclrunlenker dexception](eclrunhandledexception-enumeration.md) -Werte, der angibt, ob das Verhalten durch die CLR oder den Host festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="47287-106">[in] One of the [EClrUnhandledException](eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47287-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="47287-107">Return Value</span></span>  
  
|<span data-ttu-id="47287-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="47287-108">HRESULT</span></span>|<span data-ttu-id="47287-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="47287-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47287-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="47287-110">S_OK</span></span>|<span data-ttu-id="47287-111">`SetUnhandledExceptionPolicy`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="47287-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="47287-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="47287-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="47287-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="47287-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="47287-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="47287-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="47287-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="47287-115">The call timed out.</span></span>|  
|<span data-ttu-id="47287-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="47287-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="47287-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="47287-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="47287-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="47287-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="47287-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="47287-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="47287-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="47287-120">E_FAIL</span></span>|<span data-ttu-id="47287-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="47287-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="47287-122">Nachdem eine Methode E_FAIL zurückgegeben hat, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="47287-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="47287-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="47287-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47287-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="47287-124">Remarks</span></span>  
 <span data-ttu-id="47287-125">Standardmäßig ist die CLR der letzte Handler für alle nicht behandelten Ausnahmen, und Ihr Standardverhalten besteht darin, den Prozess zu beenden.</span><span class="sxs-lookup"><span data-stu-id="47287-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="47287-126">Der Host kann dieses Verhalten durch Festlegen des `policy` Werts auf eHostDeterminedPolicy ändern.</span><span class="sxs-lookup"><span data-stu-id="47287-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="47287-127">Dieser Wert ermöglicht es dem Host, sein eigenes Standardverhalten zu implementieren, wie bei früheren Versionen der CLR.</span><span class="sxs-lookup"><span data-stu-id="47287-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47287-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="47287-128">Requirements</span></span>  
 <span data-ttu-id="47287-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47287-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47287-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="47287-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="47287-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="47287-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47287-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47287-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47287-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47287-133">See also</span></span>

- [<span data-ttu-id="47287-134">EClrUnhandledException-Enumeration</span><span class="sxs-lookup"><span data-stu-id="47287-134">EClrUnhandledException Enumeration</span></span>](eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="47287-135">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47287-135">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="47287-136">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47287-136">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="47287-137">IHostPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47287-137">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
