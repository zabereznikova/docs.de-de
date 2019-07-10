---
title: IMetaDataImport::EnumMethodSemantics-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodSemantics
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodSemantics
helpviewer_keywords:
- EnumMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::EnumMethodSemantics method [.NET Framework metadata]
ms.assetid: e7e3c630-9691-46d6-94df-b5593a7bb08a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 715e53ae04532214d4011d4a40503b2ade5a014d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782072"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="a1d1d-102">IMetaDataImport::EnumMethodSemantics-Methode</span><span class="sxs-lookup"><span data-stu-id="a1d1d-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="a1d1d-103">Zählt die Eigenschaften und die Eigenschaftenänderungsereignisse auf, auf die sich die angegebene Methode bezieht.</span><span class="sxs-lookup"><span data-stu-id="a1d1d-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1d1d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1d1d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,   
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1d1d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a1d1d-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a1d1d-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="a1d1d-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a1d1d-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="a1d1d-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="a1d1d-108">[in] Ein MethodDef-Token, das den Bereich der Enumeration einschränkt.</span><span class="sxs-lookup"><span data-stu-id="a1d1d-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="a1d1d-109">[out] Das Array zum Speichern von Ereignissen oder Eigenschaften verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a1d1d-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a1d1d-110">[in] Die maximale Größe des `rEventProp`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="a1d1d-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="a1d1d-111">[out] Die Anzahl von Ereignissen oder Eigenschaften, die in zurückgegebenen `rEventProp`.</span><span class="sxs-lookup"><span data-stu-id="a1d1d-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a1d1d-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a1d1d-112">Return Value</span></span>  
  
|<span data-ttu-id="a1d1d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a1d1d-113">HRESULT</span></span>|<span data-ttu-id="a1d1d-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1d1d-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a1d1d-115">`EnumMethodSemantics` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a1d1d-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a1d1d-116">Es gibt keine Ereignisse oder Eigenschaften aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="a1d1d-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="a1d1d-117">In diesem Fall `pcEventProp` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="a1d1d-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a1d1d-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a1d1d-118">Remarks</span></span>  
 <span data-ttu-id="a1d1d-119">Viele Typen der common Language Runtime definieren *Eigenschaft* `Changed` Ereignisse und `On` *Eigenschaft* `Changed` Methoden, die sich auf ihre Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="a1d1d-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="a1d1d-120">Z. B. die <xref:System.Windows.Forms.Control?displayProperty=nameWithType> Typ definiert ein <xref:System.Windows.Forms.Control.Font%2A> -Eigenschaft, ein <xref:System.Windows.Forms.Control.FontChanged> Ereignis und einem <xref:System.Windows.Forms.Control.OnFontChanged%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="a1d1d-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="a1d1d-121">Die Set-Accessor-Methode, der die <xref:System.Windows.Forms.Control.Font%2A> eigenschaftsaufrufen <xref:System.Windows.Forms.Control.OnFontChanged%2A> -Methode, die wiederum löst die <xref:System.Windows.Forms.Control.FontChanged> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a1d1d-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="a1d1d-122">Rufen Sie `EnumMethodSemantics` mithilfe von MethodDef für <xref:System.Windows.Forms.Control.OnFontChanged%2A> zum Abrufen von Verweisen auf die <xref:System.Windows.Forms.Control.Font%2A> Eigenschaft und die <xref:System.Windows.Forms.Control.FontChanged> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a1d1d-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1d1d-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1d1d-123">Requirements</span></span>  
 <span data-ttu-id="a1d1d-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1d1d-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1d1d-125">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a1d1d-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a1d1d-126">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a1d1d-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a1d1d-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1d1d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1d1d-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1d1d-128">See also</span></span>

- [<span data-ttu-id="a1d1d-129">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1d1d-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a1d1d-130">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1d1d-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
