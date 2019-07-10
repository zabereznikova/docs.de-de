---
title: IMetaDataEmit::SetParamProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8448de17ad974bc77021a7880b7d8576c69ae75
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750913"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="929be-102">IMetaDataEmit::SetParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="929be-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="929be-103">Legt fest oder ändert Sie Features eines Methodenparameters, die von einem vorherigen Aufruf von definiert wurde [DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="929be-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="929be-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="929be-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="929be-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="929be-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="929be-106">[in] Das Token für den Target-Parameter.</span><span class="sxs-lookup"><span data-stu-id="929be-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="929be-107">[in] Der Name des Parameters im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="929be-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="929be-108">[in] Die Flags für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="929be-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="929be-109">[in] Die ELEMENT_TYPE_ \* für den konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="929be-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="929be-110">[in] Der Konstante Wert für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="929be-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="929be-111">[in] Die Größe in Zeichen (Unicode) der `pValue`.</span><span class="sxs-lookup"><span data-stu-id="929be-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="929be-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="929be-112">Requirements</span></span>  
 <span data-ttu-id="929be-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="929be-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="929be-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="929be-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="929be-115">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="929be-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="929be-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="929be-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="929be-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="929be-117">See also</span></span>

- [<span data-ttu-id="929be-118">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="929be-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="929be-119">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="929be-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
