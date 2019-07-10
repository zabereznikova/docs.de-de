---
title: IValidator::Validate-Methode
ms.date: 03/30/2017
api_name:
- IValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Validate
helpviewer_keywords:
- IValidator::Validate method [.NET Framework hosting]
- Validate method, IValidator interface [.NET Framework hosting]
ms.assetid: 7d68666a-fb73-4455-bebd-908d49a16abc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 840a3779ca5692787c2c352db60a29d6a4d4ba4f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768590"
---
# <a name="ivalidatorvalidate-method"></a><span data-ttu-id="9a2d7-102">IValidator::Validate-Methode</span><span class="sxs-lookup"><span data-stu-id="9a2d7-102">IValidator::Validate Method</span></span>
<span data-ttu-id="9a2d7-103">Überprüft die angegebene Datei (portable Executable) oder Microsoft intermediate Language (MSIL)-Datei.</span><span class="sxs-lookup"><span data-stu-id="9a2d7-103">Validates the specified portable executable (PE) or Microsoft intermediate language (MSIL) file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a2d7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a2d7-104">Syntax</span></span>  
  
```cpp  
HRESULT Validate (  
    [in] IVEHandler            *veh,  
    [in] IUnknown              *pAppDomain,  
    [in] unsigned long          ulFlags,  
    [in] unsigned long          ulMaxError,  
    [in] unsigned long          token,  
    [in] LPWSTR                 fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long          ulSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a2d7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9a2d7-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="9a2d7-106">[in] Ein Zeiger auf ein `IVEHandler` -Instanz, die Validierungsfehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="9a2d7-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="9a2d7-107">[in] Ein Zeiger auf die Anwendungsdomäne, in der die Datei geladen wird.</span><span class="sxs-lookup"><span data-stu-id="9a2d7-107">[in] A pointer to the application domain in which the file is loaded.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="9a2d7-108">[in] Eine bitweise Kombination von [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) Werte, der angibt, Überprüfungen, die ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a2d7-108">[in] A bitwise combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the validations that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="9a2d7-109">[in] Die maximale Anzahl von Fehlern, die vor dem Beenden der Überprüfungsprozess zulassen.</span><span class="sxs-lookup"><span data-stu-id="9a2d7-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="9a2d7-110">[in] Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a2d7-110">[in] Not used.</span></span>  
  
 `fileName`  
 <span data-ttu-id="9a2d7-111">[in] Eine Zeichenfolge, die mit dem Namen der Datei, die überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a2d7-111">[in] A string that specifies the name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="9a2d7-112">[in] Ein Zeiger auf den Speicherpuffer, die in dem die Datei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="9a2d7-112">[in] A pointer to the memory buffer in which the file is stored.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="9a2d7-113">[in] Die Größe in Bytes der Datei, die überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="9a2d7-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a2d7-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9a2d7-114">Requirements</span></span>  
 <span data-ttu-id="9a2d7-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a2d7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a2d7-116">**Header:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="9a2d7-116">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="9a2d7-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9a2d7-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a2d7-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a2d7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
