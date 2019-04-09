---
title: IMetaDataEmit::DeletePinvokeMap-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5ea100ff86286cb98db5aa9fa6f3c12f5d318a90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217743"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="5f7b7-102">IMetaDataEmit::DeletePinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="5f7b7-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="5f7b7-103">Zerstört die PInvoke-Mapping-Metadaten für das Objekt, das durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5f7b7-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f7b7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f7b7-104">Syntax</span></span>  
  
```  
HRESULT DeletePinvokeMap (   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f7b7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5f7b7-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="5f7b7-106">[in] Ein `mdFieldDef` oder `mdMethodDef` Token, das das Objekt für die Sie löschen die PInvoke-Zuordnungsmetadaten darstellt.</span><span class="sxs-lookup"><span data-stu-id="5f7b7-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f7b7-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5f7b7-107">Requirements</span></span>  
 <span data-ttu-id="5f7b7-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f7b7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f7b7-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5f7b7-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f7b7-110">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="5f7b7-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5f7b7-111">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5f7b7-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5f7b7-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f7b7-112">See also</span></span>

- [<span data-ttu-id="5f7b7-113">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f7b7-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5f7b7-114">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f7b7-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
