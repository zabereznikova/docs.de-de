---
title: IMetaDataValidate::ValidatorInit-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataValidate.ValidatorInit
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 26f5f6626766d7341ef5c8b2ecbe5e56a17eafdd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="a9dc8-102">IMetaDataValidate::ValidatorInit-Methode</span><span class="sxs-lookup"><span data-stu-id="a9dc8-102">IMetaDataValidate::ValidatorInit Method</span></span>
<span data-ttu-id="a9dc8-103">Setzt ein Flag, das den Typ des Moduls im aktuellen Metadatenbereich angibt, und registriert die angegebene Rückrufmethode für Validierungsfehler.</span><span class="sxs-lookup"><span data-stu-id="a9dc8-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9dc8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9dc8-104">Syntax</span></span>  
  
```  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9dc8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a9dc8-105">Parameters</span></span>  
 `dwModule`  
 <span data-ttu-id="a9dc8-106">[in] Der Wert der [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) -Enumeration, der den Typ des Moduls im aktuellen Metadatenbereich angibt.</span><span class="sxs-lookup"><span data-stu-id="a9dc8-106">[in] A value of the [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="a9dc8-107">[in] Ein Zeiger auf ein <<!--zzxref:IUnknown --> `IUnknown`> Instanz, die als ein Funktionsrückruf für Validierungsfehler dient.</span><span class="sxs-lookup"><span data-stu-id="a9dc8-107">[in] A pointer to an <<!--zzxref:IUnknown --> `IUnknown`> instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9dc8-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a9dc8-108">Requirements</span></span>  
 <span data-ttu-id="a9dc8-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9dc8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9dc8-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a9dc8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9dc8-111">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a9dc8-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9dc8-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9dc8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9dc8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9dc8-113">See Also</span></span>  
 [<span data-ttu-id="a9dc8-114">IMetaDataValidate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9dc8-114">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)
