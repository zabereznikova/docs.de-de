---
title: IMetaDataEmit2::DefineMethodSpec-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 85b17199ad40d8b3fbf4e1a0271828e5a5ac7991
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445259"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="e4600-102">IMetaDataEmit2::DefineMethodSpec-Methode</span><span class="sxs-lookup"><span data-stu-id="e4600-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="e4600-103">Erstellt eine generische Instanz einer Methode und ruft ein Token für die Definition.</span><span class="sxs-lookup"><span data-stu-id="e4600-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4600-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4600-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4600-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4600-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="e4600-106">[in] Ein Token für die Methode, von denen die generischen Instanz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e4600-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="e4600-107">Das Token muss vom Typ `mdMethodDef` oder `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="e4600-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="e4600-108">[in] Ein Zeiger auf die binäre COM+-Signatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="e4600-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="e4600-109">[in] Die Größe in Bytes, der `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="e4600-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="e4600-110">[out] Ein Token für die Metadatendefinition für die Signatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="e4600-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4600-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4600-111">Requirements</span></span>  
 <span data-ttu-id="e4600-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4600-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4600-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e4600-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e4600-114">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e4600-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e4600-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4600-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4600-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4600-116">See Also</span></span>  
 [<span data-ttu-id="e4600-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4600-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="e4600-118">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4600-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
