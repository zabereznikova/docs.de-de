---
title: IMetaDataValidate::ValidatorInit-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 053c94bc540b130510f155506b6fad32f032a475
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449545"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="a55bf-102">IMetaDataValidate::ValidatorInit-Methode</span><span class="sxs-lookup"><span data-stu-id="a55bf-102">IMetaDataValidate::ValidatorInit Method</span></span>
<span data-ttu-id="a55bf-103">Setzt ein Flag, das den Typ des Moduls im aktuellen Metadatenbereich angibt, und registriert die angegebene Rückrufmethode für Validierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="a55bf-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a55bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a55bf-104">Syntax</span></span>  
  
```  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a55bf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a55bf-105">Parameters</span></span>  
 `dwModule`  
 <span data-ttu-id="a55bf-106">[in] Der Wert der [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) -Enumeration, der den Typ des Moduls im aktuellen Metadatenbereich angibt.</span><span class="sxs-lookup"><span data-stu-id="a55bf-106">[in] A value of the [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="a55bf-107">[in] Ein Zeiger auf ein <<!--zzxref:IUnknown --> `IUnknown`> Instanz, die als ein Funktionsrückruf für Validierungsfehler dient.</span><span class="sxs-lookup"><span data-stu-id="a55bf-107">[in] A pointer to an <<!--zzxref:IUnknown --> `IUnknown`> instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a55bf-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a55bf-108">Requirements</span></span>  
 <span data-ttu-id="a55bf-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a55bf-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a55bf-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a55bf-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a55bf-111">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a55bf-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a55bf-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a55bf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a55bf-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a55bf-113">See Also</span></span>  
 [<span data-ttu-id="a55bf-114">IMetaDataValidate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a55bf-114">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)
