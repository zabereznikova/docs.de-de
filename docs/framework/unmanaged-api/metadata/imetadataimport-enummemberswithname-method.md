---
title: IMetaDataImport::EnumMembersWithName-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.EnumMembersWithName
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3b0cef8fca7be315185ab521464b251f2a94f3b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="50389-102">IMetaDataImport::EnumMembersWithName-Methode</span><span class="sxs-lookup"><span data-stu-id="50389-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="50389-103">Zählt MemberDef-Token auf, die Elemente des angegebenen Typs mit dem angegebenen Namen darstellen.</span><span class="sxs-lookup"><span data-stu-id="50389-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50389-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="50389-104">Syntax</span></span>  
  
```  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   cl,   
   [in]      LPCWSTR     szName,   
   [out]     mdToken     rMembers[],   
   [in]      ULONG       cMax,   
   [out]     ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="50389-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="50389-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="50389-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="50389-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="50389-107">[in] Eine TypeDef-Token, die den Typ der aufzulistenden Member darstellt.</span><span class="sxs-lookup"><span data-stu-id="50389-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="50389-108">[in] Der Elementname, der den Bereich des Enumerators einschränkt.</span><span class="sxs-lookup"><span data-stu-id="50389-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="50389-109">[out] Das Array zum Speichern der MemberDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="50389-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="50389-110">[in] Die maximale Größe des `rMembers`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="50389-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="50389-111">[out] Die tatsächliche Anzahl von MemberDef-Token im zurückgegebenen `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="50389-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50389-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="50389-112">Remarks</span></span>  
 <span data-ttu-id="50389-113">Diese Methode listet Felder und Methoden, jedoch keine Eigenschaften oder Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="50389-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="50389-114">Im Gegensatz zu [IMetaDataImport:: EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` verwirft alle Feld und Element-Token, die nicht mit den angegebenen Namen verfügen.</span><span class="sxs-lookup"><span data-stu-id="50389-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="50389-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="50389-115">Return Value</span></span>  
  
|<span data-ttu-id="50389-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="50389-116">HRESULT</span></span>|<span data-ttu-id="50389-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50389-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="50389-118">`EnumTypeDefs`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="50389-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="50389-119">Es sind keine MemberDef-Token, aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="50389-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="50389-120">In diesem Fall `pcTokens` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="50389-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="50389-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="50389-121">Requirements</span></span>  
 <span data-ttu-id="50389-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="50389-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50389-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="50389-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="50389-124">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="50389-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50389-125">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50389-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50389-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="50389-126">See Also</span></span>  
 [<span data-ttu-id="50389-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50389-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="50389-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="50389-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
