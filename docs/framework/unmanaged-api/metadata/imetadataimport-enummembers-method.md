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
ms.openlocfilehash: 20c7a90f27defa18a5ef311d1f3a549b81fc5c40
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175485"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="0d4cf-102">IMetaDataImport::EnumMembers-Methode</span><span class="sxs-lookup"><span data-stu-id="0d4cf-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="0d4cf-103">Zählt MemberDef-Token auf, die Elemente des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d4cf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d4cf-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d4cf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0d4cf-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="0d4cf-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="0d4cf-107">[in] Ein TypeDef-Token, das den Typ darstellt, dessen Member aufgezählt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="0d4cf-108">[out] Das Array, das zum Besitz der MemberDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0d4cf-109">[in] Die maximale Größe des `rMembers`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="0d4cf-110">[out] Die tatsächliche Anzahl der MemberDef-Token, die in `rMembers`zurückgegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d4cf-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0d4cf-111">Return Value</span></span>  
  
|<span data-ttu-id="0d4cf-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0d4cf-112">HRESULT</span></span>|<span data-ttu-id="0d4cf-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d4cf-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0d4cf-114">`EnumMembers`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0d4cf-115">Es sind keine MemberDef-Token zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="0d4cf-116">In diesem `pcTokens` Fall ist Null.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d4cf-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0d4cf-117">Remarks</span></span>  
 <span data-ttu-id="0d4cf-118">Beim Aufzählen von Auflistungen von `EnumMembers` Membern für eine Klasse werden nur Member zurückgegeben (Felder und Methoden, jedoch **keine** Eigenschaften oder Ereignisse), die direkt für die Klasse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="0d4cf-119">Es werden keine Member zurückgegeben, die von der Klasse geerbt werden, auch wenn die Klasse eine Implementierung für diese geerbten Member bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="0d4cf-120">Um geerbte Member aufzuzählen, muss der Aufrufer die Vererbungskette explizit aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="0d4cf-121">Beachten Sie, dass die Regeln für die Vererbungskette je nach Sprache oder Compiler, der die ursprünglichen Metadaten ausgegeben hat, variieren können.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>

 <span data-ttu-id="0d4cf-122">Eigenschaften und Ereignisse werden nicht `EnumMembers`von aufgezählt.</span><span class="sxs-lookup"><span data-stu-id="0d4cf-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="0d4cf-123">Um diese aufzuzählen, verwenden Sie [EnumProperties](imetadataimport-enumproperties-method.md) oder [EnumEvents](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="0d4cf-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="0d4cf-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0d4cf-124">Requirements</span></span>  
 <span data-ttu-id="0d4cf-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d4cf-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d4cf-126">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0d4cf-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d4cf-127">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0d4cf-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d4cf-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d4cf-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d4cf-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0d4cf-129">See also</span></span>

- [<span data-ttu-id="0d4cf-130">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d4cf-130">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0d4cf-131">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d4cf-131">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
