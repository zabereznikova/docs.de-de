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
ms.openlocfilehash: 5989c45782b4f83ecfa285cb305080320abf6a3c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700547"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="35d11-102">IMetaDataEmit::DeleteFieldMarshal-Methode</span><span class="sxs-lookup"><span data-stu-id="35d11-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>

<span data-ttu-id="35d11-103">Zerstört die PInvoke-marshallingmetadatensignatur für das Objekt, auf das durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="35d11-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35d11-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35d11-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35d11-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="35d11-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="35d11-106">in Ein- `mdFieldDef` oder- `mdParamDef` Token, das das Feld oder den Parameter darstellt, für das die marshallingmetadatensignatur gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="35d11-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35d11-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="35d11-107">Requirements</span></span>  

 <span data-ttu-id="35d11-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35d11-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35d11-109">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="35d11-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35d11-110">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="35d11-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="35d11-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35d11-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d11-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35d11-112">See also</span></span>

- [<span data-ttu-id="35d11-113">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35d11-113">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="35d11-114">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35d11-114">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
