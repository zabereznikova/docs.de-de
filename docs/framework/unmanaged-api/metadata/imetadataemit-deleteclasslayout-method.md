---
title: IMetaDataEmit::DeleteClassLayout-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteClassLayout
helpviewer_keywords:
- DeleteClassLayout method [.NET Framework metadata]
- IMetaDataEmit::DeleteClassLayout method [.NET Framework metadata]
ms.assetid: 65a4ad49-fa49-4b36-8ed1-76dd6a185ab4
topic_type:
- apiref
ms.openlocfilehash: d355e0e3b2461932384ca11d83d46fd1dc63b80e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732683"
---
# <a name="imetadataemitdeleteclasslayout-method"></a><span data-ttu-id="d0305-102">IMetaDataEmit::DeleteClassLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="d0305-102">IMetaDataEmit::DeleteClassLayout Method</span></span>

<span data-ttu-id="d0305-103">Zerstört die klassenlayoutmetadatensignatur für den Typ, der durch das angegebene Token dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d0305-103">Destroys the class layout metadata signature for the type represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0305-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0305-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteClassLayout (  
    [in]  mdTypeDef   td  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0305-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d0305-105">Parameters</span></span>  

 `td`  
 <span data-ttu-id="d0305-106">in Ein `mdTypeDef` Metadatentoken, das den Typ darstellt, für den das Klassen Layout gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="d0305-106">[in] An `mdTypeDef` metadata token that represents the type for which the class layout will be deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0305-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="d0305-107">Requirements</span></span>  

 <span data-ttu-id="d0305-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0305-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0305-109">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d0305-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d0305-110">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="d0305-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d0305-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0305-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0305-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0305-112">See also</span></span>

- [<span data-ttu-id="d0305-113">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0305-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d0305-114">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0305-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
