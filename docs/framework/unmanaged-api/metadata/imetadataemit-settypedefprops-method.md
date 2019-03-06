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
ms.openlocfilehash: ddb40c3265b3f42514d9dbd6f620a783089a4fad
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481176"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="666c0-102">IMetaDataEmit::SetTypeDefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="666c0-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="666c0-103">Legt die Funktionen eines Typs, die von einem vorherigen Aufruf von definiert [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="666c0-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="666c0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="666c0-104">Syntax</span></span>  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="666c0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="666c0-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="666c0-106">[in] Ein `mdTypeDef` Token abgerufen wird, aus der ursprünglichen Aufruf von [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="666c0-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="666c0-107">[in] `TypeDef` Attribute.</span><span class="sxs-lookup"><span data-stu-id="666c0-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="666c0-108">Dies ist eine Bitmaske der `CorTypeAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="666c0-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="666c0-109">[in] Die `mdToken` der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="666c0-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="666c0-110">Abgerufen aus einem vorherigen Aufruf von [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), oder `null`.</span><span class="sxs-lookup"><span data-stu-id="666c0-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="666c0-111">[in] Ein Array von Token für die Schnittstellen, die dieser Typ implementiert.</span><span class="sxs-lookup"><span data-stu-id="666c0-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="666c0-112">Diese `mdTypeRef` Token abgerufen werden, mithilfe von [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="666c0-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="666c0-113">Das letzte Element des Arrays muss `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="666c0-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="666c0-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="666c0-114">Requirements</span></span>  
 <span data-ttu-id="666c0-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="666c0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="666c0-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="666c0-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="666c0-117">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="666c0-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="666c0-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="666c0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="666c0-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="666c0-119">See also</span></span>
- [<span data-ttu-id="666c0-120">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="666c0-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="666c0-121">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="666c0-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
