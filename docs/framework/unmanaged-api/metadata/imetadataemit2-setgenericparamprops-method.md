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
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="2fdeb-102">IMetaDataEmit2::SetGenericParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="2fdeb-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="2fdeb-103">Legt Eigenschaftswerte für die generische Parameterdefinition fest, auf die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fdeb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fdeb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fdeb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2fdeb-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="2fdeb-106">in Das Token für die generische Parameterdefinition, für die Werte festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="2fdeb-107">in Ein Wert der [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) -Enumeration, der den Typ für den generischen Parameter beschreibt.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="2fdeb-108">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-108">[in] Optional.</span></span> <span data-ttu-id="2fdeb-109">Der Name des Parameters, für den Werte festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="2fdeb-110">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="2fdeb-111">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-111">[in] Optional.</span></span> <span data-ttu-id="2fdeb-112">Ein mit Null endendes Array von Typeinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="2fdeb-113">Array Elemente müssen ein `mdTypeDef`-, `mdTypeRef`-oder `mdTypeSpec` Metadatentoken sein.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fdeb-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2fdeb-114">Requirements</span></span>  
 <span data-ttu-id="2fdeb-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fdeb-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fdeb-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2fdeb-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2fdeb-117">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="2fdeb-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2fdeb-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fdeb-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fdeb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fdeb-119">See also</span></span>

- [<span data-ttu-id="2fdeb-120">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2fdeb-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="2fdeb-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2fdeb-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
