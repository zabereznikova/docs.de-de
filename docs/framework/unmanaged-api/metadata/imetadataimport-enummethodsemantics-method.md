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
ms.openlocfilehash: f20652a7f86576e64646a1f63c3e2c48b55cf811
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175459"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="109d4-102">IMetaDataImport::EnumMethodSemantics-Methode</span><span class="sxs-lookup"><span data-stu-id="109d4-102">IMetaDataImport::EnumMethodSemantics Method</span></span>
<span data-ttu-id="109d4-103">Zählt die Eigenschaften und die Eigenschaftenänderungsereignisse auf, auf die sich die angegebene Methode bezieht.</span><span class="sxs-lookup"><span data-stu-id="109d4-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="109d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="109d4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="109d4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="109d4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="109d4-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="109d4-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="109d4-107">Dies muss NULL für den ersten Aufruf dieser Methode sein.</span><span class="sxs-lookup"><span data-stu-id="109d4-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="109d4-108">[in] Ein MethodDef-Token, das den Umfang der Enumeration einschränkt.</span><span class="sxs-lookup"><span data-stu-id="109d4-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="109d4-109">[out] Das Array, das zum Speichern der Ereignisse oder Eigenschaften verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="109d4-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="109d4-110">[in] Die maximale Größe des `rEventProp`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="109d4-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="109d4-111">[out] Die Anzahl der Ereignisse `rEventProp`oder Eigenschaften, die in zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="109d4-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="109d4-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="109d4-112">Return Value</span></span>  
  
|<span data-ttu-id="109d4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="109d4-113">HRESULT</span></span>|<span data-ttu-id="109d4-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="109d4-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="109d4-115">`EnumMethodSemantics`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="109d4-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="109d4-116">Es sind keine Ereignisse oder Eigenschaften zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="109d4-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="109d4-117">In diesem `pcEventProp` Fall ist Null.</span><span class="sxs-lookup"><span data-stu-id="109d4-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="109d4-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="109d4-118">Remarks</span></span>  
 <span data-ttu-id="109d4-119">Viele Common Language-Laufzeittypen definieren `On` *Eigenschaftsereignisse* `Changed` und *Eigenschaftenmethoden,* `Changed` die sich auf ihre Eigenschaften beziehen.</span><span class="sxs-lookup"><span data-stu-id="109d4-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="109d4-120">Der <xref:System.Windows.Forms.Control?displayProperty=nameWithType> Typ definiert beispielsweise <xref:System.Windows.Forms.Control.Font%2A> eine Eigenschaft, ein <xref:System.Windows.Forms.Control.FontChanged> <xref:System.Windows.Forms.Control.OnFontChanged%2A> Ereignis und eine Methode.</span><span class="sxs-lookup"><span data-stu-id="109d4-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="109d4-121">Die set accessor-Methode <xref:System.Windows.Forms.Control.Font%2A> <xref:System.Windows.Forms.Control.OnFontChanged%2A> der Eigenschaftsaufrufmethode, <xref:System.Windows.Forms.Control.FontChanged> die wiederum das Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="109d4-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="109d4-122">Sie würden `EnumMethodSemantics` die Anwendung <xref:System.Windows.Forms.Control.OnFontChanged%2A> von MethodDef <xref:System.Windows.Forms.Control.Font%2A> aufrufen, <xref:System.Windows.Forms.Control.FontChanged> um Verweise auf die Eigenschaft und das Ereignis abzurufen.</span><span class="sxs-lookup"><span data-stu-id="109d4-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="109d4-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="109d4-123">Requirements</span></span>  
 <span data-ttu-id="109d4-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="109d4-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="109d4-125">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="109d4-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="109d4-126">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="109d4-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="109d4-127">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="109d4-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="109d4-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="109d4-128">See also</span></span>

- [<span data-ttu-id="109d4-129">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="109d4-129">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="109d4-130">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="109d4-130">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
