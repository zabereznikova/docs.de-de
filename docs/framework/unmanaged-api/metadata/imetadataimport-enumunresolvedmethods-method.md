---
title: IMetaDataImport::EnumUnresolvedMethods-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumUnresolvedMethods
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumUnresolvedMethods
helpviewer_keywords:
- EnumUnresolvedMethods method [.NET Framework metadata]
- IMetaDataImport::EnumUnresolvedMethods method [.NET Framework metadata]
ms.assetid: eb3187d7-74cf-44b1-aeeb-7a8d2b60e3b7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3c7709180e5b7811379c25977f8a8d23b91adb3d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenumunresolvedmethods-method"></a><span data-ttu-id="e55a7-102">IMetaDataImport::EnumUnresolvedMethods-Methode</span><span class="sxs-lookup"><span data-stu-id="e55a7-102">IMetaDataImport::EnumUnresolvedMethods Method</span></span>
<span data-ttu-id="e55a7-103">Zählt MemberDef-Token auf, die die nicht aufgelösten Methoden im aktuellen Metadatenbereich darstellen.</span><span class="sxs-lookup"><span data-stu-id="e55a7-103">Enumerates MemberDef tokens representing the unresolved methods in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e55a7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e55a7-104">Syntax</span></span>  
  
```  
HRESULT EnumUnresolvedMethods (  
   [in, out] HCORENUM    *phEnum,  
   [out]     mdToken     rMethods[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e55a7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e55a7-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e55a7-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="e55a7-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="e55a7-107">Dies muss für den ersten Aufruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="e55a7-107">This must be NULL for the first call of this method.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="e55a7-108">[out] Das Array zum Speichern der MemberDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e55a7-108">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e55a7-109">[in] Die maximale Größe des `rMethods`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="e55a7-109">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="e55a7-110">[out] Die Anzahl der zurückgegebenen MemberDef-Token `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="e55a7-110">[out] The number of MemberDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e55a7-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e55a7-111">Return Value</span></span>  
  
|<span data-ttu-id="e55a7-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e55a7-112">HRESULT</span></span>|<span data-ttu-id="e55a7-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e55a7-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="e55a7-114">`EnumUnresolvedMethods`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e55a7-114">`EnumUnresolvedMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="e55a7-115">Es sind keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="e55a7-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="e55a7-116">In diesem Fall `pcTokens` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="e55a7-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e55a7-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e55a7-117">Remarks</span></span>  
 <span data-ttu-id="e55a7-118">Eine nicht aufgelöste Methode ist eine, die deklariert, aber nicht implementiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e55a7-118">An unresolved method is one that has been declared but not implemented.</span></span> <span data-ttu-id="e55a7-119">Eine Methode ist in der Enumeration enthalten, wenn die Methode gekennzeichnet ist `miForwardRef` und entweder `mdPinvokeImpl` oder `miRuntime` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e55a7-119">A method is included in the enumeration if the method is marked `miForwardRef` and either `mdPinvokeImpl` or `miRuntime` is set to zero.</span></span> <span data-ttu-id="e55a7-120">Das heißt, nicht aufgelöste Methode ist eine Methode einer Klasse, die markiert ist `miForwardRef` aber die nicht in nicht verwaltetem Code (über PInvoke erreicht) implementiert ist, oder intern von der Laufzeit selbst implementiert</span><span class="sxs-lookup"><span data-stu-id="e55a7-120">In other words, an unresolved method is a class method that is marked `miForwardRef` but which is not implemented in unmanaged code (reached via PInvoke) nor implemented internally by the runtime itself</span></span>  
  
 <span data-ttu-id="e55a7-121">Die Enumeration schließt alle Methoden, die im Modul Gültigkeitsbereich (Global) oder in Schnittstellen oder abstrakten Klassen definiert werden.</span><span class="sxs-lookup"><span data-stu-id="e55a7-121">The enumeration excludes all methods that are defined either at module scope (globals) or in interfaces or abstract classes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e55a7-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e55a7-122">Requirements</span></span>  
 <span data-ttu-id="e55a7-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e55a7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e55a7-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e55a7-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e55a7-125">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e55a7-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e55a7-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e55a7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e55a7-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e55a7-127">See Also</span></span>  
 [<span data-ttu-id="e55a7-128">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e55a7-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e55a7-129">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e55a7-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
