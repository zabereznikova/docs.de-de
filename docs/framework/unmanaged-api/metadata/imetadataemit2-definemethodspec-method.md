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
ms.openlocfilehash: a5d9342b8bfe650106ccf9daf2a91dfbcd575446
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175538"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="2f663-102">IMetaDataEmit2::DefineMethodSpec-Methode</span><span class="sxs-lookup"><span data-stu-id="2f663-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="2f663-103">Erstellt eine generische Instanz einer Methode und ruft ein Token für die Definition ab.</span><span class="sxs-lookup"><span data-stu-id="2f663-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f663-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2f663-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f663-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2f663-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="2f663-106">[in] Ein Token für die Methode, deren generische Instanz erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f663-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="2f663-107">Das Token muss `mdMethodDef` vom `mdMemberRef`Typ oder sein.</span><span class="sxs-lookup"><span data-stu-id="2f663-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="2f663-108">[in] Ein Zeiger auf die binäre COM+-Signatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="2f663-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="2f663-109">[in] Die Größe von in `pvSigBlob`Bytes von .</span><span class="sxs-lookup"><span data-stu-id="2f663-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="2f663-110">[out] Ein Token für die Metadatensignaturdefinition der Methode.</span><span class="sxs-lookup"><span data-stu-id="2f663-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f663-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="2f663-111">Requirements</span></span>  
 <span data-ttu-id="2f663-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f663-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f663-113">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2f663-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2f663-114">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2f663-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2f663-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f663-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f663-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f663-116">See also</span></span>

- [<span data-ttu-id="2f663-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f663-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="2f663-118">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2f663-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
