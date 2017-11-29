---
title: IMetaDataImport::EnumMembers-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMembers
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMembers
helpviewer_keywords:
- IMetaDataImport::EnumMembers method [.NET Framework metadata]
- EnumMembers method [.NET Framework metadata]
ms.assetid: 3fb8e178-342b-4c89-9bcf-f7f834e6cb77
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cc17437c18dd7a2cdc2fdabdc714b12f8d91cc7a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="a6a33-102">IMetaDataImport::EnumMembers-Methode</span><span class="sxs-lookup"><span data-stu-id="a6a33-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="a6a33-103">Zählt MemberDef-Token auf, die Elemente des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="a6a33-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6a33-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6a33-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a6a33-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a6a33-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a6a33-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="a6a33-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="a6a33-107">[in] Eine TypeDef-Token, die den Typ, dessen Member aufzuzählenden darstellt.</span><span class="sxs-lookup"><span data-stu-id="a6a33-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="a6a33-108">[out] Das Array zum Speichern der MemberDef-Token verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6a33-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a6a33-109">[in] Die maximale Größe des `rMembers`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="a6a33-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a6a33-110">[out] Die tatsächliche Anzahl von MemberDef-Token im zurückgegebenen `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="a6a33-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a6a33-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a6a33-111">Return Value</span></span>  
  
|<span data-ttu-id="a6a33-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a6a33-112">HRESULT</span></span>|<span data-ttu-id="a6a33-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a6a33-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a6a33-114">`EnumMembers`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a6a33-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a6a33-115">Es sind keine MemberDef-Token, aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="a6a33-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="a6a33-116">In diesem Fall `pcTokens` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="a6a33-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a6a33-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a6a33-117">Remarks</span></span>  
 <span data-ttu-id="a6a33-118">Beim Aufzählen von Auflistungen von Elementen für eine Klasse `EnumMembers` gibt nur Elemente, die direkt für die Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="a6a33-118">When enumerating collections of members for a class, `EnumMembers` returns only members defined directly on the class.</span></span> <span data-ttu-id="a6a33-119">Es gibt keine Member, die die Klasse erbt, zurück, selbst wenn die Klasse eine Implementierung für diese geerbten Member bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="a6a33-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="a6a33-120">Um geerbte Member aufzulisten, muss der Aufrufer die Vererbungskette explizit durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="a6a33-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="a6a33-121">Beachten Sie, dass die Regeln für die Vererbungskette variiert je nach Sprache oder Compiler, die die ursprüngliche Metadaten ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="a6a33-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6a33-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a6a33-122">Requirements</span></span>  
 <span data-ttu-id="a6a33-123">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6a33-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6a33-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a6a33-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a6a33-125">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a6a33-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a6a33-126">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6a33-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6a33-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6a33-127">See Also</span></span>  
 [<span data-ttu-id="a6a33-128">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a6a33-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="a6a33-129">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a6a33-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
