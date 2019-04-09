---
title: IMetaDataEmit::SetCustomAttributeValue-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6f9e684b90dcc7f0ff83962361486caf7e991568
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096341"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="4d0a1-102">IMetaDataEmit::SetCustomAttributeValue-Methode</span><span class="sxs-lookup"><span data-stu-id="4d0a1-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="4d0a1-103">Legt fest oder aktualisiert den Wert eines benutzerdefinierten Attributs definiert, die von einem vorherigen Aufruf von [DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="4d0a1-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d0a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4d0a1-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d0a1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4d0a1-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="4d0a1-106">[in] Das Token des Ziel-Attributs.</span><span class="sxs-lookup"><span data-stu-id="4d0a1-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="4d0a1-107">[in] Ein Zeiger auf das Array, das das benutzerdefinierte Attribut enthält.</span><span class="sxs-lookup"><span data-stu-id="4d0a1-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="4d0a1-108">[in] Die Größe in Bytes des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="4d0a1-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d0a1-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4d0a1-109">Requirements</span></span>  
 <span data-ttu-id="4d0a1-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d0a1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d0a1-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4d0a1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4d0a1-112">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4d0a1-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="4d0a1-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="4d0a1-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4d0a1-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d0a1-114">See also</span></span>

- [<span data-ttu-id="4d0a1-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d0a1-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4d0a1-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4d0a1-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
