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
ms.openlocfilehash: 52190583338f1c1ee9183a98d5f4a6cd7236342d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992549"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="3b62c-102">IMetaDataEmit::DefineCustomAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="3b62c-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="3b62c-103">Erstellt eine Definition für ein benutzerdefiniertes Attribut mit der angegebenen Metadaten-Signatur, die an das angegebene Objekt angefügt werden, und ruft ein Token für diese Definition des benutzerdefinierten Attributs ab.</span><span class="sxs-lookup"><span data-stu-id="3b62c-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b62c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3b62c-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b62c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3b62c-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="3b62c-106">[in] Das Token für das Besitzerelement.</span><span class="sxs-lookup"><span data-stu-id="3b62c-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="3b62c-107">[in] Das Token, das benutzerdefinierte Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="3b62c-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="3b62c-108">[in] Ein Zeiger auf das benutzerdefinierte Attribut.</span><span class="sxs-lookup"><span data-stu-id="3b62c-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="3b62c-109">[in] Die Anzahl der Bytes im `pCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="3b62c-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="3b62c-110">[out] Die `mdCustomAttribute` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="3b62c-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b62c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3b62c-111">Requirements</span></span>  
 <span data-ttu-id="3b62c-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b62c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b62c-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3b62c-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b62c-114">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="3b62c-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3b62c-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b62c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b62c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b62c-116">See also</span></span>

- [<span data-ttu-id="3b62c-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b62c-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3b62c-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3b62c-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
