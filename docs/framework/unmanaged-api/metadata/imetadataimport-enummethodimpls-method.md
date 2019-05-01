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
ms.openlocfilehash: 09bd9f4029f5e4609ab1ef6f49a4364e83f1edfb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049907"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="7869f-102">IMetaDataImport::EnumMethodImpls-Methode</span><span class="sxs-lookup"><span data-stu-id="7869f-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="7869f-103">Zählt MethodBody- und MethodDeclaration-Token auf, die Methoden des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="7869f-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7869f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7869f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="7869f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7869f-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7869f-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="7869f-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7869f-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="7869f-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="7869f-108">[in] Eine TypeDef-token für den Typ, dessen methodenimplementierungen aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="7869f-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="7869f-109">[out] Das Array zum Speichern der MethodBody--Token.</span><span class="sxs-lookup"><span data-stu-id="7869f-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="7869f-110">[out] Das Array zum Speichern der MethodDeclaration-Token.</span><span class="sxs-lookup"><span data-stu-id="7869f-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7869f-111">[in] Die maximale Größe der `rMethodBody` und `rMethodDecl` Arrays.</span><span class="sxs-lookup"><span data-stu-id="7869f-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="7869f-112">[in] Die tatsächliche Anzahl von Methoden, die in zurückgegebenen `rMethodBody` und `rMethodDecl`.</span><span class="sxs-lookup"><span data-stu-id="7869f-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7869f-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7869f-113">Return Value</span></span>  
  
|<span data-ttu-id="7869f-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7869f-114">HRESULT</span></span>|<span data-ttu-id="7869f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7869f-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7869f-116">`EnumMethodImpls` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7869f-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7869f-117">Es gibt keine Methodentoken aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="7869f-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="7869f-118">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="7869f-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7869f-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7869f-119">Requirements</span></span>  
 <span data-ttu-id="7869f-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7869f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7869f-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7869f-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7869f-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7869f-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7869f-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7869f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7869f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7869f-124">See also</span></span>

- [<span data-ttu-id="7869f-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7869f-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7869f-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7869f-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
