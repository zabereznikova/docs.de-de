---
title: IMetaDataEmit2::SetGenericParamProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
ms.openlocfilehash: 7a93bbe0d7a9d9e6ff7505bbc215efa79176ad1f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440437"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="92e0c-102">IMetaDataEmit2::SetGenericParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="92e0c-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="92e0c-103">Sets property values for the generic parameter definition referenced by the specified token.</span><span class="sxs-lookup"><span data-stu-id="92e0c-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92e0c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="92e0c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="92e0c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="92e0c-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="92e0c-106">[in] The token for the generic parameter definition for which to set values.</span><span class="sxs-lookup"><span data-stu-id="92e0c-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="92e0c-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span><span class="sxs-lookup"><span data-stu-id="92e0c-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="92e0c-108">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="92e0c-108">[in] Optional.</span></span> <span data-ttu-id="92e0c-109">The name of the parameter for which to set values.</span><span class="sxs-lookup"><span data-stu-id="92e0c-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="92e0c-110">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="92e0c-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="92e0c-111">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="92e0c-111">[in] Optional.</span></span> <span data-ttu-id="92e0c-112">A zero-terminated array of type constraints.</span><span class="sxs-lookup"><span data-stu-id="92e0c-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="92e0c-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span><span class="sxs-lookup"><span data-stu-id="92e0c-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92e0c-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92e0c-114">Requirements</span></span>  
 <span data-ttu-id="92e0c-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92e0c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92e0c-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="92e0c-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92e0c-117">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="92e0c-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="92e0c-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92e0c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92e0c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92e0c-119">See also</span></span>

- [<span data-ttu-id="92e0c-120">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92e0c-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="92e0c-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="92e0c-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
