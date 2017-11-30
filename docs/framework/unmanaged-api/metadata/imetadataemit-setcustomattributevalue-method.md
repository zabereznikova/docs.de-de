---
title: IMetaDataEmit::SetCustomAttributeValue-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetCustomAttributeValue
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 30538b0f6f6aa196edf8373f5f4e6f09ba903223
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="76a58-102">IMetaDataEmit::SetCustomAttributeValue-Methode</span><span class="sxs-lookup"><span data-stu-id="76a58-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="76a58-103">Legt fest oder aktualisiert den Wert eines benutzerdefinierten Attributs definiert, die durch einen vorherigen Aufruf von [DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span><span class="sxs-lookup"><span data-stu-id="76a58-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76a58-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="76a58-104">Syntax</span></span>  
  
```  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76a58-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="76a58-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="76a58-106">[in] Das Token des benutzerdefinierten Zielattributs.</span><span class="sxs-lookup"><span data-stu-id="76a58-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="76a58-107">[in] Ein Zeiger auf das Array, das das benutzerdefinierte Attribut enthält.</span><span class="sxs-lookup"><span data-stu-id="76a58-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="76a58-108">[in] Die Größe in Bytes, des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="76a58-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76a58-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="76a58-109">Requirements</span></span>  
 <span data-ttu-id="76a58-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76a58-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76a58-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="76a58-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="76a58-112">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="76a58-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76a58-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76a58-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76a58-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76a58-114">See Also</span></span>  
 [<span data-ttu-id="76a58-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="76a58-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="76a58-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="76a58-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
