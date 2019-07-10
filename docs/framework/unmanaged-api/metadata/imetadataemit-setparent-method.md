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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6006c8892f650eec9528074d54f030d84ee8f88
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750881"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="0c0e0-102">IMetaDataEmit::SetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="0c0e0-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="0c0e0-103">Erstellt, durch die das angegebene Element gemäß Definition durch einen vorherigen Aufruf von [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), ein Mitglied über den angegebenen Typ ist, gemäß einem vorherigen Aufruf von [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="0c0e0-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c0e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c0e0-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c0e0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0c0e0-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="0c0e0-106">[in] Die `mdMemberRef` Token um ein neues übergeordnetes Element zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0c0e0-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="0c0e0-107">[in] Die `mdToken` für das neue übergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="0c0e0-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c0e0-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0c0e0-108">Requirements</span></span>  
 <span data-ttu-id="0c0e0-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c0e0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c0e0-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0c0e0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c0e0-111">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="0c0e0-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c0e0-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c0e0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c0e0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c0e0-113">See also</span></span>

- [<span data-ttu-id="0c0e0-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0c0e0-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0c0e0-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0c0e0-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
