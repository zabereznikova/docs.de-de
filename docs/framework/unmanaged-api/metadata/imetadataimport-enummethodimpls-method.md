---
title: IMetaDataImport::EnumMethodImpls-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: aebfd41a232a3284f79e4229a8845bf5a34f9d1f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54574767"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="c2675-102">IMetaDataImport::EnumMethodImpls-Methode</span><span class="sxs-lookup"><span data-stu-id="c2675-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="c2675-103">Zählt MethodBody- und MethodDeclaration-Token auf, die Methoden des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="c2675-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2675-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2675-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,   
   [in]      mdTypeDef   td,   
   [out]     mdToken     rMethodBody[],   
   [out]     mdToken     rMethodDecl[],   
   [in]      ULONG       cMax,   
   [in]      ULONG       *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2675-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2675-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c2675-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="c2675-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c2675-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="c2675-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="c2675-108">[in] Eine TypeDef-token für den Typ, dessen methodenimplementierungen aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="c2675-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="c2675-109">[out] Das Array zum Speichern der MethodBody--Token.</span><span class="sxs-lookup"><span data-stu-id="c2675-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="c2675-110">[out] Das Array zum Speichern der MethodDeclaration-Token.</span><span class="sxs-lookup"><span data-stu-id="c2675-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c2675-111">[in] Die maximale Größe der `rMethodBody` und `rMethodDecl` Arrays.</span><span class="sxs-lookup"><span data-stu-id="c2675-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c2675-112">[in] Die tatsächliche Anzahl von Methoden, die in zurückgegebenen `rMethodBody` und `rMethodDecl`.</span><span class="sxs-lookup"><span data-stu-id="c2675-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c2675-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c2675-113">Return Value</span></span>  
  
|<span data-ttu-id="c2675-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c2675-114">HRESULT</span></span>|<span data-ttu-id="c2675-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c2675-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c2675-116">`EnumMethodImpls` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c2675-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c2675-117">Es gibt keine Methodentoken aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="c2675-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="c2675-118">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="c2675-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2675-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2675-119">Requirements</span></span>  
 <span data-ttu-id="c2675-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2675-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2675-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c2675-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2675-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c2675-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2675-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2675-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2675-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2675-124">See also</span></span>
- [<span data-ttu-id="c2675-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2675-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c2675-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c2675-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
