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
ms.openlocfilehash: 506e13ad956a01b16e36d8c71737fe0efce4c01b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450315"
---
# <a name="imetadataemitseteventprops-method"></a><span data-ttu-id="e8a1d-102">IMetaDataEmit::SetEventProps-Methode</span><span class="sxs-lookup"><span data-stu-id="e8a1d-102">IMetaDataEmit::SetEventProps Method</span></span>
<span data-ttu-id="e8a1d-103">Legt die angegebene Funktion eines Ereignisses fest, das durch einen vorherigen [IMetaDataEmit::D efineevent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)definiert ist, oder aktualisiert sie.</span><span class="sxs-lookup"><span data-stu-id="e8a1d-103">Sets or updates the specified feature of an event defined by a prior call to [IMetaDataEmit::DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8a1d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8a1d-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="e8a1d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e8a1d-105">Parameters</span></span>  
 `ev`  
 <span data-ttu-id="e8a1d-106">in Das Ereignis Token.</span><span class="sxs-lookup"><span data-stu-id="e8a1d-106">[in] The event token.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="e8a1d-107">in Ereignisflags.</span><span class="sxs-lookup"><span data-stu-id="e8a1d-107">[in] Event flags.</span></span> <span data-ttu-id="e8a1d-108">Dies ist eine Bitmaske von `CorEventAttr` Werten.</span><span class="sxs-lookup"><span data-stu-id="e8a1d-108">This is a bitmask of `CorEventAttr` values.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="e8a1d-109">in Das Token für die Ereignisklasse.</span><span class="sxs-lookup"><span data-stu-id="e8a1d-109">[in] The token for the event class.</span></span> <span data-ttu-id="e8a1d-110">Dabei handelt es sich entweder um ein `mdTypeDef`-oder ein `mdTypeRef` Token.</span><span class="sxs-lookup"><span data-stu-id="e8a1d-110">This is either a `mdTypeDef` or a `mdTypeRef` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="e8a1d-111">in Die Methode, die zum Abonnieren des Ereignisses verwendet wird, oder NULL.</span><span class="sxs-lookup"><span data-stu-id="e8a1d-111">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="e8a1d-112">in Die Methode, die zum Kündigen des Ereignisses verwendet wird, oder NULL.</span><span class="sxs-lookup"><span data-stu-id="e8a1d-112">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="e8a1d-113">in Die Methode, die (von einer abgeleiteten Klasse) verwendet wird, um das Ereignis zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="e8a1d-113">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="e8a1d-114">in Ein Array von Token für andere Methoden, die dem Ereignis zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e8a1d-114">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="e8a1d-115">Das letzte Element des Arrays muss `mdMethodDefNil`werden.</span><span class="sxs-lookup"><span data-stu-id="e8a1d-115">The last element of the array must be `mdMethodDefNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8a1d-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e8a1d-116">Requirements</span></span>  
 <span data-ttu-id="e8a1d-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8a1d-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8a1d-118">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="e8a1d-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e8a1d-119">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="e8a1d-119">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8a1d-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8a1d-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8a1d-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8a1d-121">See also</span></span>

- [<span data-ttu-id="e8a1d-122">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8a1d-122">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e8a1d-123">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e8a1d-123">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
