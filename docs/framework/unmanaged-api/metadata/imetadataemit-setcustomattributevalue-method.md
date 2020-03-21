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
ms.openlocfilehash: 25b7f478ae0bd05b82fa960561fb8534efe2b4db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175667"
---
# <a name="imetadataemitsetcustomattributevalue-method"></a><span data-ttu-id="2b2c7-102">IMetaDataEmit::SetCustomAttributeValue-Methode</span><span class="sxs-lookup"><span data-stu-id="2b2c7-102">IMetaDataEmit::SetCustomAttributeValue Method</span></span>
<span data-ttu-id="2b2c7-103">Legt den Wert eines benutzerdefinierten Attributs fest, das durch einen vorherigen Aufruf von [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2b2c7-103">Sets or updates the value of a custom attribute defined by a prior call to [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b2c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b2c7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetCustomAttributeValue (
    [in]  mdCustomAttribute       pcv,
    [in]  void const              *pCustomAttribute,
    [in]  ULONG                   cbCustomAttribute
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b2c7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2b2c7-105">Parameters</span></span>  
 `pcv`  
 <span data-ttu-id="2b2c7-106">[in] Das Token des benutzerdefinierten Zielattributs.</span><span class="sxs-lookup"><span data-stu-id="2b2c7-106">[in] The token of the target custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="2b2c7-107">[in] Ein Zeiger auf das Array, das das benutzerdefinierte Attribut enthält.</span><span class="sxs-lookup"><span data-stu-id="2b2c7-107">[in] A pointer to the array that contains the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="2b2c7-108">[in] Die Größe des benutzerdefinierten Attributs in Bytes.</span><span class="sxs-lookup"><span data-stu-id="2b2c7-108">[in] The size, in bytes, of the custom attribute.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b2c7-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2b2c7-109">Requirements</span></span>  
 <span data-ttu-id="2b2c7-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b2c7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b2c7-111">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2b2c7-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2b2c7-112">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2b2c7-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b2c7-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b2c7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b2c7-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b2c7-114">See also</span></span>

- [<span data-ttu-id="2b2c7-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b2c7-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="2b2c7-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2b2c7-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
