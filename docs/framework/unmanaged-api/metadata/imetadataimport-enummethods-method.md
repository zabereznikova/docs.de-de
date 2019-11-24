---
title: IMetaDataImport::EnumMethods-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 8e9e08ac903423b2e121f22cc9e43a660ccfac7b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450083"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="4a5c9-102">IMetaDataImport::EnumMethods-Methode</span><span class="sxs-lookup"><span data-stu-id="4a5c9-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="4a5c9-103">Zählt MethodDef-Token auf, die Methoden des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a5c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a5c9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a5c9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4a5c9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4a5c9-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="4a5c9-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="4a5c9-108">[in] A TypeDef token representing the type with the methods to enumerate.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="4a5c9-109">[out] The array to store the MethodDef tokens.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4a5c9-110">[in] The maximum size of the MethodDef `rMethods` array.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="4a5c9-111">[out] The number of MethodDef tokens returned in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a5c9-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4a5c9-112">Return Value</span></span>  
  
|<span data-ttu-id="4a5c9-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a5c9-113">HRESULT</span></span>|<span data-ttu-id="4a5c9-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4a5c9-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4a5c9-115">`EnumMethods` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4a5c9-116">There are no MethodDef tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="4a5c9-117">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="4a5c9-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a5c9-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4a5c9-118">Requirements</span></span>  
 <span data-ttu-id="4a5c9-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a5c9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a5c9-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4a5c9-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4a5c9-121">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4a5c9-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4a5c9-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a5c9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a5c9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a5c9-123">See also</span></span>

- [<span data-ttu-id="4a5c9-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a5c9-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4a5c9-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4a5c9-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
