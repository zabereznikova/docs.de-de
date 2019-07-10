---
title: IMetaDataEmit::DeleteClassLayout-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 84de8e3c688a23198762fca5219d317fabb69c1b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777457"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="e9667-102">IMetaDataEmit::DeleteClassLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="e9667-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="e9667-103">Zerstört die Metadatensignatur Layout für den Typ, der durch das angegebene Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e9667-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9667-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e9667-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9667-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e9667-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="e9667-106">[in] Ein `mdTypeDef` Metadatentoken, das den Typ darstellt, für die das Klassenlayout gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="e9667-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9667-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e9667-107">Requirements</span></span>  
 <span data-ttu-id="e9667-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9667-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9667-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e9667-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e9667-110">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e9667-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9667-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9667-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9667-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e9667-112">See also</span></span>

- [<span data-ttu-id="e9667-113">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9667-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e9667-114">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e9667-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
