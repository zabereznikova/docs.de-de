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
ms.openlocfilehash: b64275def01d7b62f9a461de69a286769094305e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777583"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="c1950-102">IMetaDataEmit::DefineMethodImpl-Methode</span><span class="sxs-lookup"><span data-stu-id="c1950-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="c1950-103">Erstellt eine Definition für die Implementierung einer Methode, die von einer Schnittstelle geerbt, und ein Token an dieser Definition der Implementierung der Methode zurück.</span><span class="sxs-lookup"><span data-stu-id="c1950-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1950-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1950-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1950-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c1950-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="c1950-106">[in] Die `mdTypedef` token von der implementierenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="c1950-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="c1950-107">[in] Die `mdMethodDef` oder `mdMemberRef` des Codetexts token.</span><span class="sxs-lookup"><span data-stu-id="c1950-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="c1950-108">[in] Die `mdMethodDef` oder `mdMemberRef` token der Schnittstellenmethode implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c1950-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1950-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c1950-109">Requirements</span></span>  
 <span data-ttu-id="c1950-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1950-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1950-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c1950-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1950-112">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c1950-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c1950-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1950-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1950-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1950-114">See also</span></span>

- [<span data-ttu-id="c1950-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1950-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c1950-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1950-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
