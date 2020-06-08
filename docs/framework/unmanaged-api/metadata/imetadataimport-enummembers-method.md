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
ms.openlocfilehash: cc3bc5140da0634b5172f6253de3de37bff487f1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492033"
---
# <a name="imetadataimportenummembers-method"></a><span data-ttu-id="32c56-102">IMetaDataImport::EnumMembers-Methode</span><span class="sxs-lookup"><span data-stu-id="32c56-102">IMetaDataImport::EnumMembers Method</span></span>
<span data-ttu-id="32c56-103">Zählt MemberDef-Token auf, die Elemente des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="32c56-103">Enumerates MemberDef tokens representing members of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32c56-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32c56-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMembers (
   [in, out]  HCORENUM    *phEnum,
   [in]  mdTypeDef   cl,
   [out] mdToken     rMembers[],
   [in]  ULONG       cMax,
   [out] ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32c56-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="32c56-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="32c56-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="32c56-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `cl`  
 <span data-ttu-id="32c56-107">in Ein TypeDef-Token, das den Typ darstellt, dessen Member aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="32c56-107">[in] A TypeDef token representing the type whose members are to be enumerated.</span></span>  
  
 `rMembers`  
 <span data-ttu-id="32c56-108">vorgenommen Das Array, das zum Speichern der mitgliedtendef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="32c56-108">[out] The array used to hold the MemberDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="32c56-109">[in] Die maximale Größe des `rMembers`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="32c56-109">[in] The maximum size of the `rMembers` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="32c56-110">vorgenommen Die tatsächliche Anzahl der in zurückgegebenen mitgliedsdef-Token `rMembers` .</span><span class="sxs-lookup"><span data-stu-id="32c56-110">[out] The actual number of MemberDef tokens returned in `rMembers`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="32c56-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="32c56-111">Return Value</span></span>  
  
|<span data-ttu-id="32c56-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="32c56-112">HRESULT</span></span>|<span data-ttu-id="32c56-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="32c56-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="32c56-114">`EnumMembers`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="32c56-114">`EnumMembers` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="32c56-115">Es sind keine mitgliedungstokentoken zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="32c56-115">There are no MemberDef tokens to enumerate.</span></span> <span data-ttu-id="32c56-116">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="32c56-116">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32c56-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="32c56-117">Remarks</span></span>  
 <span data-ttu-id="32c56-118">Beim Auflisten von Auflistungen von Membern für eine Klasse `EnumMembers` gibt nur Member (Felder und Methoden, aber **keine** Eigenschaften oder Ereignisse) zurück, die direkt in der Klasse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="32c56-118">When enumerating collections of members for a class, `EnumMembers` returns only members (fields and methods, but **not** properties or events) defined directly on the class.</span></span> <span data-ttu-id="32c56-119">Er gibt keine Member zurück, die die Klasse erbt, selbst wenn die Klasse eine Implementierung für diese geerbten Member bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="32c56-119">It does not return any members that the class inherits, even if the class provides an implementation for those inherited members.</span></span> <span data-ttu-id="32c56-120">Um geerbte Member aufzuzählen, muss der Aufrufer die Vererbungs Kette explizit durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="32c56-120">To enumerate inherited members, the caller must explicitly walk the inheritance chain.</span></span> <span data-ttu-id="32c56-121">Beachten Sie, dass die Regeln für die Vererbungs Kette abhängig von der Sprache oder dem Compiler variieren können, die die ursprünglichen Metadaten ausgegeben haben.</span><span class="sxs-lookup"><span data-stu-id="32c56-121">Note that the rules for the inheritance chain may vary depending on the language or compiler that emitted the original metadata.</span></span>

 <span data-ttu-id="32c56-122">Eigenschaften und Ereignisse werden nicht durch aufgezählt `EnumMembers` .</span><span class="sxs-lookup"><span data-stu-id="32c56-122">Properties and events are not enumerated by `EnumMembers`.</span></span> <span data-ttu-id="32c56-123">Um diese aufzulisten, verwenden Sie [EnumProperties](imetadataimport-enumproperties-method.md) oder [EnumEvents](imetadataimport-enumevents-method.md).</span><span class="sxs-lookup"><span data-stu-id="32c56-123">To enumerate those, use [EnumProperties](imetadataimport-enumproperties-method.md) or [EnumEvents](imetadataimport-enumevents-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="32c56-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="32c56-124">Requirements</span></span>  
 <span data-ttu-id="32c56-125">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32c56-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32c56-126">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="32c56-126">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32c56-127">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="32c56-127">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="32c56-128">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32c56-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32c56-129">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="32c56-129">See also</span></span>

- [<span data-ttu-id="32c56-130">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="32c56-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="32c56-131">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="32c56-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
