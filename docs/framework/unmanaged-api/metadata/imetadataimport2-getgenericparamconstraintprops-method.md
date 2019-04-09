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
ms.openlocfilehash: e0503c5bd924793df8143c89e358618fb8844c6c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215117"
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="5164a-102">IMetaDataImport2::GetGenericParamConstraintProps-Methode</span><span class="sxs-lookup"><span data-stu-id="5164a-102">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>
<span data-ttu-id="5164a-103">Ruft die Einschränkung des generischen Parameters, durch das Token der angegebenen Einschränkung dargestellt zugeordneten Metadaten ab.</span><span class="sxs-lookup"><span data-stu-id="5164a-103">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5164a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5164a-104">Syntax</span></span>  
  
```  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5164a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5164a-105">Parameters</span></span>  
 `gpc`  
 <span data-ttu-id="5164a-106">[in] Das Token für die Einschränkung der generischen Parameter für die die Metadaten zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="5164a-106">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="5164a-107">[out] Ein Zeiger auf das Token, das den generischen Parameter darstellt, der beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="5164a-107">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="5164a-108">[out] Ein Zeiger auf eine TypeDef, TypeRef oder TypeSpec-Token, die eine Einschränkung darstellt `ptGenericParam`.</span><span class="sxs-lookup"><span data-stu-id="5164a-108">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5164a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5164a-109">Requirements</span></span>  
 <span data-ttu-id="5164a-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5164a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5164a-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5164a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5164a-112">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="5164a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="5164a-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5164a-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5164a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5164a-114">See also</span></span>

- [<span data-ttu-id="5164a-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5164a-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="5164a-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5164a-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
