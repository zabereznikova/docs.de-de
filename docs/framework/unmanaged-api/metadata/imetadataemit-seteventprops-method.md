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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ab479aab56b429c104a44b1fae192bc7f20a389d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656920"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="92491-102">IMetaDataEmit::SetEventProps-Methode</span><span class="sxs-lookup"><span data-stu-id="92491-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="92491-103">Legt fest oder aktualisiert die angegebene Funktion eines Ereignisses definiert, die von einem vorherigen Aufruf von [IMetaDataEmit:: DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="92491-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92491-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="92491-104">Syntax</span></span>  
  
```  
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
  
#### <a name="parameters"></a><span data-ttu-id="92491-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="92491-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="92491-106">[in] Das Ereignistoken.</span><span class="sxs-lookup"><span data-stu-id="92491-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="92491-107">[in] Ereignisflags.</span><span class="sxs-lookup"><span data-stu-id="92491-107">[in] Event flags.</span></span> <span data-ttu-id="92491-108">Dies ist eine Bitmaske der `CorEventAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="92491-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="92491-109">[in] Das Token für Event-Klasse.</span><span class="sxs-lookup"><span data-stu-id="92491-109">[in] The token for the event class.</span></span> <span data-ttu-id="92491-110">Dies ist entweder ein `mdTypeDef` oder `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="92491-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="92491-111">[in] Die Methode, die zum Abonnieren das Ereignis oder Null.</span><span class="sxs-lookup"><span data-stu-id="92491-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="92491-112">[in] Die Methode verwendet, um das Ereignis oder Null zu kündigen.</span><span class="sxs-lookup"><span data-stu-id="92491-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="92491-113">[in] Die Methode, die zum Auslösen des Ereignisses (durch eine abgeleitete Klasse) verwendet.</span><span class="sxs-lookup"><span data-stu-id="92491-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="92491-114">[in] Ein Array von Token für andere Methoden, die dem Ereignis zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="92491-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="92491-115">Das letzte Element des Arrays muss `mdMethodDefNil`.</span><span class="sxs-lookup"><span data-stu-id="92491-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92491-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92491-116">Requirements</span></span>  
 <span data-ttu-id="92491-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92491-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92491-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="92491-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92491-119">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="92491-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="92491-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92491-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92491-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92491-121">See also</span></span>
- [<span data-ttu-id="92491-122">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92491-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="92491-123">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92491-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
