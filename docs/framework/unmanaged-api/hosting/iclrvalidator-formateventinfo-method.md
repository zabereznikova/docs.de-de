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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30fca37887c17f5f0da7fd2faaba32f0e5edf235
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437364"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="a437a-102">ICLRValidator::FormatEventInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="a437a-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="a437a-103">Ruft eine ausführliche Meldung über den angegebenen Validierungsfehler ab.</span><span class="sxs-lookup"><span data-stu-id="a437a-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a437a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a437a-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a437a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a437a-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="a437a-106">[in] Der HRESULT-Wert, der an den Fehlerhandler Überprüfung übergeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a437a-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="a437a-107">[in] Ein `VEContext` -Instanz, die Kontextinformationen über die Validierungsfehler enthält.</span><span class="sxs-lookup"><span data-stu-id="a437a-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="a437a-108">[in, out] Die angezeigte Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="a437a-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="a437a-109">[in] Die maximale Länge der Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="a437a-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="a437a-110">[in] Ein sicheres Array zusätzlicher Parameter in der Nachricht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a437a-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a437a-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a437a-111">Return Value</span></span>  
  
|<span data-ttu-id="a437a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a437a-112">HRESULT</span></span>|<span data-ttu-id="a437a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a437a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a437a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="a437a-114">S_OK</span></span>|<span data-ttu-id="a437a-115">`FormatEventInfo` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a437a-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="a437a-116">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="a437a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a437a-117">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="a437a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a437a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a437a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a437a-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a437a-119">The call timed out.</span></span>|  
|<span data-ttu-id="a437a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a437a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a437a-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a437a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a437a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a437a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a437a-123">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="a437a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a437a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a437a-124">E_FAIL</span></span>|<span data-ttu-id="a437a-125">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a437a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a437a-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="a437a-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a437a-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a437a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a437a-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a437a-128">Requirements</span></span>  
 <span data-ttu-id="a437a-129">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a437a-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a437a-130">**Header:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="a437a-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="a437a-131">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a437a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a437a-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a437a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a437a-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a437a-133">See Also</span></span>  
 [<span data-ttu-id="a437a-134">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a437a-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="a437a-135">ICLRValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a437a-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
