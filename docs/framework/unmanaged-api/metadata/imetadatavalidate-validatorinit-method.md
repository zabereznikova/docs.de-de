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
ms.openlocfilehash: 687f33c364f9730a554a41ade1ca2b78e33ffdc5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84489701"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="472b4-102">IMetaDataValidate::ValidatorInit-Methode</span><span class="sxs-lookup"><span data-stu-id="472b4-102">IMetaDataValidate::ValidatorInit Method</span></span>
<span data-ttu-id="472b4-103">Setzt ein Flag, das den Typ des Moduls im aktuellen Metadatenbereich angibt, und registriert die angegebene Rückrufmethode für Überprüfungsfehler.</span><span class="sxs-lookup"><span data-stu-id="472b4-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="472b4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="472b4-104">Syntax</span></span>  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="472b4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="472b4-105">Parameters</span></span>  
 `dwModule`  
 <span data-ttu-id="472b4-106">in Ein Wert der [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) -Enumeration, der den Typ des Moduls im aktuellen Metadatenbereich angibt.</span><span class="sxs-lookup"><span data-stu-id="472b4-106">[in] A value of the [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="472b4-107">in Ein Zeiger auf eine [IUnknown](/cpp/atl/iunknown) -Instanz, die als Funktions Rückruf für Validierungs Fehler fungiert.</span><span class="sxs-lookup"><span data-stu-id="472b4-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="472b4-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="472b4-108">Requirements</span></span>  
 <span data-ttu-id="472b4-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="472b4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="472b4-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="472b4-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="472b4-111">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="472b4-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="472b4-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="472b4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="472b4-113">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="472b4-113">See also</span></span>

- [<span data-ttu-id="472b4-114">IMetaDataValidate-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="472b4-114">IMetaDataValidate Interface</span></span>](imetadatavalidate-interface.md)
