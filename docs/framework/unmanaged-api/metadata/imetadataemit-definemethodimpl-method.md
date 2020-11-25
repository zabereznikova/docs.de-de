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
ms.openlocfilehash: 24a7c5bca1287e55f3eb06d63e1fed8da37eb3b0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719566"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="c8314-102">IMetaDataEmit::DefineMethodImpl-Methode</span><span class="sxs-lookup"><span data-stu-id="c8314-102">IMetaDataEmit::DefineMethodImpl Method</span></span>

<span data-ttu-id="c8314-103">Erstellt eine Definition für die Implementierung einer Methode, die von einer Schnittstelle geerbt wurde, und gibt ein Token an diese Methoden Implementierungs Definition zurück.</span><span class="sxs-lookup"><span data-stu-id="c8314-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8314-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c8314-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c8314-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c8314-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="c8314-106">in Das `mdTypedef` Token der implementierenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="c8314-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="c8314-107">in Das- `mdMethodDef` oder- `mdMemberRef` Token des Code Texts.</span><span class="sxs-lookup"><span data-stu-id="c8314-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="c8314-108">in Das- `mdMethodDef` oder- `mdMemberRef` Token der Schnittstellen Methode, die implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c8314-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c8314-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c8314-109">Requirements</span></span>  

 <span data-ttu-id="c8314-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8314-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8314-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c8314-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c8314-112">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="c8314-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c8314-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8314-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8314-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c8314-114">See also</span></span>

- [<span data-ttu-id="c8314-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8314-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="c8314-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c8314-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
