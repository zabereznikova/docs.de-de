---
title: IMetaDataEmit::DefineMethodImpl-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineMethodImpl
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5bf16c51a241a01f18aae84f8b3bb7554f08b87c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="8edd9-102">IMetaDataEmit::DefineMethodImpl-Methode</span><span class="sxs-lookup"><span data-stu-id="8edd9-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="8edd9-103">Erstellt eine Definition für die Implementierung einer Methode, die von einer Schnittstelle geerbt, und gibt ein Token zu dieser Definition der Implementierung der Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="8edd9-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8edd9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8edd9-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8edd9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8edd9-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="8edd9-106">[in] Die `mdTypedef` der implementierenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="8edd9-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="8edd9-107">[in] Die `mdMethodDef` oder `mdMethodRef` token des Codetexts.</span><span class="sxs-lookup"><span data-stu-id="8edd9-107">[in] The `mdMethodDef` or `mdMethodRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="8edd9-108">[in] Die `mdMethodDef` oder `mdMethodRef` token der Schnittstellenmethode implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="8edd9-108">[in] The `mdMethodDef` or `mdMethodRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8edd9-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8edd9-109">Requirements</span></span>  
 <span data-ttu-id="8edd9-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8edd9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8edd9-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8edd9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8edd9-112">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="8edd9-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8edd9-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8edd9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8edd9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8edd9-114">See Also</span></span>  
 [<span data-ttu-id="8edd9-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8edd9-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="8edd9-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8edd9-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
