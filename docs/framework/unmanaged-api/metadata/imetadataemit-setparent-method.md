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
ms.openlocfilehash: d821413e67b36392d936499cd22f2e065f1556ec
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503847"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="0ce92-102">IMetaDataEmit::SetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="0ce92-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="0ce92-103">Legt fest, dass der angegebene Member, wie durch einen vorherigen-Befehl von [IMetaDataEmit::D efinemembership Ref](imetadataemit-definememberref-method.md)definiert, ein Member des angegebenen Typs ist, wie durch einen vorherigen-Befehl von [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="0ce92-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ce92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0ce92-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0ce92-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0ce92-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="0ce92-106">in Das `mdMemberRef` Token, das ein neues übergeordnetes Element empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="0ce92-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="0ce92-107">in Der `mdToken` für das neue übergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="0ce92-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ce92-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0ce92-108">Requirements</span></span>  
 <span data-ttu-id="0ce92-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ce92-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ce92-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0ce92-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0ce92-111">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="0ce92-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ce92-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ce92-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ce92-113">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="0ce92-113">See also</span></span>

- [<span data-ttu-id="0ce92-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ce92-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="0ce92-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0ce92-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
