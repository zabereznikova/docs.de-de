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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4c998d70fa5dd41ab4c1656f129bb77767a8ab97
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574624"
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="ce127-102">IMetaDataEmit2::SetGenericParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="ce127-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="ce127-103">Legt Eigenschaftswerte für die generischen Parameter-Definition, die auf die verwiesen wird durch das angegebene Token fest.</span><span class="sxs-lookup"><span data-stu-id="ce127-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce127-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce127-104">Syntax</span></span>  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce127-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ce127-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="ce127-106">[in] Das Token für die Definition der generischen Parameter für die Werte festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ce127-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="ce127-107">[in] Der Wert der [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) -Enumeration, der den Typ für den generischen Parameter beschreibt.</span><span class="sxs-lookup"><span data-stu-id="ce127-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="ce127-108">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="ce127-108">[in] Optional.</span></span> <span data-ttu-id="ce127-109">Der Name des Parameters für die Werte festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ce127-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="ce127-110">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="ce127-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="ce127-111">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="ce127-111">[in] Optional.</span></span> <span data-ttu-id="ce127-112">Ein NULL-terminierte Array von Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="ce127-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="ce127-113">Arraymember muss ein `mdTypeDef`, `mdTypeRef`, oder `mdTypeSpec` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="ce127-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce127-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ce127-114">Requirements</span></span>  
 <span data-ttu-id="ce127-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce127-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce127-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ce127-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce127-117">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="ce127-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce127-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce127-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce127-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce127-119">See also</span></span>
- [<span data-ttu-id="ce127-120">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce127-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="ce127-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce127-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
