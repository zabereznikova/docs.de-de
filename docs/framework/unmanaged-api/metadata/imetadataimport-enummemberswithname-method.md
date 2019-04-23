---
title: IMetaDataImport::EnumMembersWithName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMembersWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMembersWithName
helpviewer_keywords:
- IMetaDataImport::EnumMembersWithName method [.NET Framework metadata]
- EnumMembersWithName method [.NET Framework metadata]
ms.assetid: 7c9e9120-3104-42f0-86ce-19a025f20dcc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c2509945d2799b81e036888d146a51cee87fda09
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169844"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="7a4ee-102">IMetaDataImport::EnumMembersWithName-Methode</span><span class="sxs-lookup"><span data-stu-id="7a4ee-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="7a4ee-103">Zählt MemberDef-Token auf, die Elemente des angegebenen Typs mit dem angegebenen Namen darstellen.</span><span class="sxs-lookup"><span data-stu-id="7a4ee-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a4ee-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a4ee-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="7a4ee-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7a4ee-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7a4ee-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="7a4ee-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="7a4ee-107">[in] Eine TypeDef-Token, die den Typ der aufzulistenden Member darstellt.</span><span class="sxs-lookup"><span data-stu-id="7a4ee-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="7a4ee-108">[in] Der Elementname, der den Bereich des Enumerators einschränkt.</span><span class="sxs-lookup"><span data-stu-id="7a4ee-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="7a4ee-109">[out] Das Array zum Speichern der MemberDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7a4ee-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7a4ee-110">[in] Die maximale Größe des `rMembers`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="7a4ee-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="7a4ee-111">[out] Die tatsächliche Anzahl der zurückgegebenen MemberDef-Token `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="7a4ee-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a4ee-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a4ee-112">Remarks</span></span>  
 <span data-ttu-id="7a4ee-113">Diese Methode listet die Felder und Methoden, jedoch keine Eigenschaften oder Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="7a4ee-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="7a4ee-114">Im Gegensatz zu [IMetaDataImport:: EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` verwirft alle Feld und Element-Token, die nicht mit den angegebenen Namen verfügen.</span><span class="sxs-lookup"><span data-stu-id="7a4ee-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a4ee-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7a4ee-115">Return Value</span></span>  
  
|<span data-ttu-id="7a4ee-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a4ee-116">HRESULT</span></span>|<span data-ttu-id="7a4ee-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7a4ee-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7a4ee-118">`EnumTypeDefs` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7a4ee-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7a4ee-119">Es gibt keine MemberDef-Token, die aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="7a4ee-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="7a4ee-120">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="7a4ee-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7a4ee-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7a4ee-121">Requirements</span></span>  
 <span data-ttu-id="7a4ee-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a4ee-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a4ee-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7a4ee-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7a4ee-124">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7a4ee-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7a4ee-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a4ee-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a4ee-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a4ee-126">See also</span></span>

- [<span data-ttu-id="7a4ee-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a4ee-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7a4ee-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7a4ee-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
