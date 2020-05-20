---
title: ICLRRuntimeHost::GetCLRControl-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCLRControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type:
- apiref
ms.openlocfilehash: 68bcdc33e34075cc5876ee721ef57282cdaa6e86
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703688"
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="c99f1-102">ICLRRuntimeHost::GetCLRControl-Methode</span><span class="sxs-lookup"><span data-stu-id="c99f1-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="c99f1-103">Ruft einen Schnittstellen Zeiger vom Typ [ICLRControl-Schnittstelle](iclrcontrol-interface.md) ab, mit der Hosts Aspekte des Common Language Runtime (CLR) anpassen können.</span><span class="sxs-lookup"><span data-stu-id="c99f1-103">Gets an interface pointer of type [ICLRControl Interface](iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c99f1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c99f1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c99f1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c99f1-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="c99f1-106">vorgenommen Ein Schnittstellen Zeiger vom Typ [ICLRControl-Schnittstelle](iclrcontrol-interface.md) , mit der Hosts weitere Aspekte der CLR konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="c99f1-106">[out] An interface pointer of type [ICLRControl Interface](iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c99f1-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c99f1-107">Return Value</span></span>  
  
|<span data-ttu-id="c99f1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c99f1-108">HRESULT</span></span>|<span data-ttu-id="c99f1-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c99f1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c99f1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c99f1-110">S_OK</span></span>|<span data-ttu-id="c99f1-111">`GetCLRControl`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c99f1-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="c99f1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c99f1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c99f1-113">Die CLR wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="c99f1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="c99f1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c99f1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="c99f1-115">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="c99f1-115">The call timed out.</span></span>|  
|<span data-ttu-id="c99f1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="c99f1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="c99f1-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="c99f1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="c99f1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="c99f1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="c99f1-119">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="c99f1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="c99f1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c99f1-120">E_FAIL</span></span>|<span data-ttu-id="c99f1-121">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c99f1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="c99f1-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="c99f1-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="c99f1-123">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="c99f1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c99f1-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="c99f1-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="c99f1-125">Die CLR wurde bereits gestartet.</span><span class="sxs-lookup"><span data-stu-id="c99f1-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c99f1-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c99f1-126">Remarks</span></span>  
 <span data-ttu-id="c99f1-127">`ICLRControl`stellt die [Methode GetCLRManager-Methode](iclrcontrol-getclrmanager-method.md) bereit, die es dem Host ermöglicht, einen Schnittstellen Zeiger auf einen der Manager-Typen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c99f1-127">`ICLRControl` provides the [GetCLRManager Method](iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c99f1-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c99f1-128">Requirements</span></span>  
 <span data-ttu-id="c99f1-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c99f1-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c99f1-130">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c99f1-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c99f1-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c99f1-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c99f1-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c99f1-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c99f1-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c99f1-133">See also</span></span>

- [<span data-ttu-id="c99f1-134">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c99f1-134">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="c99f1-135">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c99f1-135">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
