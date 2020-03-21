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
ms.openlocfilehash: 9c4ed282e259aa46fc0cb0175214dc51d3d5fbee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175888"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="5dfa0-102">IMetaDataEmit::DefineCustomAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="5dfa0-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="5dfa0-103">Erstellt eine Definition für ein benutzerdefiniertes Attribut mit der angegebenen Metadatensignatur, die dem angegebenen Objekt zugeordnet werden soll, und ruft ein Token zu dieser benutzerdefinierten Attributdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="5dfa0-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5dfa0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5dfa0-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5dfa0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5dfa0-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="5dfa0-106">[in] Das Token für das Besitzerelement.</span><span class="sxs-lookup"><span data-stu-id="5dfa0-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="5dfa0-107">[in] Das Token, das das benutzerdefinierte Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="5dfa0-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="5dfa0-108">[in] Ein Zeiger auf das benutzerdefinierte Attribut.</span><span class="sxs-lookup"><span data-stu-id="5dfa0-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="5dfa0-109">[in] Die Anzahl der `pCustomAttribute`Bytes in .</span><span class="sxs-lookup"><span data-stu-id="5dfa0-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="5dfa0-110">[out] Das `mdCustomAttribute` token zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="5dfa0-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5dfa0-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5dfa0-111">Requirements</span></span>  
 <span data-ttu-id="5dfa0-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5dfa0-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5dfa0-113">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5dfa0-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5dfa0-114">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="5dfa0-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5dfa0-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5dfa0-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dfa0-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5dfa0-116">See also</span></span>

- [<span data-ttu-id="5dfa0-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5dfa0-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5dfa0-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5dfa0-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
