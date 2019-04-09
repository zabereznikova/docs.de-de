---
title: IMetaDataImport::EnumModuleRefs-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumModuleRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumModuleRefs
helpviewer_keywords:
- EnumModuleRefs method [.NET Framework metadata]
- IMetaDataImport::EnumModuleRefs method [.NET Framework metadata]
ms.assetid: 53441f3a-68d2-477c-906e-37c55dfcfb4d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d66d24da05bc3b8f0c3d0a828456d7c61613d219
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188305"
---
# <a name="imetadataimportenummodulerefs-method"></a><span data-ttu-id="2f48b-102">IMetaDataImport::EnumModuleRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="2f48b-102">IMetaDataImport::EnumModuleRefs Method</span></span>
<span data-ttu-id="2f48b-103">Zählt ModuleRef-Token auf, die importierte Module darstellen.</span><span class="sxs-lookup"><span data-stu-id="2f48b-103">Enumerates ModuleRef tokens that represent imported modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f48b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f48b-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleRefs (  
   [in, out] HCORENUM     *phEnum,  
   [out]     mdModuleRef  rModuleRefs[],  
   [in]      ULONG        cMax,  
   [out]     ULONG        *pcModuleRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f48b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2f48b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2f48b-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="2f48b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="2f48b-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="2f48b-107">This must be NULL for the first call of this method.</span></span>  
  
 `rModuleRefs`  
 <span data-ttu-id="2f48b-108">[out] Das Array zum Speichern der ModuleRef-Token verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2f48b-108">[out] The array used to store the ModuleRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2f48b-109">[in] Die maximale Größe des `rModuleRefs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="2f48b-109">[in] The maximum size of the `rModuleRefs` array.</span></span>  
  
 `pcModuleRefs`  
 <span data-ttu-id="2f48b-110">[out] Die Anzahl der zurückgegebenen ModuleRef-Token `rModuleRefs`.</span><span class="sxs-lookup"><span data-stu-id="2f48b-110">[out] The number of ModuleRef tokens returned in `rModuleRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f48b-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2f48b-111">Return Value</span></span>  
  
|<span data-ttu-id="2f48b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2f48b-112">HRESULT</span></span>|<span data-ttu-id="2f48b-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2f48b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumModuleRefs` <span data-ttu-id="2f48b-114">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2f48b-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2f48b-115">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="2f48b-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="2f48b-116">In diesem Fall `pcModuleRefs` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="2f48b-116">In that case, `pcModuleRefs` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2f48b-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2f48b-117">Requirements</span></span>  
 <span data-ttu-id="2f48b-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f48b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f48b-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2f48b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2f48b-120">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2f48b-120">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="2f48b-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="2f48b-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2f48b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f48b-122">See also</span></span>

- [<span data-ttu-id="2f48b-123">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f48b-123">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2f48b-124">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f48b-124">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
