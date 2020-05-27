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
ms.openlocfilehash: 17757df566ba8d141e7adec00dcc1f75959d0e00
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005626"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="8631a-102">IMetaDataEmit::DefineCustomAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="8631a-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="8631a-103">Erstellt eine Definition für ein benutzerdefiniertes Attribut mit der angegebenen Metadatensignatur, das an das angegebene Objekt angefügt werden soll, und ruft ein Token für die Definition des benutzerdefinierten Attributs ab.</span><span class="sxs-lookup"><span data-stu-id="8631a-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8631a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8631a-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineCustomAttribute (
    [in]  mdToken     tkObj,
    [in]  mdToken     tkType,
    [in]  void const  *pCustomAttribute,
    [in]  ULONG       cbCustomAttribute,
    [out] mdCustomAttribute *pcv
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8631a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8631a-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="8631a-106">in Das Token für das Besitzer Element.</span><span class="sxs-lookup"><span data-stu-id="8631a-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="8631a-107">in Das Token, das das benutzerdefinierte Attribut identifiziert.</span><span class="sxs-lookup"><span data-stu-id="8631a-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="8631a-108">in Ein Zeiger auf das benutzerdefinierte Attribut.</span><span class="sxs-lookup"><span data-stu-id="8631a-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="8631a-109">in Die Anzahl von Bytes in `pCustomAttribute` .</span><span class="sxs-lookup"><span data-stu-id="8631a-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="8631a-110">vorgenommen Das `mdCustomAttribute` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="8631a-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8631a-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8631a-111">Requirements</span></span>  
 <span data-ttu-id="8631a-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8631a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8631a-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8631a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8631a-114">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="8631a-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8631a-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8631a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8631a-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8631a-116">See also</span></span>

- [<span data-ttu-id="8631a-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8631a-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8631a-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8631a-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
