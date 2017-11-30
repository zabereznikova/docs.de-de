---
title: IMetaDataImport2::GetGenericParamConstraintProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetGenericParamConstraintProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7d1e560dd511758652e1acbc262b4ddc3efdd12c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="af721-102">IMetaDataImport2::GetGenericParamConstraintProps-Methode</span><span class="sxs-lookup"><span data-stu-id="af721-102">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>
<span data-ttu-id="af721-103">Ruft die Einschränkung des generischen Parameters, durch die angegebene Einschränkung-Token dargestellt wird zugeordneten Metadaten ab.</span><span class="sxs-lookup"><span data-stu-id="af721-103">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af721-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af721-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af721-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="af721-105">Parameters</span></span>  
 `gpc`  
 <span data-ttu-id="af721-106">[in] Das Token für die Einschränkung der generischen Parameter für die die Metadaten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="af721-106">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="af721-107">[out] Ein Zeiger auf das Token, das den generischen Parameter darstellt, der eingeschränkt wird.</span><span class="sxs-lookup"><span data-stu-id="af721-107">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="af721-108">[out] Ein Zeiger auf eine TypeDef, TypeRef-Token oder TypeSpec-Token, die eine Einschränkung auf darstellt `ptGenericParam`.</span><span class="sxs-lookup"><span data-stu-id="af721-108">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af721-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af721-109">Requirements</span></span>  
 <span data-ttu-id="af721-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af721-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af721-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="af721-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="af721-112">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="af721-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="af721-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af721-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af721-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af721-114">See Also</span></span>  
 [<span data-ttu-id="af721-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af721-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [<span data-ttu-id="af721-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af721-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
