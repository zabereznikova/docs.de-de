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
ms.openlocfilehash: 596888a8eb4a55c4cfe594b1911f17f6d32f56d2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165931"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="a43c2-102">IMetaDataEmit::SetTypeDefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="a43c2-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="a43c2-103">Legt die Funktionen eines Typs, die von einem vorherigen Aufruf von definiert [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="a43c2-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a43c2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a43c2-104">Syntax</span></span>  
  
```  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a43c2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a43c2-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="a43c2-106">[in] Ein `mdTypeDef` Token abgerufen wird, aus der ursprünglichen Aufruf von [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="a43c2-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="a43c2-107">[in] `TypeDef` Attribute.</span><span class="sxs-lookup"><span data-stu-id="a43c2-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="a43c2-108">Dies ist eine Bitmaske der `CorTypeAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="a43c2-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="a43c2-109">[in] Die `mdToken` der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="a43c2-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="a43c2-110">Abgerufen aus einem vorherigen Aufruf von [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), oder `null`.</span><span class="sxs-lookup"><span data-stu-id="a43c2-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="a43c2-111">[in] Ein Array von Token für die Schnittstellen, die dieser Typ implementiert.</span><span class="sxs-lookup"><span data-stu-id="a43c2-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="a43c2-112">Diese `mdTypeRef` Token abgerufen werden, mithilfe von [IMetaDataEmit:: DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="a43c2-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="a43c2-113">Das letzte Element des Arrays muss `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="a43c2-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a43c2-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a43c2-114">Requirements</span></span>  
 <span data-ttu-id="a43c2-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a43c2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a43c2-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a43c2-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a43c2-117">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a43c2-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a43c2-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a43c2-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a43c2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a43c2-119">See also</span></span>

- [<span data-ttu-id="a43c2-120">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a43c2-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a43c2-121">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a43c2-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
