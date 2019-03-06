---
title: IMetaDataEmit::DefineCustomAttribute-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: adf3c74526bbf2b8e740f505ab6f4243cd799041
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474578"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="ecfdc-102">IMetaDataEmit::DefineCustomAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="ecfdc-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="ecfdc-103">Erstellt eine Definition für ein benutzerdefiniertes Attribut mit der angegebenen Metadaten-Signatur, die an das angegebene Objekt angefügt werden, und ruft ein Token für diese Definition des benutzerdefinierten Attributs ab.</span><span class="sxs-lookup"><span data-stu-id="ecfdc-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecfdc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ecfdc-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecfdc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ecfdc-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="ecfdc-106">[in] Das Token für das Besitzerelement.</span><span class="sxs-lookup"><span data-stu-id="ecfdc-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="ecfdc-107">[in] Das Token, das benutzerdefinierte Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="ecfdc-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="ecfdc-108">[in] Ein Zeiger auf das benutzerdefinierte Attribut.</span><span class="sxs-lookup"><span data-stu-id="ecfdc-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="ecfdc-109">[in] Die Anzahl der Bytes im `pCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="ecfdc-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="ecfdc-110">[out] Die `mdCustomAttribute` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="ecfdc-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecfdc-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ecfdc-111">Requirements</span></span>  
 <span data-ttu-id="ecfdc-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecfdc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecfdc-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ecfdc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ecfdc-114">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="ecfdc-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ecfdc-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecfdc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecfdc-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ecfdc-116">See also</span></span>
- [<span data-ttu-id="ecfdc-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ecfdc-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ecfdc-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ecfdc-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
