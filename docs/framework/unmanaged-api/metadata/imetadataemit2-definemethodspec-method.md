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
ms.openlocfilehash: ce6df232f3793b8b61d9fa7c18c9c90ca9fa3900
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184716"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="f06d8-102">IMetaDataEmit2::DefineMethodSpec-Methode</span><span class="sxs-lookup"><span data-stu-id="f06d8-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="f06d8-103">Erstellt eine generische Instanz einer Methode und ruft ein Token an der Definition ab.</span><span class="sxs-lookup"><span data-stu-id="f06d8-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f06d8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f06d8-104">Syntax</span></span>  
  
```  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f06d8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f06d8-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="f06d8-106">[in] Ein Token für die Methode, von dem die generische Instanz erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f06d8-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="f06d8-107">Das Token muss vom Typ `mdMethodDef` oder `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="f06d8-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="f06d8-108">[in] Ein Zeiger auf die binäre COM+-Signatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="f06d8-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="f06d8-109">[in] Die Größe in Bytes, des `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="f06d8-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="f06d8-110">[out] Ein Token für die Metadatendefinition für die Signatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="f06d8-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f06d8-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f06d8-111">Requirements</span></span>  
 <span data-ttu-id="f06d8-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f06d8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f06d8-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f06d8-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f06d8-114">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f06d8-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f06d8-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="f06d8-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f06d8-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f06d8-116">See also</span></span>

- [<span data-ttu-id="f06d8-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f06d8-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="f06d8-118">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f06d8-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
