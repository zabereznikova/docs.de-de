---
title: ICLRValidator::FormatEventInfo-Methode
ms.date: 03/30/2017
api_name:
- ICLRValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::FormatEventInfo
helpviewer_keywords:
- FormatEventInfo method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::FormatEventInfo method [.NET Framework hosting]
ms.assetid: 808e1f1d-52f4-47c4-83cc-dcf47d075219
topic_type:
- apiref
ms.openlocfilehash: 935d8e9fa3ed15be03c6cd05b1bc3c4919d0cc2b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127858"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="ce658-102">ICLRValidator::FormatEventInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="ce658-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="ce658-103">Ruft eine ausführliche Meldung über den angegebenen Validierungs Fehler ab.</span><span class="sxs-lookup"><span data-stu-id="ce658-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce658-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce658-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce658-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ce658-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="ce658-106">in Der HRESULT-Wert, der an den Validierungs Fehlerhandler übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="ce658-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="ce658-107">in Eine `VEContext`-Instanz, die Kontextinformationen über die Validierungs Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="ce658-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="ce658-108">[in, out] Die Anzeige Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="ce658-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="ce658-109">in Die maximale Länge der Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="ce658-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="ce658-110">in Ein sicheres Array zusätzlicher Parameter, die in der Nachricht verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ce658-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ce658-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ce658-111">Return Value</span></span>  
  
|<span data-ttu-id="ce658-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce658-112">HRESULT</span></span>|<span data-ttu-id="ce658-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce658-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce658-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce658-114">S_OK</span></span>|<span data-ttu-id="ce658-115">`FormatEventInfo` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ce658-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="ce658-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ce658-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ce658-117">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="ce658-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ce658-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ce658-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ce658-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="ce658-119">The call timed out.</span></span>|  
|<span data-ttu-id="ce658-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce658-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ce658-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ce658-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ce658-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ce658-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ce658-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="ce658-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ce658-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ce658-124">E_FAIL</span></span>|<span data-ttu-id="ce658-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ce658-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ce658-126">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ce658-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ce658-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ce658-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ce658-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ce658-128">Requirements</span></span>  
 <span data-ttu-id="ce658-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce658-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce658-130">**Header:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="ce658-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="ce658-131">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ce658-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce658-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce658-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce658-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce658-133">See also</span></span>

- [<span data-ttu-id="ce658-134">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce658-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="ce658-135">ICLRValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce658-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
