---
title: IMetaDataImport::EnumTypeSpecs-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01151dc2fe6aa995285a34076527609816b2f3e8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205159"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="48208-102">IMetaDataImport::EnumTypeSpecs-Methode</span><span class="sxs-lookup"><span data-stu-id="48208-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="48208-103">Zählt TypeSpec-Token auf, die im aktuellen Metadatenbereich definiert sind.</span><span class="sxs-lookup"><span data-stu-id="48208-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48208-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="48208-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48208-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="48208-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="48208-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="48208-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="48208-107">Dieser Wert muss NULL für den ersten Aufruf dieser Methode sein.</span><span class="sxs-lookup"><span data-stu-id="48208-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="48208-108">[out] Das Array zum Speichern der TypeSpec-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="48208-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="48208-109">[in] Die maximale Größe des `rTypeSpecs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="48208-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="48208-110">[out] Die Anzahl der zurückgegebenen TypeSpec-Token `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="48208-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48208-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="48208-111">Return Value</span></span>  
  
|<span data-ttu-id="48208-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48208-112">HRESULT</span></span>|<span data-ttu-id="48208-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="48208-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeSpecs` <span data-ttu-id="48208-114">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="48208-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="48208-115">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="48208-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="48208-116">In diesem Fall `pcTypeSpecs` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="48208-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48208-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="48208-117">Remarks</span></span>  
 <span data-ttu-id="48208-118">Die TypeSpec-Token werden erstellt, indem die [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="48208-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48208-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="48208-119">Requirements</span></span>  
 <span data-ttu-id="48208-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48208-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48208-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="48208-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="48208-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="48208-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="48208-123">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="48208-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="48208-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="48208-124">See also</span></span>

- [<span data-ttu-id="48208-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48208-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="48208-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="48208-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
