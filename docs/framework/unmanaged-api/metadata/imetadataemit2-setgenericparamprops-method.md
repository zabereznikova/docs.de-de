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
ms.openlocfilehash: 8858e692d66f7b34a66334bd4e8b906dd12962ba
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701990"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="b2437-102">IMetaDataEmit2::SetGenericParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="b2437-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>

<span data-ttu-id="b2437-103">Legt Eigenschaftswerte für die generische Parameterdefinition fest, auf die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b2437-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2437-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2437-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2437-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b2437-105">Parameters</span></span>  

 `gp`  
 <span data-ttu-id="b2437-106">in Das Token für die generische Parameterdefinition, für die Werte festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b2437-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="b2437-107">in Ein Wert der [CorGenericParamAttr](corgenericparamattr-enumeration.md) -Enumeration, der den Typ für den generischen Parameter beschreibt.</span><span class="sxs-lookup"><span data-stu-id="b2437-107">[in] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="b2437-108">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="b2437-108">[in] Optional.</span></span> <span data-ttu-id="b2437-109">Der Name des Parameters, für den Werte festgelegt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b2437-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="b2437-110">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="b2437-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="b2437-111">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="b2437-111">[in] Optional.</span></span> <span data-ttu-id="b2437-112">Ein mit Null endendes Array von Typeinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="b2437-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="b2437-113">Array Elemente müssen ein- `mdTypeDef` ,- `mdTypeRef` oder- `mdTypeSpec` Metadatentoken sein.</span><span class="sxs-lookup"><span data-stu-id="b2437-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2437-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b2437-114">Requirements</span></span>  

 <span data-ttu-id="b2437-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2437-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2437-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b2437-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b2437-117">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="b2437-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b2437-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2437-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2437-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2437-119">See also</span></span>

- [<span data-ttu-id="b2437-120">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b2437-120">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="b2437-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b2437-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
