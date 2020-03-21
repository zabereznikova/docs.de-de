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
ms.openlocfilehash: e59e7695246b2c83171e77352e16464258516f8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177465"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="2df87-102">IMetaDataEmit::SetTypeDefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="2df87-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="2df87-103">Legt Features eines Typs fest, der durch einen vorherigen Aufruf von [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2df87-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2df87-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2df87-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2df87-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2df87-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="2df87-106">[in] Ein `mdTypeDef` Token, das aus dem ursprünglichen Aufruf von [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="2df87-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="2df87-107">[in] `TypeDef` Attribute.</span><span class="sxs-lookup"><span data-stu-id="2df87-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="2df87-108">Dies ist eine `CorTypeAttr` Bitmaske von Werten.</span><span class="sxs-lookup"><span data-stu-id="2df87-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="2df87-109">[in] Die `mdToken` der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="2df87-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="2df87-110">Abgerufen von einem vorherigen Aufruf von [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)oder `null`.</span><span class="sxs-lookup"><span data-stu-id="2df87-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="2df87-111">[in] Ein Array von Token für die Schnittstellen, die dieser Typ implementiert.</span><span class="sxs-lookup"><span data-stu-id="2df87-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="2df87-112">Diese `mdTypeRef` Token werden mit [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)abgerufen.</span><span class="sxs-lookup"><span data-stu-id="2df87-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="2df87-113">Das letzte Element des Arrays muss `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="2df87-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2df87-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2df87-114">Requirements</span></span>  
 <span data-ttu-id="2df87-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2df87-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2df87-116">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2df87-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2df87-117">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2df87-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2df87-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2df87-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df87-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2df87-119">See also</span></span>

- [<span data-ttu-id="2df87-120">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2df87-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2df87-121">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2df87-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
