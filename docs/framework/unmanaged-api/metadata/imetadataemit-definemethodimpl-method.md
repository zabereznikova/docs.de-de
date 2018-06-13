---
title: IMetaDataEmit::DefineMethodImpl-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMethodImpl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMethodImpl
helpviewer_keywords:
- DefineMethodImpl method [.NET Framework metadata]
- IMetaDataEmit::DefineMethodImpl method [.NET Framework metadata]
ms.assetid: 9dcc8b3d-33ee-4c7c-8d6f-322c57b94a0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ab66fecfaa66b5c56690950f6b19ecfd7e85e33
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443988"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="c740e-102">IMetaDataEmit::DefineMethodImpl-Methode</span><span class="sxs-lookup"><span data-stu-id="c740e-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="c740e-103">Erstellt eine Definition für die Implementierung einer Methode, die von einer Schnittstelle geerbt, und gibt ein Token zu dieser Definition der Implementierung der Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="c740e-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c740e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c740e-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c740e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c740e-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="c740e-106">[in] Die `mdTypedef` der implementierenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="c740e-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="c740e-107">[in] Die `mdMethodDef` oder `mdMethodRef` token des Codetexts.</span><span class="sxs-lookup"><span data-stu-id="c740e-107">[in] The `mdMethodDef` or `mdMethodRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="c740e-108">[in] Die `mdMethodDef` oder `mdMethodRef` token der Schnittstellenmethode implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c740e-108">[in] The `mdMethodDef` or `mdMethodRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c740e-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c740e-109">Requirements</span></span>  
 <span data-ttu-id="c740e-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c740e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c740e-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c740e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c740e-112">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c740e-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c740e-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c740e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c740e-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c740e-114">See Also</span></span>  
 [<span data-ttu-id="c740e-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c740e-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="c740e-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c740e-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
