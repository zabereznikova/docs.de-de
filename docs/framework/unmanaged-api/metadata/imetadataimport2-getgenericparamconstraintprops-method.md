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
ms.openlocfilehash: 8beaea0b7493b7cea76466bb15355cfc5c6d5c7d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702705"
---
# <a name="imetadataimport2getgenericparamconstraintprops-method"></a><span data-ttu-id="dbdfa-102">IMetaDataImport2::GetGenericParamConstraintProps-Methode</span><span class="sxs-lookup"><span data-stu-id="dbdfa-102">IMetaDataImport2::GetGenericParamConstraintProps Method</span></span>

<span data-ttu-id="dbdfa-103">Ruft die Metadaten ab, die der durch das angegebene Einschränkungs Token dargestellten generischen Parameter Einschränkung zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="dbdfa-103">Gets the metadata associated with the generic parameter constraint represented by the specified constraint token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbdfa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dbdfa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamConstraintProps (  
   [in]  mdGenericParamConstraint  gpc,  
   [out] mdGenericParam            *ptGenericParam,  
   [out] mdToken                   *ptkConstraintType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbdfa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dbdfa-105">Parameters</span></span>  

 `gpc`  
 <span data-ttu-id="dbdfa-106">in Das Token für die generische Parameter Einschränkung, für die die Metadaten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="dbdfa-106">[in] The token to the generic parameter constraint for which to return the metadata.</span></span>  
  
 `ptGenericParam`  
 <span data-ttu-id="dbdfa-107">vorgenommen Ein Zeiger auf das Token, das den eingeschränkten generischen Parameter darstellt.</span><span class="sxs-lookup"><span data-stu-id="dbdfa-107">[out] A pointer to the token that represents the generic parameter that is constrained.</span></span>  
  
 `ptkConstraintType`  
 <span data-ttu-id="dbdfa-108">vorgenommen Ein Zeiger auf ein TypeDef-, TypeRef-oder TypeSpec-Token, das eine Einschränkung für darstellt `ptGenericParam` .</span><span class="sxs-lookup"><span data-stu-id="dbdfa-108">[out] A pointer to a TypeDef, TypeRef, or TypeSpec token that represents a constraint on `ptGenericParam`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbdfa-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dbdfa-109">Requirements</span></span>  

 <span data-ttu-id="dbdfa-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbdfa-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbdfa-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dbdfa-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dbdfa-112">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="dbdfa-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dbdfa-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbdfa-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbdfa-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dbdfa-114">See also</span></span>

- [<span data-ttu-id="dbdfa-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbdfa-115">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
- [<span data-ttu-id="dbdfa-116">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dbdfa-116">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
