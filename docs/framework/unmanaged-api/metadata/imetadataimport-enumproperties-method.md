---
title: IMetaDataImport::EnumProperties-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumProperties
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumProperties
helpviewer_keywords:
- IMetaDataImport::EnumProperties method [.NET Framework metadata]
- EnumProperties method [.NET Framework metadata]
ms.assetid: 60573ad7-8821-4721-a068-3f7a6d25926a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c63797b60354b461891f44d32cf1840f7fdcf3d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756494"
---
# <a name="imetadataimportenumproperties-method"></a><span data-ttu-id="481de-102">IMetaDataImport::EnumProperties-Methode</span><span class="sxs-lookup"><span data-stu-id="481de-102">IMetaDataImport::EnumProperties Method</span></span>
<span data-ttu-id="481de-103">Zählt PropertyDef-Token auf, die die Eigenschaften des Typs darstellen, auf den vom angegebenen TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="481de-103">Enumerates PropertyDef tokens representing the properties of the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="481de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="481de-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumProperties (  
   [in, out] HCORENUM    *phEnum,  
   [in]      mdTypeDef   td,  
   [out]     mdProperty  rProperties[],  
   [in]      ULONG       cMax,  
   [out]     ULONG       *pcProperties  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="481de-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="481de-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="481de-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="481de-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="481de-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="481de-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="481de-108">[in] Eine TypeDef-Token, das den Typ mit Eigenschaften auflisten darstellt.</span><span class="sxs-lookup"><span data-stu-id="481de-108">[in] A TypeDef token representing the type with properties to enumerate.</span></span>  
  
 `rProperties`  
 <span data-ttu-id="481de-109">[out] Das Array zum Speichern der PropertyDef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="481de-109">[out] The array used to store the PropertyDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="481de-110">[in] Die maximale Größe des `rProperties`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="481de-110">[in] The maximum size of the `rProperties` array.</span></span>  
  
 `pcProperties`  
 <span data-ttu-id="481de-111">[out] Die Anzahl der zurückgegebenen PropertyDef-Token `rProperties`.</span><span class="sxs-lookup"><span data-stu-id="481de-111">[out] The number of PropertyDef tokens returned in `rProperties`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="481de-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="481de-112">Return Value</span></span>  
  
|<span data-ttu-id="481de-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="481de-113">HRESULT</span></span>|<span data-ttu-id="481de-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="481de-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="481de-115">`EnumProperties` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="481de-115">`EnumProperties` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="481de-116">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="481de-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="481de-117">In diesem Fall `pcProperties` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="481de-117">In that case, `pcProperties` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="481de-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="481de-118">Requirements</span></span>  
 <span data-ttu-id="481de-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="481de-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="481de-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="481de-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="481de-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="481de-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="481de-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="481de-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="481de-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="481de-123">See also</span></span>

- [<span data-ttu-id="481de-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="481de-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="481de-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="481de-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
