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
ms.openlocfilehash: b2885d89883ab6312c2ad9d3feac405eef2fbede
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693690"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="163e0-102">IMetaDataEmit::SetParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="163e0-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="163e0-103">Legt fest oder ändert Sie Features eines Methodenparameters, die von einem vorherigen Aufruf von definiert wurde [DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="163e0-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="163e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="163e0-104">Syntax</span></span>  
  
```  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="163e0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="163e0-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="163e0-106">[in] Das Token für den Target-Parameter.</span><span class="sxs-lookup"><span data-stu-id="163e0-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="163e0-107">[in] Der Name des Parameters im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="163e0-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="163e0-108">[in] Die Flags für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="163e0-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="163e0-109">[in] Die ELEMENT_TYPE_ \* für den konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="163e0-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="163e0-110">[in] Der Konstante Wert für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="163e0-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="163e0-111">[in] Die Größe in Zeichen (Unicode) der `pValue`.</span><span class="sxs-lookup"><span data-stu-id="163e0-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="163e0-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="163e0-112">Requirements</span></span>  
 <span data-ttu-id="163e0-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="163e0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="163e0-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="163e0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="163e0-115">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="163e0-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="163e0-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="163e0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="163e0-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="163e0-117">See also</span></span>
- [<span data-ttu-id="163e0-118">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="163e0-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="163e0-119">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="163e0-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
