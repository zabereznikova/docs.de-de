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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: de4bf2cf647682062fbacb4484ffae905d1b7995
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/26/2019
ms.locfileid: "56835368"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="68ca0-102">IMetaDataImport::EnumMembers-Methode</span><span class="sxs-lookup"><span data-stu-id="68ca0-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="68ca0-103">Zählt MemberDef-Token auf, die Elemente des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="68ca0-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68ca0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="68ca0-104">Syntax</span></span>  
  
```  
HRESULT EnumMembers (   
   [in, out]  HCORENUM    *phEnum,   
   [in]  mdTypeDef   cl,   
   [out] mdToken     rMembers[],   
   [in]  ULONG       cMax,   
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68ca0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="68ca0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="68ca0-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="68ca0-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="68ca0-107">[in] Eine TypeDef-Token, das den Typ, dessen Member aufgelistet werden darstellt.</span><span class="sxs-lookup"><span data-stu-id="68ca0-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="68ca0-108">[out] Das Array, die MemberDef-Token enthalten.</span><span class="sxs-lookup"><span data-stu-id="68ca0-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="68ca0-109">[in] Die maximale Größe des `rMembers`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="68ca0-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="68ca0-110">[out] Die tatsächliche Anzahl der zurückgegebenen MemberDef-Token `rMembers`.</span><span class="sxs-lookup"><span data-stu-id="68ca0-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="68ca0-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="68ca0-111">Return Value</span></span>  
  
|<span data-ttu-id="68ca0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="68ca0-112">HRESULT</span></span>|<span data-ttu-id="68ca0-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="68ca0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="68ca0-114">`EnumMembers` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="68ca0-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="68ca0-115">Es gibt keine MemberDef-Token, die aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="68ca0-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="68ca0-116">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="68ca0-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68ca0-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68ca0-117">Remarks</span></span>  
 <span data-ttu-id="68ca0-118">Beim Auflisten von Sammlungen von Elementen für eine Klasse von `EnumMembers` gibt nur Mitglieder (Felder und Methoden, aber **nicht** Eigenschaften oder Ereignisse) direkt in der Klasse definiert.</span><span class="sxs-lookup"><span data-stu-id="68ca0-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="68ca0-119">Es gibt keine Member, die die Klasse erbt, zurück, auch wenn die Klasse eine Implementierung für diese geerbten Member bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="68ca0-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="68ca0-120">Um geerbte Member aufzulisten, muss der Aufrufer explizit die Vererbungskette geführt.</span><span class="sxs-lookup"><span data-stu-id="68ca0-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="68ca0-121">Beachten Sie, dass die Regeln für die Vererbungskette variieren abhängig von der Sprache und Compiler, die die ursprüngliche Metadaten ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="68ca0-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>
 
 <span data-ttu-id="68ca0-122">Eigenschaften und Ereignisse werden nicht durch den aufgezählt `EnumMembers`.</span><span class="sxs-lookup"><span data-stu-id="68ca0-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="68ca0-123">Verwenden Sie zum Auflisten von den [EnumProperties](imetadataimport-enumproperties-method.md) oder [EnumEvents](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="68ca0-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="68ca0-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="68ca0-124">Requirements</span></span>  
 <span data-ttu-id="68ca0-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68ca0-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68ca0-126">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="68ca0-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="68ca0-127">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="68ca0-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="68ca0-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68ca0-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68ca0-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68ca0-129">See also</span></span>
- [<span data-ttu-id="68ca0-130">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68ca0-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="68ca0-131">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="68ca0-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
