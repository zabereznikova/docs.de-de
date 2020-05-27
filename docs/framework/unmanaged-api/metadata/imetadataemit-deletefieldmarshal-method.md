---
title: IMetaDataEmit::DeleteFieldMarshal-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeleteFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeleteFieldMarshal
helpviewer_keywords:
- IMetaDataEmit::DeleteFieldMarshal method [.NET Framework metadata]
- DeleteFieldMarshal method [.NET Framework metadata]
ms.assetid: 7c75aef9-c742-4b33-a14b-56ff94b0f725
topic_type:
- apiref
ms.openlocfilehash: 6d0f9a8c5c3baf7594e098a3d5544bad55fdc917
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009287"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="bd50a-102">IMetaDataEmit::DeleteFieldMarshal-Methode</span><span class="sxs-lookup"><span data-stu-id="bd50a-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="bd50a-103">Zerstört die PInvoke-marshallingmetadatensignatur für das Objekt, auf das durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="bd50a-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd50a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd50a-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd50a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd50a-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="bd50a-106">in Ein- `mdFieldDef` oder- `mdParamDef` Token, das das Feld oder den Parameter darstellt, für das die marshallingmetadatensignatur gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="bd50a-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd50a-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bd50a-107">Requirements</span></span>  
 <span data-ttu-id="bd50a-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd50a-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd50a-109">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="bd50a-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd50a-110">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="bd50a-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd50a-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd50a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd50a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd50a-112">See also</span></span>

- [<span data-ttu-id="bd50a-113">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd50a-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="bd50a-114">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd50a-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
