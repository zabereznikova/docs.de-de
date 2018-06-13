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
ms.openlocfilehash: e5fca698adc4d08d805fec2ff80af377366674b6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445954"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="05489-102">IMetaDataImport::EnumMembersWithName-Methode</span><span class="sxs-lookup"><span data-stu-id="05489-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="05489-103">Zählt MemberDef-Token auf, die Elemente des angegebenen Typs mit dem angegebenen Namen darstellen.</span><span class="sxs-lookup"><span data-stu-id="05489-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05489-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05489-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="05489-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="05489-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="05489-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="05489-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="05489-107">[in] Eine TypeDef-Token, die den Typ der aufzulistenden Member darstellt.</span><span class="sxs-lookup"><span data-stu-id="05489-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="05489-108">[in] Der Elementname, der den Bereich des Enumerators einschränkt.</span><span class="sxs-lookup"><span data-stu-id="05489-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="05489-109">[out] Das Array zum Speichern der MemberDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="05489-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="05489-110">[in] Die maximale Größe des `rMembers`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="05489-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="05489-111">[out] Die tatsächliche Anzahl von MemberDef-Token im zurückgegebenen `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="05489-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05489-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="05489-112">Remarks</span></span>  
 <span data-ttu-id="05489-113">Diese Methode listet Felder und Methoden, jedoch keine Eigenschaften oder Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="05489-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="05489-114">Im Gegensatz zu [IMetaDataImport:: EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` verwirft alle Feld und Element-Token, die nicht mit den angegebenen Namen verfügen.</span><span class="sxs-lookup"><span data-stu-id="05489-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="05489-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="05489-115">Return Value</span></span>  
  
|<span data-ttu-id="05489-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="05489-116">HRESULT</span></span>|<span data-ttu-id="05489-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="05489-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="05489-118">`EnumTypeDefs` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="05489-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="05489-119">Es sind keine MemberDef-Token, aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="05489-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="05489-120">In diesem Fall `pcTokens` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="05489-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="05489-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="05489-121">Requirements</span></span>  
 <span data-ttu-id="05489-122">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05489-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05489-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="05489-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05489-124">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="05489-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="05489-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05489-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05489-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="05489-126">See Also</span></span>  
 [<span data-ttu-id="05489-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05489-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="05489-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05489-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
