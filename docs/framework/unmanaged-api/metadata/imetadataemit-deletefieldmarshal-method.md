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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 36f9ac10348cb8235c95070ddbc9cb5f47a84bd6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777440"
---
# <a name="imetadataemitdeletefieldmarshal-method"></a><span data-ttu-id="9f42e-102">IMetaDataEmit::DeleteFieldMarshal-Methode</span><span class="sxs-lookup"><span data-stu-id="9f42e-102">IMetaDataEmit::DeleteFieldMarshal Method</span></span>
<span data-ttu-id="9f42e-103">Zerstört die PInvoke Marshalling der Signatur der Metadaten für das Objekt, das durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9f42e-103">Destroys the PInvoke marshaling metadata signature for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f42e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f42e-104">Syntax</span></span>  
  
```cpp  
HRESULT DeleteFieldMarshal (  
    [in]  mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f42e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9f42e-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="9f42e-106">[in] Ein `mdFieldDef` oder `mdParamDef` Token, das das Feld oder Parameter für das Marshalling Metadatensignatur gelöscht darstellt.</span><span class="sxs-lookup"><span data-stu-id="9f42e-106">[in] An `mdFieldDef` or `mdParamDef` token that represents the field or parameter for which to delete the marshaling metadata signature.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f42e-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9f42e-107">Requirements</span></span>  
 <span data-ttu-id="9f42e-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f42e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f42e-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9f42e-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9f42e-110">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="9f42e-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9f42e-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f42e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f42e-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f42e-112">See also</span></span>

- [<span data-ttu-id="9f42e-113">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9f42e-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9f42e-114">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9f42e-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
