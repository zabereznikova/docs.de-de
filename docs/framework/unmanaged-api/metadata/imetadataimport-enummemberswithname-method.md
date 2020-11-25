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
ms.openlocfilehash: 35b82c33e54619eb9bebd5e5749ae202e905357a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720989"
---
# <a name="imetadataimportenummemberswithname-method"></a><span data-ttu-id="2d2e6-102">IMetaDataImport::EnumMembersWithName-Methode</span><span class="sxs-lookup"><span data-stu-id="2d2e6-102">IMetaDataImport::EnumMembersWithName Method</span></span>

<span data-ttu-id="2d2e6-103">Zählt MemberDef-Token auf, die Elemente des angegebenen Typs mit dem angegebenen Namen darstellen.</span><span class="sxs-lookup"><span data-stu-id="2d2e6-103">Enumerates MemberDef tokens representing members of the specified type with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d2e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2d2e6-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="2d2e6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2d2e6-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="2d2e6-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="2d2e6-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="2d2e6-107">in Ein TypeDef-Token, das den Typ mit aufzuzählenden Membern darstellt.</span><span class="sxs-lookup"><span data-stu-id="2d2e6-107">[in] A TypeDef token representing the type with members to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="2d2e6-108">in Der Elementname, der den Bereich des Enumerators einschränkt.</span><span class="sxs-lookup"><span data-stu-id="2d2e6-108">[in] The member name that limits the scope of the enumerator.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="2d2e6-109">vorgenommen Das Array, das zum Speichern der mitgliedungstokentoken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2d2e6-109">[out] The array used to store the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2d2e6-110">[in] Die maximale Größe des `rMembers`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="2d2e6-110">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="2d2e6-111">vorgenommen Die tatsächliche Anzahl der in zurückgegebenen mitgliedsdef-Token `rMembers` .</span><span class="sxs-lookup"><span data-stu-id="2d2e6-111">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2d2e6-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2d2e6-112">Remarks</span></span>  

 <span data-ttu-id="2d2e6-113">Diese Methode listet Felder und Methoden auf, aber keine Eigenschaften oder Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="2d2e6-113">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="2d2e6-114">Im Gegensatz zu [IMetaDataImport:: EnumMembers](imetadataimport-enummembers-method.md) `EnumMembersWithName` verwirft alle Feld-und Element Token, die nicht über den angegebenen Namen verfügen.</span><span class="sxs-lookup"><span data-stu-id="2d2e6-114">Unlike [IMetaDataImport::EnumMembers](imetadataimport-enummembers-method.md), `EnumMembersWithName` discards all field and member tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2d2e6-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2d2e6-115">Return Value</span></span>  
  
|<span data-ttu-id="2d2e6-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2d2e6-116">HRESULT</span></span>|<span data-ttu-id="2d2e6-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2d2e6-117">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2d2e6-118">`EnumTypeDefs` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2d2e6-118">`EnumTypeDefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2d2e6-119">Es sind keine mitgliedungstokentoken zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2d2e6-119">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="2d2e6-120">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="2d2e6-120">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2d2e6-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2d2e6-121">Requirements</span></span>  

 <span data-ttu-id="2d2e6-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2d2e6-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d2e6-123">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2d2e6-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2d2e6-124">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2d2e6-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2d2e6-125">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2d2e6-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d2e6-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d2e6-126">See also</span></span>

- [<span data-ttu-id="2d2e6-127">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d2e6-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="2d2e6-128">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d2e6-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
