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
ms.openlocfilehash: 7410f91a853f3a677a105dc2e12a86d723c9fad6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177317"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="d5ee8-102">IMetaDataImport::EnumMembersWithName-Methode</span><span class="sxs-lookup"><span data-stu-id="d5ee8-102">IMetaDataImport::EnumMembersWithName Method</span></span>
<span data-ttu-id="d5ee8-103">Zählt MemberDef-Token auf, die Elemente des angegebenen Typs mit dem angegebenen Namen darstellen.</span><span class="sxs-lookup"><span data-stu-id="d5ee8-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5ee8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5ee8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembersWithName (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   cl,
   [in]      LPCWSTR     szName,
   [out]     mdToken     rMembers[],
   [in]      ULONG       cMax,
   [out]     ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5ee8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5ee8-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="d5ee8-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="d5ee8-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="d5ee8-107">[in] Ein TypeDef-Token, das den Typ mit aufzuzählenden Membern darstellt.</span><span class="sxs-lookup"><span data-stu-id="d5ee8-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="d5ee8-108">[in] Der Membername, der den Umfang des Enumerators einschränkt.</span><span class="sxs-lookup"><span data-stu-id="d5ee8-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="d5ee8-109">[out] Das Array, das zum Speichern der MemberDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d5ee8-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="d5ee8-110">[in] Die maximale Größe des `rMembers`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="d5ee8-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d5ee8-111">[out] Die tatsächliche Anzahl der MemberDef-Token, die in `rMembers`zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="d5ee8-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5ee8-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="d5ee8-112">Remarks</span></span>  
 <span data-ttu-id="d5ee8-113">Diese Methode zählt Felder und Methoden auf, jedoch keine Eigenschaften oder Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="d5ee8-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="d5ee8-114">Im Gegensatz zu [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md) `EnumMembersWithName` verwirft alle Feld- und Elementtoken, die nicht den angegebenen Namen haben.</span><span class="sxs-lookup"><span data-stu-id="d5ee8-114">Unlike [IMetaDataImport::EnumMembers](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d5ee8-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d5ee8-115">Return Value</span></span>  
  
|<span data-ttu-id="d5ee8-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d5ee8-116">HRESULT</span></span>|<span data-ttu-id="d5ee8-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d5ee8-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="d5ee8-118">`EnumTypeDefs`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d5ee8-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="d5ee8-119">Es sind keine MemberDef-Token zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="d5ee8-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="d5ee8-120">In diesem `pcTokens` Fall ist Null.</span><span class="sxs-lookup"><span data-stu-id="d5ee8-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d5ee8-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d5ee8-121">Requirements</span></span>  
 <span data-ttu-id="d5ee8-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5ee8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5ee8-123">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d5ee8-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d5ee8-124">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d5ee8-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d5ee8-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5ee8-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5ee8-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d5ee8-126">See also</span></span>

- [<span data-ttu-id="d5ee8-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5ee8-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="d5ee8-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5ee8-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
