---
title: IMetaDataImport::EnumUnresolvedMethods-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUnresolvedMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type:
- apiref
ms.openlocfilehash: ff9827174e43fd62f3a995e9f477c6fff66b227a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449956"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="f0804-102">IMetaDataImport::EnumUnresolvedMethods-Methode</span><span class="sxs-lookup"><span data-stu-id="f0804-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="f0804-103">Zählt MemberDef-Token auf, die die nicht aufgelösten Methoden im aktuellen Metadatenbereich darstellen.</span><span class="sxs-lookup"><span data-stu-id="f0804-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0804-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0804-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0804-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0804-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f0804-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="f0804-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f0804-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="f0804-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="f0804-108">[out] The array used to store the MemberDef tokens.</span><span class="sxs-lookup"><span data-stu-id="f0804-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f0804-109">[in] Die maximale Größe des `rMethods`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="f0804-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="f0804-110">[out] The number of MemberDef tokens returned in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="f0804-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0804-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f0804-111">Return Value</span></span>  
  
|<span data-ttu-id="f0804-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f0804-112">HRESULT</span></span>|<span data-ttu-id="f0804-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0804-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f0804-114">`EnumUnresolvedMethods` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="f0804-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f0804-115">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="f0804-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="f0804-116">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="f0804-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f0804-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f0804-117">Remarks</span></span>  
 <span data-ttu-id="f0804-118">An unresolved method is one that has been declared but not implemented.</span><span class="sxs-lookup"><span data-stu-id="f0804-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="f0804-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span><span class="sxs-lookup"><span data-stu-id="f0804-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="f0804-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span><span class="sxs-lookup"><span data-stu-id="f0804-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="f0804-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span><span class="sxs-lookup"><span data-stu-id="f0804-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0804-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0804-122">Requirements</span></span>  
 <span data-ttu-id="f0804-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0804-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0804-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f0804-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f0804-125">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f0804-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f0804-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0804-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0804-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0804-127">See also</span></span>

- [<span data-ttu-id="f0804-128">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0804-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="f0804-129">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0804-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
