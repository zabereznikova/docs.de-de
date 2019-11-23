---
title: IMetaDataImport::FindMember-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.FindMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::FindMember
helpviewer_keywords:
- IMetaDataImport::FindMember method [.NET Framework metadata]
- FindMember method [.NET Framework metadata]
ms.assetid: ad32fb84-c2b6-41cd-888d-787ff3a90449
topic_type:
- apiref
ms.openlocfilehash: 7a46fa5319a1badc0cf28dcdbf535a6ed017c9c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437916"
---
# <a name="imetadataimportfindmember-method"></a><span data-ttu-id="07359-102">IMetaDataImport::FindMember-Methode</span><span class="sxs-lookup"><span data-stu-id="07359-102">IMetaDataImport::FindMember Method</span></span>
<span data-ttu-id="07359-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span><span class="sxs-lookup"><span data-stu-id="07359-103">Gets a pointer to the MemberDef token for field or method that is enclosed by the specified <xref:System.Type> and that has the specified name and metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07359-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07359-104">Syntax</span></span>  
  
```cpp  
HRESULT FindMember (  
   [in]  mdTypeDef         td,  
   [in]  LPCWSTR           szName,   
   [in]  PCCOR_SIGNATURE   pvSigBlob,   
   [in]  ULONG             cbSigBlob,   
   [out] mdToken           *pmb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07359-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="07359-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="07359-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span><span class="sxs-lookup"><span data-stu-id="07359-106">[in] The TypeDef token for the class or interface that encloses the member to search for.</span></span> <span data-ttu-id="07359-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span><span class="sxs-lookup"><span data-stu-id="07359-107">If this value is `mdTokenNil`, the lookup is done for a global-variable or global-function.</span></span>  
  
 `szName`  
 <span data-ttu-id="07359-108">[in] The name of the member to search for.</span><span class="sxs-lookup"><span data-stu-id="07359-108">[in] The name of the member to search for.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="07359-109">[in] A pointer to the binary metadata signature of the member.</span><span class="sxs-lookup"><span data-stu-id="07359-109">[in] A pointer to the binary metadata signature of the member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="07359-110">[in] The size in bytes of `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="07359-110">[in] The size in bytes of `pvSigBlob`.</span></span>  
  
 `pmb`  
 <span data-ttu-id="07359-111">[out] A pointer to the matching MemberDef token.</span><span class="sxs-lookup"><span data-stu-id="07359-111">[out] A pointer to the matching MemberDef token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07359-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07359-112">Remarks</span></span>  
 <span data-ttu-id="07359-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span><span class="sxs-lookup"><span data-stu-id="07359-113">You specify the member using its enclosing class or interface (`td`), its name (`szName`), and optionally its signature (`pvSigBlob`).</span></span> <span data-ttu-id="07359-114">There might be multiple members with the same name in a class or interface.</span><span class="sxs-lookup"><span data-stu-id="07359-114">There might be multiple members with the same name in a class or interface.</span></span> <span data-ttu-id="07359-115">In that case, pass the member's signature to find the unique match.</span><span class="sxs-lookup"><span data-stu-id="07359-115">In that case, pass the member's signature to find the unique match.</span></span>  
  
 <span data-ttu-id="07359-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span><span class="sxs-lookup"><span data-stu-id="07359-116">The signature passed to `FindMember` must have been generated in the current scope, because signatures are bound to a particular scope.</span></span> <span data-ttu-id="07359-117">A signature can embed a token that identifies the enclosing class or value type.</span><span class="sxs-lookup"><span data-stu-id="07359-117">A signature can embed a token that identifies the enclosing class or value type.</span></span> <span data-ttu-id="07359-118">The token is an index into the local TypeDef table.</span><span class="sxs-lookup"><span data-stu-id="07359-118">The token is an index into the local TypeDef table.</span></span> <span data-ttu-id="07359-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span><span class="sxs-lookup"><span data-stu-id="07359-119">You cannot build a run-time signature outside the context of the current scope and use that signature as input to input to `FindMember`.</span></span>  
  
 <span data-ttu-id="07359-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span><span class="sxs-lookup"><span data-stu-id="07359-120">`FindMember` finds only members that were defined directly in the class or interface; it does not find inherited members.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="07359-121">`FindMember` is a helper method.</span><span class="sxs-lookup"><span data-stu-id="07359-121">`FindMember` is a helper method.</span></span> <span data-ttu-id="07359-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span><span class="sxs-lookup"><span data-stu-id="07359-122">It calls [IMetaDataImport::FindMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md); if that call does not find a match, `FindMember` then calls [IMetaDataImport::FindField](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07359-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="07359-123">Requirements</span></span>  
 <span data-ttu-id="07359-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07359-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07359-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="07359-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07359-126">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="07359-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="07359-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07359-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07359-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07359-128">See also</span></span>

- [<span data-ttu-id="07359-129">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07359-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="07359-130">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07359-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
