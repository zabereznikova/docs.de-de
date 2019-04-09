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
ms.openlocfilehash: a195daf2aa1b1c5a8f9c4335f7c4185f30093360
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178528"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="0b332-102">IMetaDataEmit::DeleteClassLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="0b332-102">IMetaDataEmit::DeleteClassLayout Method</span></span>
<span data-ttu-id="0b332-103">Zerstört die Metadatensignatur Layout für den Typ, der durch das angegebene Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0b332-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b332-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b332-104">Syntax</span></span>  
  
```  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b332-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0b332-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="0b332-106">[in] Ein `mdTypeDef` Metadatentoken, das den Typ darstellt, für die das Klassenlayout gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="0b332-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b332-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0b332-107">Requirements</span></span>  
 <span data-ttu-id="0b332-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b332-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b332-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0b332-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0b332-110">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="0b332-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="0b332-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="0b332-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0b332-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0b332-112">See also</span></span>

- [<span data-ttu-id="0b332-113">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b332-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0b332-114">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b332-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
