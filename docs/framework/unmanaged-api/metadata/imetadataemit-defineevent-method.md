---
title: IMetaDataEmit::DefineEvent-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineEvent
helpviewer_keywords:
- IMetaDataEmit::DefineEvent method [.NET Framework metadata]
- DefineEvent method [.NET Framework metadata]
ms.assetid: cf064bac-9a9f-41c5-9e1d-108ff7af3afe
topic_type:
- apiref
ms.openlocfilehash: 3c03497f48b8199da545d796637e5f8a5c532362
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95675684"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="d50da-102">IMetaDataEmit::DefineEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="d50da-102">IMetaDataEmit::DefineEvent Method</span></span>

<span data-ttu-id="d50da-103">Erstellt eine Definition für ein Ereignis mit der angegebenen Metadatensignatur und ruft ein Token für diese Ereignis Definition ab.</span><span class="sxs-lookup"><span data-stu-id="d50da-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d50da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d50da-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineEvent (
    [in]  mdTypeDef    td,
    [in]  LPCWSTR      szEvent,
    [in]  DWORD        dwEventFlags,
    [in]  mdToken      tkEventType,
    [in]  mdMethodDef  mdAddOn,
    [in]  mdMethodDef  mdRemoveOn,
    [in]  mdMethodDef  mdFire,
    [in]  mdMethodDef  rmdOtherMethods[],
    [out] mdEvent      *pmdEvent
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d50da-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d50da-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="d50da-106">in Das Token für die Zielklasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d50da-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="d50da-107">Dabei handelt es sich entweder um ein- `mdTypeDef` oder- `mdTypeDefNil` Token.</span><span class="sxs-lookup"><span data-stu-id="d50da-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="d50da-108">[in] Der Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="d50da-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="d50da-109">in Ereignisflags.</span><span class="sxs-lookup"><span data-stu-id="d50da-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="d50da-110">in Das Token für die Ereignisklasse.</span><span class="sxs-lookup"><span data-stu-id="d50da-110">[in] The token for the event class.</span></span> <span data-ttu-id="d50da-111">Dabei handelt es sich um ein- `mdTypeDef` , ein- `mdTypeRef` oder ein- `mdTokenNil` Token.</span><span class="sxs-lookup"><span data-stu-id="d50da-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="d50da-112">in Die Methode, die zum Abonnieren des Ereignisses verwendet wird, oder NULL.</span><span class="sxs-lookup"><span data-stu-id="d50da-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="d50da-113">in Die Methode, die zum Kündigen des Ereignisses verwendet wird, oder NULL.</span><span class="sxs-lookup"><span data-stu-id="d50da-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="d50da-114">in Die Methode, die (von einer abgeleiteten Klasse) verwendet wird, um das Ereignis zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="d50da-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="d50da-115">in Ein Array von Token für andere Methoden, die dem Ereignis zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d50da-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="d50da-116">Das Array wird mit einem `mdMethodDefNil` Token beendet.</span><span class="sxs-lookup"><span data-stu-id="d50da-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="d50da-117">vorgenommen Das Metadatentoken, das dem Ereignis zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="d50da-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d50da-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d50da-118">Requirements</span></span>  

 <span data-ttu-id="d50da-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d50da-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d50da-120">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d50da-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d50da-121">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="d50da-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d50da-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d50da-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d50da-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d50da-123">See also</span></span>

- [<span data-ttu-id="d50da-124">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d50da-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d50da-125">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d50da-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
