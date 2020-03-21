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
ms.openlocfilehash: 7389e9233fd946cdb2c810bec01cfbfffc8b707d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175602"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="e707c-102">IMetaDataEmit::SetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="e707c-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="e707c-103">Legt fest, dass das angegebene Element, wie durch einen vorherigen Aufruf von [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)definiert, ein Member des angegebenen Typs ist, wie durch einen vorherigen Aufruf von [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="e707c-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e707c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e707c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (
    [in]  mdMemberRef mr,
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e707c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e707c-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="e707c-106">[in] Das `mdMemberRef` Token, das ein neues übergeordnetes Element empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="e707c-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="e707c-107">[in] Die `mdToken` für das neue übergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="e707c-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e707c-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e707c-108">Requirements</span></span>  
 <span data-ttu-id="e707c-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e707c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e707c-110">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e707c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e707c-111">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e707c-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e707c-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e707c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e707c-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e707c-113">See also</span></span>

- [<span data-ttu-id="e707c-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e707c-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e707c-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e707c-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
