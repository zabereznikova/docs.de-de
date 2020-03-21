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
ms.openlocfilehash: 64d76efa8c2f29fda559e5c84217b865540027ba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175823"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="77f8c-102">IMetaDataEmit::DefineMethodImpl-Methode</span><span class="sxs-lookup"><span data-stu-id="77f8c-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="77f8c-103">Erstellt eine Definition für die Implementierung einer Methode, die von einer Schnittstelle geerbt wurde, und gibt ein Token an diese Methodenimplementierungsdefinition zurück.</span><span class="sxs-lookup"><span data-stu-id="77f8c-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77f8c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77f8c-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77f8c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="77f8c-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="77f8c-106">[in] Das `mdTypedef` Token der implementierenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="77f8c-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="77f8c-107">[in] Das `mdMethodDef` `mdMemberRef` oder Token des Codetexts.</span><span class="sxs-lookup"><span data-stu-id="77f8c-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="77f8c-108">[in] Das `mdMethodDef` `mdMemberRef` oder-Token der implementierten Schnittstellenmethode.</span><span class="sxs-lookup"><span data-stu-id="77f8c-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77f8c-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="77f8c-109">Requirements</span></span>  
 <span data-ttu-id="77f8c-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77f8c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77f8c-111">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="77f8c-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77f8c-112">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="77f8c-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="77f8c-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77f8c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77f8c-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="77f8c-114">See also</span></span>

- [<span data-ttu-id="77f8c-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77f8c-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="77f8c-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="77f8c-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
