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
ms.openlocfilehash: a9598be850604f16ee8cc62187e1fed7ecf3a7e4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175849"
---
# <a name="imetadataemitdefineevent-method"></a><span data-ttu-id="d5b39-102">IMetaDataEmit::DefineEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="d5b39-102">IMetaDataEmit::DefineEvent Method</span></span>
<span data-ttu-id="d5b39-103">Erstellt eine Definition für ein Ereignis mit der angegebenen Metadatensignatur und ruft ein Token für diese Ereignisdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="d5b39-103">Creates a definition for an event with the specified metadata signature, and gets a token to that event definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5b39-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5b39-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="d5b39-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5b39-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="d5b39-106">[in] Das Token für die Zielklasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="d5b39-106">[in] The token for the target class or interface.</span></span> <span data-ttu-id="d5b39-107">Dies ist `mdTypeDef` `mdTypeDefNil` entweder ein oder ein Token.</span><span class="sxs-lookup"><span data-stu-id="d5b39-107">This is either a `mdTypeDef` or `mdTypeDefNil` token.</span></span>  
  
 `szEvent`  
 <span data-ttu-id="d5b39-108">[in] Der Name des Ereignisses.</span><span class="sxs-lookup"><span data-stu-id="d5b39-108">[in] The name of the event.</span></span>  
  
 `dwEventFlags`  
 <span data-ttu-id="d5b39-109">[in] Ereignisflags.</span><span class="sxs-lookup"><span data-stu-id="d5b39-109">[in] Event flags.</span></span>  
  
 `tkEventType`  
 <span data-ttu-id="d5b39-110">[in] Das Token für die Ereignisklasse.</span><span class="sxs-lookup"><span data-stu-id="d5b39-110">[in] The token for the event class.</span></span> <span data-ttu-id="d5b39-111">Dies `mdTypeDef`ist `mdTypeRef`ein , `mdTokenNil` ein oder ein Token.</span><span class="sxs-lookup"><span data-stu-id="d5b39-111">This is a `mdTypeDef`, a `mdTypeRef`, or a `mdTokenNil` token.</span></span>  
  
 `mdAddOn`  
 <span data-ttu-id="d5b39-112">[in] Die Methode, die zum Abonnieren des Ereignisses verwendet wird, oder NULL.</span><span class="sxs-lookup"><span data-stu-id="d5b39-112">[in] The method used to subscribe to the event, or null.</span></span>  
  
 `mdRemoveOn`  
 <span data-ttu-id="d5b39-113">[in] Die Methode, die zum Abbestellen des Ereignisses verwendet wird, oder null.</span><span class="sxs-lookup"><span data-stu-id="d5b39-113">[in] The method used to unsubscribe to the event, or null.</span></span>  
  
 `mdFire`  
 <span data-ttu-id="d5b39-114">[in] Die Methode, die (von einer abgeleiteten Klasse) verwendet wird, um das Ereignis zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="d5b39-114">[in] The method used (by a derived class) to raise the event.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="d5b39-115">[in] Ein Array von Token für andere Methoden, die dem Ereignis zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d5b39-115">[in] An array of tokens for other methods associated with the event.</span></span> <span data-ttu-id="d5b39-116">Das Array wird mit `mdMethodDefNil` einem Token beendet.</span><span class="sxs-lookup"><span data-stu-id="d5b39-116">The array is terminated with a `mdMethodDefNil` token.</span></span>  
  
 `pmdEvent`  
 <span data-ttu-id="d5b39-117">[out] Das dem Ereignis zugewiesene Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="d5b39-117">[out] The metadata token assigned to the event.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5b39-118">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d5b39-118">Requirements</span></span>  
 <span data-ttu-id="d5b39-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5b39-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5b39-120">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d5b39-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d5b39-121">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d5b39-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5b39-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5b39-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5b39-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d5b39-123">See also</span></span>

- [<span data-ttu-id="d5b39-124">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5b39-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d5b39-125">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5b39-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
