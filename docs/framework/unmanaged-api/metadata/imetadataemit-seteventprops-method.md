---
title: IMetaDataEmit::SetEventProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
ms.openlocfilehash: f664e694303691fb1132150037dcbcdb5549539a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177529"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="0ad6d-102">IMetaDataEmit::SetEventProps-Methode</span><span class="sxs-lookup"><span data-stu-id="0ad6d-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="0ad6d-103">Legt das angegebene Feature eines Ereignisses fest, das durch einen vorherigen Aufruf von [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)definiert wurde, oder aktualisiert es.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ad6d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ad6d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,
    [in]  DWORD       dwEventFlags,
    [in]  mdToken     tkEventType,
    [in]  mdMethodDef mdAddOn,
    [in]  mdMethodDef mdRemoveOn,
    [in]  mdMethodDef mdFire,
    [in]  mdMethodDef rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ad6d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ad6d-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="0ad6d-106">[in] Das Ereignistoken.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="0ad6d-107">[in] Ereignisflags.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-107">[in] Event flags.</span></span> <span data-ttu-id="0ad6d-108">Dies ist eine `CorEventAttr` Bitmaske von Werten.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="0ad6d-109">[in] Das Token für die Ereignisklasse.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-109">[in] The token for the event class.</span></span> <span data-ttu-id="0ad6d-110">Dies ist `mdTypeDef` entweder `mdTypeRef` ein oder ein Token.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="0ad6d-111">[in] Die Methode, die zum Abonnieren des Ereignisses verwendet wird, oder NULL.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="0ad6d-112">[in] Die Methode, die zum Abbestellen des Ereignisses verwendet wird, oder null.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="0ad6d-113">[in] Die Methode, die (von einer abgeleiteten Klasse) verwendet wird, um das Ereignis zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="0ad6d-114">[in] Ein Array von Token für andere Methoden, die dem Ereignis zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0ad6d-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="0ad6d-115">Das letzte Element des `mdMethodDefNil`Arrays muss .</span><span class="sxs-lookup"><span data-stu-id="0ad6d-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ad6d-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0ad6d-116">Requirements</span></span>  
 <span data-ttu-id="0ad6d-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ad6d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ad6d-118">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0ad6d-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ad6d-119">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="0ad6d-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ad6d-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ad6d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ad6d-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ad6d-121">See also</span></span>

- [<span data-ttu-id="0ad6d-122">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ad6d-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0ad6d-123">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ad6d-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
