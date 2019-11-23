---
title: IMetaDataImport::EnumMembers-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type:
- apiref
ms.openlocfilehash: acb772a64c8f13405f2836bb5f4f308986dce414
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447656"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="483e4-102">IMetaDataImport::EnumMembers-Methode</span><span class="sxs-lookup"><span data-stu-id="483e4-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="483e4-103">Zählt MemberDef-Token auf, die Elemente des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="483e4-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="483e4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="483e4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="483e4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="483e4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="483e4-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="483e4-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="483e4-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span><span class="sxs-lookup"><span data-stu-id="483e4-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="483e4-108">[out] The array used to hold the MemberDef tokens.</span><span class="sxs-lookup"><span data-stu-id="483e4-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="483e4-109">[in] Die maximale Größe des `rMembers`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="483e4-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="483e4-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="483e4-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="483e4-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="483e4-111">Return Value</span></span>  
  
|<span data-ttu-id="483e4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="483e4-112">HRESULT</span></span>|<span data-ttu-id="483e4-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="483e4-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="483e4-114">`EnumMembers` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="483e4-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="483e4-115">There are no MemberDef tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="483e4-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="483e4-116">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="483e4-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="483e4-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="483e4-117">Remarks</span></span>  
 <span data-ttu-id="483e4-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span><span class="sxs-lookup"><span data-stu-id="483e4-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="483e4-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span><span class="sxs-lookup"><span data-stu-id="483e4-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="483e4-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span><span class="sxs-lookup"><span data-stu-id="483e4-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="483e4-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span><span class="sxs-lookup"><span data-stu-id="483e4-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>
 
 <span data-ttu-id="483e4-122">Properties and events are not enumerated by `EnumMembers`.</span><span class="sxs-lookup"><span data-stu-id="483e4-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="483e4-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="483e4-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="483e4-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="483e4-124">Requirements</span></span>  
 <span data-ttu-id="483e4-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="483e4-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="483e4-126">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="483e4-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="483e4-127">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="483e4-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="483e4-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="483e4-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="483e4-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="483e4-129">See also</span></span>

- [<span data-ttu-id="483e4-130">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="483e4-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="483e4-131">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="483e4-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
