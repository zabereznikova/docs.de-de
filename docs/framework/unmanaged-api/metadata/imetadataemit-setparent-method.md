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
ms.openlocfilehash: fdaa6aab28eb82450db7b9f946e033bfad55faf5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446068"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="caa52-102">IMetaDataEmit::SetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="caa52-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="caa52-103">Legt fest, dass die angegebenen Member auf, wie er durch einen vorherigen Aufruf [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), ist ein Member des angegebenen Typs gemäß der Definition von einem vorherigen Aufruf für [DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="caa52-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="caa52-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="caa52-104">Syntax</span></span>  
  
```  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="caa52-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="caa52-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="caa52-106">[in] Die `mdMemberRef` Token, mit einen neuen übergeordneten empfangen.</span><span class="sxs-lookup"><span data-stu-id="caa52-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="caa52-107">[in] Die `mdToken` für das neue übergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="caa52-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caa52-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="caa52-108">Requirements</span></span>  
 <span data-ttu-id="caa52-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caa52-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caa52-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="caa52-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="caa52-111">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="caa52-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="caa52-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caa52-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa52-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="caa52-113">See Also</span></span>  
 [<span data-ttu-id="caa52-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="caa52-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="caa52-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="caa52-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
