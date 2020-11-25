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
ms.openlocfilehash: e2f54e11906cd4ba1440e220530f2ca5b9de769f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708555"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="27b5b-102">IMetaDataValidate::ValidatorInit-Methode</span><span class="sxs-lookup"><span data-stu-id="27b5b-102">IMetaDataValidate::ValidatorInit Method</span></span>

<span data-ttu-id="27b5b-103">Setzt ein Flag, das den Typ des Moduls im aktuellen Metadatenbereich angibt, und registriert die angegebene Rückrufmethode für Überprüfungsfehler.</span><span class="sxs-lookup"><span data-stu-id="27b5b-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27b5b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="27b5b-104">Syntax</span></span>  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27b5b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="27b5b-105">Parameters</span></span>  

 `dwModule`  
 <span data-ttu-id="27b5b-106">in Ein Wert der [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) -Enumeration, der den Typ des Moduls im aktuellen Metadatenbereich angibt.</span><span class="sxs-lookup"><span data-stu-id="27b5b-106">[in] A value of the [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="27b5b-107">in Ein Zeiger auf eine [IUnknown](/cpp/atl/iunknown) -Instanz, die als Funktions Rückruf für Validierungs Fehler fungiert.</span><span class="sxs-lookup"><span data-stu-id="27b5b-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27b5b-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="27b5b-108">Requirements</span></span>  

 <span data-ttu-id="27b5b-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27b5b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27b5b-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="27b5b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27b5b-111">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="27b5b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27b5b-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27b5b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27b5b-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="27b5b-113">See also</span></span>

- [<span data-ttu-id="27b5b-114">IMetaDataValidate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="27b5b-114">IMetaDataValidate Interface</span></span>](imetadatavalidate-interface.md)
