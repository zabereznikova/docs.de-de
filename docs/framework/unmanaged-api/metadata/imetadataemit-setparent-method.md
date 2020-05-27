---
title: IMetaDataEmit::SetParent-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
ms.openlocfilehash: da82950ea1a0da81c77d173be9ab45dcb3001bfe
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007831"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="b2aed-102">IMetaDataEmit::SetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="b2aed-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="b2aed-103">Legt fest, dass der angegebene Member, wie durch einen vorherigen-Befehl von [IMetaDataEmit::D efinemembership Ref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)definiert, ein Member des angegebenen Typs ist, wie durch einen vorherigen-Befehl von [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="b2aed-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2aed-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2aed-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2aed-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b2aed-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="b2aed-106">in Das `mdMemberRef` Token, das ein neues übergeordnetes Element empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="b2aed-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="b2aed-107">in Der `mdToken` für das neue übergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="b2aed-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2aed-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b2aed-108">Requirements</span></span>  
 <span data-ttu-id="b2aed-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2aed-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2aed-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b2aed-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2aed-111">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2aed-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2aed-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2aed-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2aed-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2aed-113">See also</span></span>

- [<span data-ttu-id="b2aed-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b2aed-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="b2aed-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b2aed-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
