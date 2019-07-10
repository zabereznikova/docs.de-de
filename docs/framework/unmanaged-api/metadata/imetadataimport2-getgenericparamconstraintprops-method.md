---
title: IMetaDataImport2::GetGenericParamConstraintProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamConstraintProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamConstraintProps method [.NET Framework metadata]
- GetGenericParamConstraintProps method [.NET Framework metadata]
ms.assetid: c5fee4a0-b132-4e5e-8730-e586ce314b9a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e3868b07ff01f2d1fec79537dd478a2d005f490f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778768"
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="e257b-102">IMetaDataImport2::GetGenericParamConstraintProps-Methode</span><span class="sxs-lookup"><span data-stu-id="e257b-102">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>
<span data-ttu-id="e257b-103">Ruft die Einschränkung des generischen Parameters, durch das Token der angegebenen Einschränkung dargestellt zugeordneten Metadaten ab.</span><span class="sxs-lookup"><span data-stu-id="e257b-103">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e257b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e257b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e257b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e257b-105">Parameters</span></span>  
 `gpc`  
 <span data-ttu-id="e257b-106">[in] Das Token für die Einschränkung der generischen Parameter für die die Metadaten zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="e257b-106">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="e257b-107">[out] Ein Zeiger auf das Token, das den generischen Parameter darstellt, der beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="e257b-107">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="e257b-108">[out] Ein Zeiger auf eine TypeDef, TypeRef oder TypeSpec-Token, die eine Einschränkung darstellt `ptGenericParam`.</span><span class="sxs-lookup"><span data-stu-id="e257b-108">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e257b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e257b-109">Requirements</span></span>  
 <span data-ttu-id="e257b-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e257b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e257b-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e257b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e257b-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e257b-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e257b-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e257b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e257b-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e257b-114">See also</span></span>

- [<span data-ttu-id="e257b-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e257b-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="e257b-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e257b-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
