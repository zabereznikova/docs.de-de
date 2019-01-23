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
ms.openlocfilehash: ca5bd8716121148fa45cc9c66cdb19de79a06f47
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546542"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="8416d-102">IMetaDataEmit::SetCustomAttributeValue-Methode</span><span class="sxs-lookup"><span data-stu-id="8416d-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="8416d-103">Legt fest oder aktualisiert den Wert eines benutzerdefinierten Attributs definiert, die von einem vorherigen Aufruf von [DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="8416d-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8416d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8416d-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8416d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8416d-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="8416d-106">[in] Das Token des Ziel-Attributs.</span><span class="sxs-lookup"><span data-stu-id="8416d-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="8416d-107">[in] Ein Zeiger auf das Array, das das benutzerdefinierte Attribut enthält.</span><span class="sxs-lookup"><span data-stu-id="8416d-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="8416d-108">[in] Die Größe in Bytes des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="8416d-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8416d-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8416d-109">Requirements</span></span>  
 <span data-ttu-id="8416d-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8416d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8416d-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8416d-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8416d-112">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="8416d-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8416d-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8416d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8416d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8416d-114">See also</span></span>
- [<span data-ttu-id="8416d-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8416d-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8416d-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8416d-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
