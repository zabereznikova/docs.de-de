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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74d0c2e9777a7bd3d49622fb326ecb6b58fbec07
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782547"
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="cda08-102">IMetaDataImport::EnumUnresolvedMethods-Methode</span><span class="sxs-lookup"><span data-stu-id="cda08-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="cda08-103">Zählt MemberDef-Token auf, die die nicht aufgelösten Methoden im aktuellen Metadatenbereich darstellen.</span><span class="sxs-lookup"><span data-stu-id="cda08-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cda08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cda08-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cda08-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cda08-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="cda08-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="cda08-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="cda08-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="cda08-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="cda08-108">[out] Das Array zum Speichern der MemberDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cda08-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="cda08-109">[in] Die maximale Größe des `rMethods`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="cda08-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="cda08-110">[out] Die Anzahl der zurückgegebenen MemberDef-Token `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="cda08-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cda08-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cda08-111">Return Value</span></span>  
  
|<span data-ttu-id="cda08-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cda08-112">HRESULT</span></span>|<span data-ttu-id="cda08-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cda08-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="cda08-114">`EnumUnresolvedMethods` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cda08-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="cda08-115">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="cda08-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="cda08-116">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="cda08-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cda08-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cda08-117">Remarks</span></span>  
 <span data-ttu-id="cda08-118">Eine nicht aufgelöste Methode ist, der deklariert, aber nicht implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="cda08-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="cda08-119">Eine Methode ist in der Enumeration enthalten, wenn die Methode markiert ist `miForwardRef` und entweder `mdPinvokeImpl` oder `miRuntime` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="cda08-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="cda08-120">Das heißt, eine nicht aufgelöste Methode ist die Methode einer Klasse, die markiert ist `miForwardRef` , aber das ist nicht implementiert, die in nicht verwaltetem Code (über PInvoke erreicht) oder intern von der Laufzeit selbst implementiert</span><span class="sxs-lookup"><span data-stu-id="cda08-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="cda08-121">Die Enumeration schließt alle Methoden, die entweder im Modulbereich (Global) oder in Schnittstellen oder abstrakten Klassen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="cda08-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cda08-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cda08-122">Requirements</span></span>  
 <span data-ttu-id="cda08-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cda08-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cda08-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cda08-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cda08-125">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cda08-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cda08-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cda08-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cda08-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cda08-127">See also</span></span>

- [<span data-ttu-id="cda08-128">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cda08-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="cda08-129">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cda08-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
