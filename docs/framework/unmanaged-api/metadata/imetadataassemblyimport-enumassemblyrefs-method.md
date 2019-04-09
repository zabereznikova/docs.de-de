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
ms.openlocfilehash: 91e253669b9f51e7c1d600ba11f13a9ce67fb58a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072479"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="795b0-102">IMetaDataAssemblyImport::EnumAssemblyRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="795b0-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="795b0-103">Listet die `mdAssemblyRef` Instanzen, die im Assemblymanifest definiert sind.</span><span class="sxs-lookup"><span data-stu-id="795b0-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="795b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="795b0-104">Syntax</span></span>  
  
```  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,   
    [out]     mdAssemblyRef   rAssemblyRefs[],   
    [in]      ULONG           cMax,   
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="795b0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="795b0-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="795b0-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="795b0-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="795b0-107">Dies muss ein NULL-Wert sein Wert fest, wenn die `EnumAssemblyRefs` Methode zum ersten Mal aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="795b0-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="795b0-108">[out] Die Enumeration von `mdAssemblyRef` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="795b0-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="795b0-109">[in] Die maximale Anzahl von Token, die in platziert werden, kann die `rAssemblyRefs` Array.</span><span class="sxs-lookup"><span data-stu-id="795b0-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="795b0-110">[out] Die Anzahl der Token, die tatsächlich in `rAssemblyRefs`.</span><span class="sxs-lookup"><span data-stu-id="795b0-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="795b0-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="795b0-111">Return Value</span></span>  
  
|<span data-ttu-id="795b0-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="795b0-112">HRESULT</span></span>|<span data-ttu-id="795b0-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="795b0-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumAssemblyRefs` <span data-ttu-id="795b0-114">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="795b0-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="795b0-115">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="795b0-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="795b0-116">In diesem Fall `pcTokens` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="795b0-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="795b0-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="795b0-117">Requirements</span></span>  
 <span data-ttu-id="795b0-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="795b0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="795b0-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="795b0-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="795b0-120">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="795b0-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="795b0-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="795b0-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="795b0-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="795b0-122">See also</span></span>

- [<span data-ttu-id="795b0-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="795b0-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
