---
title: IMetaDataAssemblyImport::EnumAssemblyRefs-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumAssemblyRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumAssemblyRefs method [.NET Framework metadata]
- EnumAssemblyRefs method [.NET Framework metadata]
ms.assetid: 8844d0dd-730e-4592-8a7b-c1462d312c70
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a56d874e5e7ef491c24b0aef2ace700087de677
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447410"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="ea225-102">IMetaDataAssemblyImport::EnumAssemblyRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="ea225-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="ea225-103">Listet die `mdAssemblyRef` Instanzen, die im Assemblymanifest definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ea225-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea225-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea225-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea225-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ea225-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="ea225-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="ea225-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="ea225-107">Dies muss ein NULL-Wert sein Wert der `EnumAssemblyRefs` Methode zum ersten Mal aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="ea225-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="ea225-108">[out] Die Enumeration von `mdAssemblyRef` Metadatentoken verwendet.</span><span class="sxs-lookup"><span data-stu-id="ea225-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="ea225-109">[in] Die maximale Anzahl von Token, die in platziert werden, kann die `rAssemblyRefs` Array.</span><span class="sxs-lookup"><span data-stu-id="ea225-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="ea225-110">[out] Die Anzahl der Token, die tatsächlich in `rAssemblyRefs`.</span><span class="sxs-lookup"><span data-stu-id="ea225-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ea225-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ea225-111">Return Value</span></span>  
  
|<span data-ttu-id="ea225-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ea225-112">HRESULT</span></span>|<span data-ttu-id="ea225-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ea225-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="ea225-114">`EnumAssemblyRefs` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ea225-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="ea225-115">Es sind keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="ea225-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="ea225-116">In diesem Fall `pcTokens` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ea225-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ea225-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ea225-117">Requirements</span></span>  
 <span data-ttu-id="ea225-118">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea225-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea225-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ea225-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea225-120">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="ea225-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea225-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea225-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea225-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea225-122">See Also</span></span>  
 [<span data-ttu-id="ea225-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea225-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
