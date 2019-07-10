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
ms.openlocfilehash: 81592b6da7fa7cdf275e9fa5b4b82ef0a15061c0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782569"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="eb330-102">IMetaDataImport::EnumTypeSpecs-Methode</span><span class="sxs-lookup"><span data-stu-id="eb330-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="eb330-103">Zählt TypeSpec-Token auf, die im aktuellen Metadatenbereich definiert sind.</span><span class="sxs-lookup"><span data-stu-id="eb330-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb330-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb330-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb330-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb330-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="eb330-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="eb330-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="eb330-107">Dieser Wert muss NULL für den ersten Aufruf dieser Methode sein.</span><span class="sxs-lookup"><span data-stu-id="eb330-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="eb330-108">[out] Das Array zum Speichern der TypeSpec-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="eb330-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="eb330-109">[in] Die maximale Größe des `rTypeSpecs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="eb330-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="eb330-110">[out] Die Anzahl der zurückgegebenen TypeSpec-Token `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="eb330-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb330-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="eb330-111">Return Value</span></span>  
  
|<span data-ttu-id="eb330-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eb330-112">HRESULT</span></span>|<span data-ttu-id="eb330-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb330-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="eb330-114">`EnumTypeSpecs` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="eb330-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="eb330-115">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="eb330-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="eb330-116">In diesem Fall `pcTypeSpecs` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="eb330-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb330-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eb330-117">Remarks</span></span>  
 <span data-ttu-id="eb330-118">Die TypeSpec-Token werden erstellt, indem die [IMetaDataEmit:: GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="eb330-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb330-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eb330-119">Requirements</span></span>  
 <span data-ttu-id="eb330-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb330-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb330-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eb330-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb330-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="eb330-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eb330-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb330-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb330-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb330-124">See also</span></span>

- [<span data-ttu-id="eb330-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb330-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="eb330-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb330-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
