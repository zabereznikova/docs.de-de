---
title: IMetaDataEmit::SetFieldMarshal-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9842108e9a26d7cca621c06b8ae1713e17c97ebe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476359"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="ce0ce-102">IMetaDataEmit::SetFieldMarshal-Methode</span><span class="sxs-lookup"><span data-stu-id="ce0ce-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="ce0ce-103">Legt die Marshallinginformationen für den Parameter Feld, Methode zurückgeben, oder eine Methode, die auf die verwiesen wird durch das angegebene Token PInvoke fest.</span><span class="sxs-lookup"><span data-stu-id="ce0ce-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce0ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce0ce-104">Syntax</span></span>  
  
```  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ce0ce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ce0ce-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="ce0ce-106">[in] Das Token für die Ziel-Datenelement.</span><span class="sxs-lookup"><span data-stu-id="ce0ce-106">[in] The token for target data item.</span></span> <span data-ttu-id="ce0ce-107">Dies ist entweder ein `mdFieldDef` oder `mdParamDef` token.</span><span class="sxs-lookup"><span data-stu-id="ce0ce-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="ce0ce-108">[in] Die Signatur für nicht verwalteten Typ.</span><span class="sxs-lookup"><span data-stu-id="ce0ce-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="ce0ce-109">[in] Die Anzahl der Bytes im `pvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="ce0ce-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce0ce-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ce0ce-110">Requirements</span></span>  
 <span data-ttu-id="ce0ce-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce0ce-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce0ce-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ce0ce-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce0ce-113">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="ce0ce-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce0ce-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce0ce-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce0ce-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce0ce-115">See also</span></span>
- [<span data-ttu-id="ce0ce-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce0ce-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ce0ce-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce0ce-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
