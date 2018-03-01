---
title: IMetaDataEmit::SetParamProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e8ada9deddf8528321797c1f9bd06b5b775ac4bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="a5d3b-102">IMetaDataEmit::SetParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="a5d3b-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="a5d3b-103">Legt fest oder ändert die Features eines Methodenparameters, die durch einen vorherigen Aufruf definiert wurde [DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="a5d3b-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5d3b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5d3b-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="a5d3b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a5d3b-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="a5d3b-106">[in] Das Token für den Target-Parameter.</span><span class="sxs-lookup"><span data-stu-id="a5d3b-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="a5d3b-107">[in] Der Name des Parameters im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="a5d3b-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="a5d3b-108">[in] Die Flags für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="a5d3b-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="a5d3b-109">[in] Der ELEMENT_TYPE_ \* für den konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="a5d3b-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="a5d3b-110">[in] Der Konstante Wert für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="a5d3b-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="a5d3b-111">[in] Die Größe in Zeichen (Unicode) der `pValue`.</span><span class="sxs-lookup"><span data-stu-id="a5d3b-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5d3b-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a5d3b-112">Requirements</span></span>  
 <span data-ttu-id="a5d3b-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5d3b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5d3b-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a5d3b-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a5d3b-115">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a5d3b-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5d3b-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5d3b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5d3b-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5d3b-117">See Also</span></span>  
 [<span data-ttu-id="a5d3b-118">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a5d3b-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="a5d3b-119">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a5d3b-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
