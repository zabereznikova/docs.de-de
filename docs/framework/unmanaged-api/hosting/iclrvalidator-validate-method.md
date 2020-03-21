---
title: ICLRValidator::Validate-Methode
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
ms.openlocfilehash: 427895ffea94e6c657d775ebdeb8571070a61c6e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178066"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="f8965-102">ICLRValidator::Validate-Methode</span><span class="sxs-lookup"><span data-stu-id="f8965-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="f8965-103">Überprüft die portable ausführbare Datei (PE) oder Microsoft-Zwischensprache (MSIL) in der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="f8965-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8965-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8965-104">Syntax</span></span>  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="f8965-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f8965-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="f8965-106">[in] Ein Zeiger auf `IVEHandler` eine Instanz, die Validierungsfehler verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f8965-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="f8965-107">[in] Der Bezeichner <xref:System.AppDomain>für die aktuelle .</span><span class="sxs-lookup"><span data-stu-id="f8965-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="f8965-108">[in] Eine Kombination von [ValidatorFlags-Werten,](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) die die Art der Validierung angibt, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f8965-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="f8965-109">[in] Die maximale Anzahl von Fehlern, die vor dem Beenden der Validierung zugelassen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f8965-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="f8965-110">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="f8965-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="f8965-111">[in] Der Name der zu überprüfenden Datei.</span><span class="sxs-lookup"><span data-stu-id="f8965-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="f8965-112">[in] Ein Zeiger auf den Dateipuffer.</span><span class="sxs-lookup"><span data-stu-id="f8965-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="f8965-113">[in] Die Größe der zu überprüfenden Datei in Bytes.</span><span class="sxs-lookup"><span data-stu-id="f8965-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8965-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f8965-114">Return Value</span></span>  
  
|<span data-ttu-id="f8965-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f8965-115">HRESULT</span></span>|<span data-ttu-id="f8965-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8965-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f8965-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="f8965-117">S_OK</span></span>|<span data-ttu-id="f8965-118">`Validate`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f8965-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="f8965-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="f8965-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="f8965-120">Die Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem sie keinen verwalteten Code ausführen oder den Aufruf erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="f8965-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="f8965-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="f8965-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="f8965-122">Timeout für den Anruf.</span><span class="sxs-lookup"><span data-stu-id="f8965-122">The call timed out.</span></span>|  
|<span data-ttu-id="f8965-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="f8965-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="f8965-124">Der Aufrufer besitzt die Sperre nicht.</span><span class="sxs-lookup"><span data-stu-id="f8965-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="f8965-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="f8965-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="f8965-126">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine blockierte Faser darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="f8965-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="f8965-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f8965-127">E_FAIL</span></span>|<span data-ttu-id="f8965-128">Ein unbekannter katastrophaler Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="f8965-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="f8965-129">Wenn eine Methode E_FAIL zurückgibt, kann die CLR innerhalb des Prozesses nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f8965-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="f8965-130">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="f8965-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f8965-131">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f8965-131">Requirements</span></span>  
 <span data-ttu-id="f8965-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8965-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8965-133">**Kopfzeile:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="f8965-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="f8965-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f8965-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f8965-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8965-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8965-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f8965-136">See also</span></span>

- [<span data-ttu-id="f8965-137">ICLRValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f8965-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
