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
ms.openlocfilehash: 99f529a151a42cf4a9ee1f74bd3a76a5b6b1b35f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445259"
---
# <a name="imetadataemitdefinemethodimpl-method"></a><span data-ttu-id="639f5-102">IMetaDataEmit::DefineMethodImpl-Methode</span><span class="sxs-lookup"><span data-stu-id="639f5-102">IMetaDataEmit::DefineMethodImpl Method</span></span>
<span data-ttu-id="639f5-103">Erstellt eine Definition für die Implementierung einer Methode, die von einer Schnittstelle geerbt wurde, und gibt ein Token an diese Methoden Implementierungs Definition zurück.</span><span class="sxs-lookup"><span data-stu-id="639f5-103">Creates a definition for implementation of a method inherited from an interface, and returns a token to that method-implementation definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="639f5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="639f5-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodImpl (   
    [in]  mdTypeDef         td,   
    [in]  mdToken           tkBody,   
    [in]  mdToken           tkDecl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="639f5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="639f5-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="639f5-106">in Das `mdTypedef` Token der implementierenden Klasse.</span><span class="sxs-lookup"><span data-stu-id="639f5-106">[in] The `mdTypedef` token of the implementing class.</span></span>  
  
 `tkBody`  
 <span data-ttu-id="639f5-107">in Der `mdMethodDef` oder `mdMemberRef` Token des Code Texts.</span><span class="sxs-lookup"><span data-stu-id="639f5-107">[in] The `mdMethodDef` or `mdMemberRef` token of the code body.</span></span>  
  
 `tkDecl`  
 <span data-ttu-id="639f5-108">in Die `mdMethodDef` oder `mdMemberRef` Token der Schnittstellen Methode, die implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="639f5-108">[in] The `mdMethodDef` or `mdMemberRef` token of the interface method being implemented.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="639f5-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="639f5-109">Requirements</span></span>  
 <span data-ttu-id="639f5-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="639f5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="639f5-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="639f5-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="639f5-112">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="639f5-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="639f5-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="639f5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="639f5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="639f5-114">See also</span></span>

- [<span data-ttu-id="639f5-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="639f5-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="639f5-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="639f5-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
