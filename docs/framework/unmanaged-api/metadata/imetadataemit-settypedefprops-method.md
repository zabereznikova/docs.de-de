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
ms.openlocfilehash: 2f572f66f16ff701350fde3b05be822b9e8c78b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706827"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="14768-102">IMetaDataEmit::SetTypeDefProps-Methode</span><span class="sxs-lookup"><span data-stu-id="14768-102">IMetaDataEmit::SetTypeDefProps Method</span></span>

<span data-ttu-id="14768-103">Legt Funktionen eines Typs fest, der durch einen vorherigen [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md)definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="14768-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14768-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14768-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14768-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="14768-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="14768-106">in Ein `mdTypeDef` Token, das vom ursprünglichen-Befehl an [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md)abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="14768-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="14768-107">[in] `TypeDef` legt.</span><span class="sxs-lookup"><span data-stu-id="14768-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="14768-108">Dies ist eine Bitmaske von `CorTypeAttr` Werten.</span><span class="sxs-lookup"><span data-stu-id="14768-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="14768-109">in Der der `mdToken` Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="14768-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="14768-110">Abgerufen von einem vorherigen-Befehl an [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md)oder `null` .</span><span class="sxs-lookup"><span data-stu-id="14768-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="14768-111">in Ein Array von Token für die Schnittstellen, die von diesem Typ implementiert werden.</span><span class="sxs-lookup"><span data-stu-id="14768-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="14768-112">Diese `mdTypeRef` Token werden mithilfe von [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md)abgerufen.</span><span class="sxs-lookup"><span data-stu-id="14768-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="14768-113">Das letzte Element des Arrays muss sein `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="14768-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14768-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="14768-114">Requirements</span></span>  

 <span data-ttu-id="14768-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14768-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14768-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="14768-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="14768-117">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="14768-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14768-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14768-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14768-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14768-119">See also</span></span>

- [<span data-ttu-id="14768-120">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14768-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="14768-121">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="14768-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
