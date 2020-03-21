---
title: IMetaDataEmit::DeletePinvokeMap-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DeletePinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DeletePinvokeMap
helpviewer_keywords:
- IMetaDataEmit::DeletePinvokeMap method [.NET Framework metadata]
- DeletePinvokeMap method [.NET Framework metadata]
ms.assetid: 3c4f6b54-5ce7-4a2a-83e1-6dec16441f50
topic_type:
- apiref
ms.openlocfilehash: 45f40dcd419e8e2fdf8a3349ccc9461854ad9aaf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175732"
---
# <a name="imetadataemitdeletepinvokemap-method"></a><span data-ttu-id="2daf4-102">IMetaDataEmit::DeletePinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="2daf4-102">IMetaDataEmit::DeletePinvokeMap Method</span></span>
<span data-ttu-id="2daf4-103">Zerstört die PInvoke-Zuordnungsmetadaten für das Objekt, auf das vom angegebenen Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2daf4-103">Destroys the PInvoke mapping metadata for the object referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2daf4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2daf4-104">Syntax</span></span>  
  
```cpp  
HRESULT DeletePinvokeMap (
    [in]  mdToken     tk
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2daf4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2daf4-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="2daf4-106">[in] Ein `mdFieldDef` `mdMethodDef` oder ein Token, das das Objekt darstellt, für das die PInvoke-Zuordnungsmetadaten gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2daf4-106">[in] An `mdFieldDef` or `mdMethodDef` token that represents the object for which to delete the PInvoke mapping metadata.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2daf4-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2daf4-107">Requirements</span></span>  
 <span data-ttu-id="2daf4-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2daf4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2daf4-109">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2daf4-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2daf4-110">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2daf4-110">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2daf4-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2daf4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2daf4-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2daf4-112">See also</span></span>

- [<span data-ttu-id="2daf4-113">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2daf4-113">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2daf4-114">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2daf4-114">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
