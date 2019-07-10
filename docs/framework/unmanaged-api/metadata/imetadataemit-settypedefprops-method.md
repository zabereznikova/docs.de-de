---
title: IMetaDataEmit::SetTypeDefProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: baee8566e923f9cb31868f8aa0e379ff1dfa42fc
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777226"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="36196-102">IMetaDataEmit::SetTypeDefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="36196-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="36196-103">Legt die Funktionen eines Typs, die von einem vorherigen Aufruf von definiert [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="36196-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36196-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="36196-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36196-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="36196-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="36196-106">[in] Ein `mdTypeDef` Token abgerufen wird, aus der ursprünglichen Aufruf von [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="36196-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="36196-107">[in] `TypeDef` Attribute.</span><span class="sxs-lookup"><span data-stu-id="36196-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="36196-108">Dies ist eine Bitmaske der `CorTypeAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="36196-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="36196-109">[in] Die `mdToken` der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="36196-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="36196-110">Abgerufen aus einem vorherigen Aufruf von [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), oder `null`.</span><span class="sxs-lookup"><span data-stu-id="36196-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="36196-111">[in] Ein Array von Token für die Schnittstellen, die dieser Typ implementiert.</span><span class="sxs-lookup"><span data-stu-id="36196-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="36196-112">Diese `mdTypeRef` Token abgerufen werden, mithilfe von [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="36196-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="36196-113">Das letzte Element des Arrays muss `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="36196-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36196-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36196-114">Requirements</span></span>  
 <span data-ttu-id="36196-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36196-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36196-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="36196-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="36196-117">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="36196-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="36196-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36196-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36196-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36196-119">See also</span></span>

- [<span data-ttu-id="36196-120">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36196-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="36196-121">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36196-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
