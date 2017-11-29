---
title: IMetaDataAssemblyImport::EnumManifestResources-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.EnumManifestResources
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 25d8b63e2f40566164274715e562960eafbb83e5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="49810-102">IMetaDataAssemblyImport::EnumManifestResources-Methode</span><span class="sxs-lookup"><span data-stu-id="49810-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="49810-103">Ruft einen Zeiger auf einem Enumerator für die Ressourcen, die im aktuellen Assemblymanifest verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="49810-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49810-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49810-104">Syntax</span></span>  
  
```  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="49810-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="49810-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="49810-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="49810-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="49810-107">Dies muss ein NULL-Wert sein Wert der `EnumManifestResources` Methode zum ersten Mal aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="49810-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="49810-108">[out] Das Array zum Speichern der `mdManifestResource` Metadatentoken verwendet.</span><span class="sxs-lookup"><span data-stu-id="49810-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="49810-109">[in] Die maximale Anzahl von `mdManifestResource` Token, die im gespeichert werden können `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="49810-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="49810-110">[out] Die Anzahl der `mdManifestResource` Token, die tatsächlich in `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="49810-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="49810-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="49810-111">Return Value</span></span>  
  
|<span data-ttu-id="49810-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="49810-112">HRESULT</span></span>|<span data-ttu-id="49810-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="49810-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="49810-114">`EnumManifestResources`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="49810-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="49810-115">Es sind keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="49810-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="49810-116">In diesem Fall `pcTokens` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="49810-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="49810-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49810-117">Requirements</span></span>  
 <span data-ttu-id="49810-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49810-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49810-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="49810-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49810-120">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="49810-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49810-121">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49810-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49810-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49810-122">See Also</span></span>  
 [<span data-ttu-id="49810-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49810-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
