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
ms.openlocfilehash: a3f52deab4d0c8ca56fae2e65912217e51abe58a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95715862"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="b60d8-102">ICLRValidator::FormatEventInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="b60d8-102">ICLRValidator::FormatEventInfo Method</span></span>

<span data-ttu-id="b60d8-103">Ruft eine ausführliche Meldung über den angegebenen Validierungs Fehler ab.</span><span class="sxs-lookup"><span data-stu-id="b60d8-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b60d8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b60d8-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b60d8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b60d8-105">Parameters</span></span>  

 `hVECode`  
 <span data-ttu-id="b60d8-106">in Der HRESULT-Wert, der an den Validierungs Fehlerhandler übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="b60d8-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="b60d8-107">in Eine- `VEContext` Instanz, die Kontextinformationen über die Validierungs Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="b60d8-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="b60d8-108">[in, out] Die Anzeige Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="b60d8-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="b60d8-109">in Die maximale Länge der Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="b60d8-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="b60d8-110">in Ein sicheres Array zusätzlicher Parameter, die in der Nachricht verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b60d8-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b60d8-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b60d8-111">Return Value</span></span>  
  
|<span data-ttu-id="b60d8-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b60d8-112">HRESULT</span></span>|<span data-ttu-id="b60d8-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b60d8-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b60d8-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="b60d8-114">S_OK</span></span>|<span data-ttu-id="b60d8-115">`FormatEventInfo` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b60d8-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="b60d8-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b60d8-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b60d8-117">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="b60d8-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b60d8-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b60d8-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b60d8-119">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="b60d8-119">The call timed out.</span></span>|  
|<span data-ttu-id="b60d8-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b60d8-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b60d8-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="b60d8-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b60d8-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b60d8-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b60d8-123">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="b60d8-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b60d8-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b60d8-124">E_FAIL</span></span>|<span data-ttu-id="b60d8-125">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b60d8-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b60d8-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="b60d8-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b60d8-127">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="b60d8-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b60d8-128">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b60d8-128">Requirements</span></span>  

 <span data-ttu-id="b60d8-129">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b60d8-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b60d8-130">**Header:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="b60d8-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="b60d8-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="b60d8-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b60d8-132">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b60d8-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b60d8-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b60d8-133">See also</span></span>

- [<span data-ttu-id="b60d8-134">ICLRErrorReportingManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b60d8-134">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="b60d8-135">ICLRValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b60d8-135">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)
