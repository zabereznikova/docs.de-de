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
ms.openlocfilehash: e766cec8fd84713e12c43cd1095650ed5b757bcb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175472"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="2e825-102">IMetaDataImport::EnumMethodImpls-Methode</span><span class="sxs-lookup"><span data-stu-id="2e825-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="2e825-103">Zählt MethodBody- und MethodDeclaration-Token auf, die Methoden des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="2e825-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e825-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e825-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdToken     rMethodBody[],
   [out]     mdToken     rMethodDecl[],
   [in]      ULONG       cMax,
   [in]      ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e825-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2e825-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2e825-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="2e825-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="2e825-107">Dies muss NULL für den ersten Aufruf dieser Methode sein.</span><span class="sxs-lookup"><span data-stu-id="2e825-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="2e825-108">[in] Ein TypeDef-Token für den Typ, dessen Methodenimplementierungen aufzuzählen sind.</span><span class="sxs-lookup"><span data-stu-id="2e825-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="2e825-109">[out] Das Array, das die MethodBody-Token speichert.</span><span class="sxs-lookup"><span data-stu-id="2e825-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="2e825-110">[out] Das Array, das die MethodDeclaration-Token speichert.</span><span class="sxs-lookup"><span data-stu-id="2e825-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2e825-111">[in] Die maximale Größe `rMethodBody` `rMethodDecl` der und der Arrays.</span><span class="sxs-lookup"><span data-stu-id="2e825-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="2e825-112">[in] Die tatsächliche Anzahl der `rMethodBody` `rMethodDecl`in und zurückgegebenen Methoden.</span><span class="sxs-lookup"><span data-stu-id="2e825-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2e825-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2e825-113">Return Value</span></span>  
  
|<span data-ttu-id="2e825-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2e825-114">HRESULT</span></span>|<span data-ttu-id="2e825-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e825-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2e825-116">`EnumMethodImpls`erfolgreich zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="2e825-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2e825-117">Es sind keine Methodentoken zum Aufzählen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="2e825-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="2e825-118">In diesem `pcTokens` Fall ist Null.</span><span class="sxs-lookup"><span data-stu-id="2e825-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e825-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2e825-119">Requirements</span></span>  
 <span data-ttu-id="2e825-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e825-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e825-121">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2e825-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2e825-122">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2e825-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2e825-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e825-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e825-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e825-124">See also</span></span>

- [<span data-ttu-id="2e825-125">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2e825-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2e825-126">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2e825-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
