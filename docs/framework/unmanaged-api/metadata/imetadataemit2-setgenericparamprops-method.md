---
title: IMetaDataEmit2::SetGenericParamProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6e8e0720934fa9d7ec3669fa1cef7ac3ef9aedaa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemit2setgenericparamprops-method"></a><span data-ttu-id="49f93-102">IMetaDataEmit2::SetGenericParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="49f93-102">IMetaDataEmit2::SetGenericParamProps Method</span></span>
<span data-ttu-id="49f93-103">Legt Eigenschaftswerte für die Definition der generischen Parameter durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="49f93-103">Sets property values for the generic parameter definition referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49f93-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49f93-104">Syntax</span></span>  
  
```  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,   
    [in] DWORD            dwParamFlags,   
    [in] LPCWSTR          szName,   
    [in] DWORD            reserved,   
    [in] mdToken          rtkConstraints[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49f93-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="49f93-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="49f93-106">[in] Das Token für die Definition der generischen Parameter für die Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="49f93-106">[in] The token for the generic parameter definition for which to set values.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="49f93-107">[in] Der Wert der [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) -Enumeration, der den Typ für den generischen Parameter beschreibt.</span><span class="sxs-lookup"><span data-stu-id="49f93-107">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="49f93-108">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="49f93-108">[in] Optional.</span></span> <span data-ttu-id="49f93-109">Der Name des Parameters für die Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="49f93-109">The name of the parameter for which to set values.</span></span>  
  
 `reserved`  
 <span data-ttu-id="49f93-110">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="49f93-110">[in] Reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="49f93-111">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="49f93-111">[in] Optional.</span></span> <span data-ttu-id="49f93-112">Ein Null endendes Array von typeinschränkungen.</span><span class="sxs-lookup"><span data-stu-id="49f93-112">A zero-terminated array of type constraints.</span></span> <span data-ttu-id="49f93-113">Arraymember muss ein `mdTypeDef`, `mdTypeRef`, oder `mdTypeSpec` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="49f93-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49f93-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49f93-114">Requirements</span></span>  
 <span data-ttu-id="49f93-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49f93-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49f93-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="49f93-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49f93-117">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="49f93-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49f93-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49f93-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f93-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49f93-119">See Also</span></span>  
 [<span data-ttu-id="49f93-120">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49f93-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="49f93-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49f93-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
