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
ms.openlocfilehash: 3d14aea92633c944d21d867c8152767ae6f1f291
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720970"
---
# <a name="imetadataimportenummethodsemantics-method"></a><span data-ttu-id="0e9bb-102">IMetaDataImport::EnumMethodSemantics-Methode</span><span class="sxs-lookup"><span data-stu-id="0e9bb-102">IMetaDataImport::EnumMethodSemantics Method</span></span>

<span data-ttu-id="0e9bb-103">Zählt die Eigenschaften und die Eigenschaftenänderungsereignisse auf, auf die sich die angegebene Methode bezieht.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-103">Enumerates the properties and the property-change events to which the specified method is related.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e9bb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e9bb-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodSemantics (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdMethodDef     mb,
   [out] mdToken         rEventProp[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcEventProp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e9bb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0e9bb-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="0e9bb-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="0e9bb-107">Dieser Wert muss für den ersten-Rückruf dieser Methode NULL sein.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-107">This must be NULL for the first call of this method.</span></span>  
  
 `mb`  
 <span data-ttu-id="0e9bb-108">in Ein MethodDef-Token, das den Bereich der-Enumeration einschränkt.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-108">[in] A MethodDef token that limits the scope of the enumeration.</span></span>  
  
 `rEventProp`  
 <span data-ttu-id="0e9bb-109">vorgenommen Das Array, das zum Speichern der Ereignisse oder Eigenschaften verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-109">[out] The array used to store the events or properties.</span></span>  
  
 `cMax`  
 <span data-ttu-id="0e9bb-110">[in] Die maximale Größe des `rEventProp`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-110">[in] The maximum size of the `rEventProp` array.</span></span>  
  
 `pcEventProp`  
 <span data-ttu-id="0e9bb-111">vorgenommen Die Anzahl der in zurückgegebenen Ereignisse oder Eigenschaften `rEventProp` .</span><span class="sxs-lookup"><span data-stu-id="0e9bb-111">[out] The number of events or properties returned in `rEventProp`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0e9bb-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0e9bb-112">Return Value</span></span>  
  
|<span data-ttu-id="0e9bb-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0e9bb-113">HRESULT</span></span>|<span data-ttu-id="0e9bb-114">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0e9bb-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="0e9bb-115">`EnumMethodSemantics` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-115">`EnumMethodSemantics` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="0e9bb-116">Es sind keine Ereignisse oder Eigenschaften zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-116">There are no events or properties to enumerate.</span></span> <span data-ttu-id="0e9bb-117">In diesem Fall `pcEventProp` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="0e9bb-117">In that case, `pcEventProp` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0e9bb-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e9bb-118">Remarks</span></span>  

 <span data-ttu-id="0e9bb-119">Viele Common Language Runtime Typen definieren *Eigenschafts* `Changed` Ereignisse und `On` *Eigenschafts* `Changed` Methoden, die sich auf ihre Eigenschaften beziehen.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-119">Many common language runtime types define *Property*`Changed` events and `On`*Property*`Changed` methods related to their properties.</span></span> <span data-ttu-id="0e9bb-120">Der <xref:System.Windows.Forms.Control?displayProperty=nameWithType> -Typ definiert z. b <xref:System.Windows.Forms.Control.Font%2A> . eine Eigenschaft, ein <xref:System.Windows.Forms.Control.FontChanged> -Ereignis und eine- <xref:System.Windows.Forms.Control.OnFontChanged%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-120">For example, the <xref:System.Windows.Forms.Control?displayProperty=nameWithType> type defines a <xref:System.Windows.Forms.Control.Font%2A> property, a <xref:System.Windows.Forms.Control.FontChanged> event, and an <xref:System.Windows.Forms.Control.OnFontChanged%2A> method.</span></span> <span data-ttu-id="0e9bb-121">Die Set-Accessor-Methode der- <xref:System.Windows.Forms.Control.Font%2A> Eigenschaft ruft die- <xref:System.Windows.Forms.Control.OnFontChanged%2A> Methode auf, die wiederum das- <xref:System.Windows.Forms.Control.FontChanged> Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="0e9bb-121">The set accessor method of the <xref:System.Windows.Forms.Control.Font%2A> property calls <xref:System.Windows.Forms.Control.OnFontChanged%2A> method, which in turn raises the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span> <span data-ttu-id="0e9bb-122">Zum Abrufen von `EnumMethodSemantics` <xref:System.Windows.Forms.Control.OnFontChanged%2A> verweisen auf die <xref:System.Windows.Forms.Control.Font%2A> -Eigenschaft und das-Ereignis wird die Verwendung von MethodDef für aufgerufen <xref:System.Windows.Forms.Control.FontChanged> .</span><span class="sxs-lookup"><span data-stu-id="0e9bb-122">You would call `EnumMethodSemantics` using the MethodDef for <xref:System.Windows.Forms.Control.OnFontChanged%2A> to get references to the <xref:System.Windows.Forms.Control.Font%2A> property and the <xref:System.Windows.Forms.Control.FontChanged> event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e9bb-123">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0e9bb-123">Requirements</span></span>  

 <span data-ttu-id="0e9bb-124">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e9bb-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e9bb-125">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0e9bb-125">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0e9bb-126">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0e9bb-126">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0e9bb-127">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e9bb-127">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e9bb-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0e9bb-128">See also</span></span>

- [<span data-ttu-id="0e9bb-129">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0e9bb-129">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="0e9bb-130">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0e9bb-130">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
