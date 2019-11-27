---
title: IMetaDataEmit::SetCustomAttributeValue-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetCustomAttributeValue
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetCustomAttributeValue
helpviewer_keywords:
- SetCustomAttributeValue method [.NET Framework metadata]
- IMetaDataEmit::SetCustomAttributeValue method [.NET Framework metadata]
ms.assetid: f721c863-9642-4e64-917a-65f9e55c25b9
topic_type:
- apiref
ms.openlocfilehash: fd5e71071de9e6afebc8f1848e0af8835f22c9bf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448126"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="d68f3-102">IMetaDataEmit::SetCustomAttributeValue-Methode</span><span class="sxs-lookup"><span data-stu-id="d68f3-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="d68f3-103">Legt den Wert eines benutzerdefinierten Attributs fest, das durch einen vorherigen [IMetaDataEmit::D efinecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)definiert ist, oder aktualisiert diesen.</span><span class="sxs-lookup"><span data-stu-id="d68f3-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d68f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d68f3-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCustomAttributeValue (   
    [in]  mdCustomAttribute       pcv,   
    [in]  void const              *pCustomAttribute,    
    [in]  ULONG                   cbCustomAttribute   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d68f3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d68f3-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="d68f3-106">in Das Token des benutzerdefinierten Ziel Attributs.</span><span class="sxs-lookup"><span data-stu-id="d68f3-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="d68f3-107">in Ein Zeiger auf das Array, das das benutzerdefinierte Attribut enthält.</span><span class="sxs-lookup"><span data-stu-id="d68f3-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="d68f3-108">in Die Größe (in Bytes) des benutzerdefinierten Attributs.</span><span class="sxs-lookup"><span data-stu-id="d68f3-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d68f3-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d68f3-109">Requirements</span></span>  
 <span data-ttu-id="d68f3-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d68f3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d68f3-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d68f3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d68f3-112">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="d68f3-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d68f3-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d68f3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d68f3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d68f3-114">See also</span></span>

- [<span data-ttu-id="d68f3-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d68f3-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d68f3-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d68f3-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
