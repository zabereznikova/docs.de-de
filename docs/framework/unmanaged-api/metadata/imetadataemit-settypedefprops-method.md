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
ms.openlocfilehash: 3ab29fc8c983b354ad5088d26c547868940ec70a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447719"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="ec8a0-102">IMetaDataEmit::SetTypeDefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="ec8a0-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="ec8a0-103">Legt Funktionen eines Typs fest, der durch einen vorherigen [IMetaDataEmit::D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec8a0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec8a0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec8a0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec8a0-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="ec8a0-106">in Ein `mdTypeDef` Token, das vom ursprünglichen [IMetaDataEmit::D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="ec8a0-107">[in] `TypeDef` Attribute.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="ec8a0-108">Dies ist eine Bitmaske von `CorTypeAttr` Werten.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="ec8a0-109">in Der `mdToken` der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="ec8a0-110">Abgerufen von einem vorherigen-Befehl an [IMetaDataEmit::D efineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)oder `null`.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="ec8a0-111">in Ein Array von Token für die Schnittstellen, die von diesem Typ implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="ec8a0-112">Diese `mdTypeRef` Token werden mithilfe von [IMetaDataEmit::D efineimporttype](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="ec8a0-113">Das letzte Element des Arrays muss `mdTokenNil`werden.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec8a0-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ec8a0-114">Requirements</span></span>  
 <span data-ttu-id="ec8a0-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec8a0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec8a0-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ec8a0-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ec8a0-117">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="ec8a0-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ec8a0-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec8a0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec8a0-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec8a0-119">See also</span></span>

- [<span data-ttu-id="ec8a0-120">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec8a0-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ec8a0-121">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ec8a0-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
