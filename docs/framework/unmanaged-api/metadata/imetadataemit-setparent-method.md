---
title: IMetaDataEmit::SetParent-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetParent
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 56436b3801eb55559605f6c875bb6fde84c2db8f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="7406e-102">IMetaDataEmit::SetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="7406e-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="7406e-103">Legt fest, dass die angegebenen Member auf, wie er durch einen vorherigen Aufruf [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), ist ein Member des angegebenen Typs gemäß der Definition von einem vorherigen Aufruf für [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="7406e-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7406e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7406e-104">Syntax</span></span>  
  
```  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7406e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7406e-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="7406e-106">[in] Die `mdMemberRef` Token, mit einen neuen übergeordneten empfangen.</span><span class="sxs-lookup"><span data-stu-id="7406e-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="7406e-107">[in] Die `mdToken` für das neue übergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="7406e-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7406e-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7406e-108">Requirements</span></span>  
 <span data-ttu-id="7406e-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7406e-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7406e-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7406e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7406e-111">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="7406e-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7406e-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7406e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7406e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7406e-113">See Also</span></span>  
 [<span data-ttu-id="7406e-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7406e-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="7406e-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7406e-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
