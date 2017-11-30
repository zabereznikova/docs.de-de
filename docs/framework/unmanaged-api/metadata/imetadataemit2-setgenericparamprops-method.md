---
title: IMetaDataEmit2::SetGenericParamProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.SetGenericParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5de54b3d113c8d43bd004b18e0a6cb22b1051dc6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="4f8b8-102">IMetaDataEmit2::SetGenericParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="4f8b8-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="4f8b8-103">Legt Eigenschaftswerte für die Definition der generischen Parameter durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="4f8b8-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f8b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f8b8-104">Syntax</span></span>  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f8b8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4f8b8-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="4f8b8-106">[in] Das Token für die Definition der generischen Parameter für die Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4f8b8-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="4f8b8-107">[in] Der Wert der [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) -Enumeration, der den Typ für den generischen Parameter beschreibt.</span><span class="sxs-lookup"><span data-stu-id="4f8b8-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="4f8b8-108">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="4f8b8-108">[in] Optional.</span></span> <span data-ttu-id="4f8b8-109">Der Name des Parameters für die Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4f8b8-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="4f8b8-110">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="4f8b8-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="4f8b8-111">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="4f8b8-111">[in] Optional.</span></span> <span data-ttu-id="4f8b8-112">Ein Null endendes Array von typeinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="4f8b8-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="4f8b8-113">Arraymember muss ein `mdTypeDef`, `mdTypeRef`, oder `mdTypeSpec` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="4f8b8-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f8b8-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f8b8-114">Requirements</span></span>  
 <span data-ttu-id="4f8b8-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f8b8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f8b8-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4f8b8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f8b8-117">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4f8b8-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f8b8-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f8b8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f8b8-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f8b8-119">See Also</span></span>  
 [<span data-ttu-id="4f8b8-120">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f8b8-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="4f8b8-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4f8b8-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
