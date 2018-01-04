---
title: IMetaDataEmit::SetTypeDefProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetTypeDefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a03b781865b55b832b34bfdab7c88ce33f4e9e12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="2268b-102">IMetaDataEmit::SetTypeDefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="2268b-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="2268b-103">Legt die Funktionen eines Typs, der durch einen vorherigen Aufruf von definiert [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="2268b-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2268b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2268b-104">Syntax</span></span>  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2268b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2268b-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="2268b-106">[in] Ein `mdTypeDef` Token abgerufen wird, aus der ursprünglichen Aufruf von [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="2268b-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="2268b-107">[in] `TypeDef` Attribute.</span><span class="sxs-lookup"><span data-stu-id="2268b-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="2268b-108">Dies ist eine Bitmaske der `CorTypeAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="2268b-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="2268b-109">[in] Die `mdToken` der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="2268b-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="2268b-110">Von einem vorherigen Aufruf abgerufen [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), oder `null`.</span><span class="sxs-lookup"><span data-stu-id="2268b-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="2268b-111">[in] Ein Array von Token für die Schnittstellen, die dieser Typ implementiert.</span><span class="sxs-lookup"><span data-stu-id="2268b-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="2268b-112">Diese `mdTypeRef` mit Token erhalten [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="2268b-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="2268b-113">Ist das letzte Element des Arrays muss `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="2268b-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2268b-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2268b-114">Requirements</span></span>  
 <span data-ttu-id="2268b-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2268b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2268b-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2268b-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2268b-117">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2268b-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2268b-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2268b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2268b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2268b-119">See Also</span></span>  
 [<span data-ttu-id="2268b-120">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2268b-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="2268b-121">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2268b-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
