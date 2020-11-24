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
ms.openlocfilehash: 4ce50f7706583f291d2e6a141d40ab6dd3e4b3e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674384"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="d9da8-102">ICLRValidator::Validate-Methode</span><span class="sxs-lookup"><span data-stu-id="d9da8-102">ICLRValidator::Validate Method</span></span>

<span data-ttu-id="d9da8-103">Überprüft die portable ausführbare Datei (PE) oder Microsoft Intermediate Language (MSIL) in der angegebenen Datei.</span><span class="sxs-lookup"><span data-stu-id="d9da8-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9da8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9da8-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d9da8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d9da8-105">Parameters</span></span>  

 `veh`  
 <span data-ttu-id="d9da8-106">in Ein Zeiger auf eine- `IVEHandler` Instanz, die Validierungs Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="d9da8-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="d9da8-107">in Der Bezeichner für die aktuelle <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="d9da8-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="d9da8-108">in Eine Kombination aus [ValidatorFlags](validatorflags-enumeration.md) -Werten, die die Art der Überprüfung angeben, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d9da8-108">[in] A combination of [ValidatorFlags](validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="d9da8-109">in Die maximal zulässige Anzahl von Fehlern, bevor die Überprüfung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="d9da8-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="d9da8-110">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="d9da8-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="d9da8-111">in Der Name der zu validierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="d9da8-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="d9da8-112">in Ein Zeiger auf den Datei Puffer.</span><span class="sxs-lookup"><span data-stu-id="d9da8-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="d9da8-113">in Die Größe (in Bytes) der zu validierenden Datei.</span><span class="sxs-lookup"><span data-stu-id="d9da8-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9da8-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d9da8-114">Return Value</span></span>  
  
|<span data-ttu-id="d9da8-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9da8-115">HRESULT</span></span>|<span data-ttu-id="d9da8-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d9da8-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9da8-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9da8-117">S_OK</span></span>|<span data-ttu-id="d9da8-118">`Validate` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d9da8-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="d9da8-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d9da8-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d9da8-120">Der Common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR befindet sich in einem Zustand, in dem Sie verwalteten Code nicht ausführen oder den-Befehl nicht erfolgreich verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="d9da8-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d9da8-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d9da8-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d9da8-122">Timeout des Aufrufes.</span><span class="sxs-lookup"><span data-stu-id="d9da8-122">The call timed out.</span></span>|  
|<span data-ttu-id="d9da8-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d9da8-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d9da8-124">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="d9da8-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d9da8-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d9da8-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d9da8-126">Ein Ereignis wurde abgebrochen, während ein blockierter Thread oder eine Fiber darauf wartete.</span><span class="sxs-lookup"><span data-stu-id="d9da8-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d9da8-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d9da8-127">E_FAIL</span></span>|<span data-ttu-id="d9da8-128">Ein unbekannter schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="d9da8-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d9da8-129">Wenn eine Methode E_FAIL zurückgibt, ist die CLR innerhalb des Prozesses nicht mehr verwendbar.</span><span class="sxs-lookup"><span data-stu-id="d9da8-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d9da8-130">Nachfolgende Aufrufe von Hostingmethoden geben HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="d9da8-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9da8-131">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d9da8-131">Requirements</span></span>  

 <span data-ttu-id="d9da8-132">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9da8-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9da8-133">**Header:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="d9da8-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="d9da8-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d9da8-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9da8-135">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9da8-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9da8-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d9da8-136">See also</span></span>

- [<span data-ttu-id="d9da8-137">ICLRValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9da8-137">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)
