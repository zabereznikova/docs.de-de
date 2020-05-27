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
ms.openlocfilehash: 5ed5afbbf49b6680d00e78b6af3d45c6f0a7229d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004490"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="a0ab3-102">IMetaDataEmit::DefineMethodImpl-Methode</span><span class="sxs-lookup"><span data-stu-id="a0ab3-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="a0ab3-103">Erstellt eine Definition für die Implementierung einer Methode, die von einer Schnittstelle geerbt wurde, und gibt ein Token an diese Methoden Implementierungs Definition zurück.</span><span class="sxs-lookup"><span data-stu-id="a0ab3-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0ab3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0ab3-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (
    [in]  mdTypeDef         td,
    [in]  mdToken           tkBody,
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0ab3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0ab3-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="a0ab3-106">in Das `mdTypedef` Token der implementierenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="a0ab3-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="a0ab3-107">in Das- `mdMethodDef` oder- `mdMemberRef` Token des Code Texts.</span><span class="sxs-lookup"><span data-stu-id="a0ab3-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="a0ab3-108">in Das- `mdMethodDef` oder- `mdMemberRef` Token der Schnittstellen Methode, die implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="a0ab3-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0ab3-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a0ab3-109">Requirements</span></span>  
 <span data-ttu-id="a0ab3-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0ab3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0ab3-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a0ab3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0ab3-112">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="a0ab3-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0ab3-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0ab3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0ab3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0ab3-114">See also</span></span>

- [<span data-ttu-id="a0ab3-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0ab3-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="a0ab3-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0ab3-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
