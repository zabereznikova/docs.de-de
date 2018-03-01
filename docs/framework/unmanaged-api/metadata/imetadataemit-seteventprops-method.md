---
title: IMetaDataEmit::SetEventProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f8e2089c3f4b4e7677c2ddb9eabc8ee08cfd3695
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="0d7df-102">IMetaDataEmit::SetEventProps-Methode</span><span class="sxs-lookup"><span data-stu-id="0d7df-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="0d7df-103">Legt fest oder aktualisiert die angegebene Funktion eines Ereignisses definiert, die durch einen vorherigen Aufruf von [DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span><span class="sxs-lookup"><span data-stu-id="0d7df-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d7df-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d7df-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="0d7df-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0d7df-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="0d7df-106">[in] Das Ereignistoken.</span><span class="sxs-lookup"><span data-stu-id="0d7df-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="0d7df-107">[in] Ereignisflags.</span><span class="sxs-lookup"><span data-stu-id="0d7df-107">[in] Event flags.</span></span> <span data-ttu-id="0d7df-108">Dies ist eine Bitmaske der `CorEventAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="0d7df-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="0d7df-109">[in] Das Token für die Ereignisklasse.</span><span class="sxs-lookup"><span data-stu-id="0d7df-109">[in] The token for the event class.</span></span> <span data-ttu-id="0d7df-110">Dies liegt entweder an einem `mdTypeDef` oder ein `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="0d7df-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="0d7df-111">[in] Die Methode, die zum Abonnieren der Ereignis- oder Null.</span><span class="sxs-lookup"><span data-stu-id="0d7df-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="0d7df-112">[in] Die Methode verwendet, um das Ereignis bzw. Null Kündigen des Abonnements.</span><span class="sxs-lookup"><span data-stu-id="0d7df-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="0d7df-113">[in] Die Methode, die zum Auslösen des Ereignisses (durch eine abgeleitete Klasse) verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d7df-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="0d7df-114">[in] Ein Array von Token für andere Methoden, die dem Ereignis zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0d7df-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="0d7df-115">Das letzte Element des Arrays muss `mdMethodDefNil`.</span><span class="sxs-lookup"><span data-stu-id="0d7df-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d7df-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0d7df-116">Requirements</span></span>  
 <span data-ttu-id="0d7df-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d7df-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d7df-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0d7df-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d7df-119">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="0d7df-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0d7df-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d7df-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d7df-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d7df-121">See Also</span></span>  
 [<span data-ttu-id="0d7df-122">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d7df-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="0d7df-123">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d7df-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
