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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 559c265c70c199e64782ba185d4925d293d6a778
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158690"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="43751-102">ICLRValidator::Validate-Methode</span><span class="sxs-lookup"><span data-stu-id="43751-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="43751-103">Überprüft die Datei (portable Executable) oder Microsoft intermediate Language (MSIL) in der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="43751-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43751-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43751-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="43751-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="43751-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="43751-106">[in] Ein Zeiger auf ein `IVEHandler` -Instanz, die Validierungsfehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="43751-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="43751-107">[in] Der Bezeichner für die aktuelle <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="43751-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="43751-108">[in] Eine Kombination von [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) Werte, der die Art der Validierung ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="43751-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="43751-109">[in] Die maximale Anzahl von Fehlern, die vor dem Beenden der Überprüfungsprozess zulassen.</span><span class="sxs-lookup"><span data-stu-id="43751-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="43751-110">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="43751-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="43751-111">[in] Der Name der Datei, die überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="43751-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="43751-112">[in] Ein Zeiger auf den Dateipuffer.</span><span class="sxs-lookup"><span data-stu-id="43751-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="43751-113">[in] Die Größe in Bytes der Datei, die überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="43751-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43751-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="43751-114">Return Value</span></span>  
  
|<span data-ttu-id="43751-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43751-115">HRESULT</span></span>|<span data-ttu-id="43751-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="43751-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43751-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="43751-117">S_OK</span></span>|`Validate` <span data-ttu-id="43751-118">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="43751-118">returned successfully.</span></span>|  
|<span data-ttu-id="43751-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="43751-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="43751-120">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="43751-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="43751-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="43751-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="43751-122">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="43751-122">The call timed out.</span></span>|  
|<span data-ttu-id="43751-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="43751-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="43751-124">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="43751-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="43751-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="43751-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="43751-126">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="43751-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="43751-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="43751-127">E_FAIL</span></span>|<span data-ttu-id="43751-128">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="43751-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="43751-129">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="43751-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="43751-130">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="43751-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="43751-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="43751-131">Requirements</span></span>  
 <span data-ttu-id="43751-132">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43751-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43751-133">**Header:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="43751-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="43751-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="43751-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="43751-135">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="43751-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="43751-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="43751-136">See also</span></span>

- [<span data-ttu-id="43751-137">ICLRValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="43751-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
