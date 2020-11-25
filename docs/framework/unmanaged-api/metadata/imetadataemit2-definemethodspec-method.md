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
ms.openlocfilehash: 817b3a18b047bfca1f3a7c7099920a12e6253f58
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95712832"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="9662a-102">IMetaDataEmit2::DefineMethodSpec-Methode</span><span class="sxs-lookup"><span data-stu-id="9662a-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>

<span data-ttu-id="9662a-103">Erstellt eine generische Instanz einer Methode und ruft ein Token für die Definition ab.</span><span class="sxs-lookup"><span data-stu-id="9662a-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9662a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9662a-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9662a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9662a-105">Parameters</span></span>  

 `tkParent`  
 <span data-ttu-id="9662a-106">in Ein Token für die Methode, von der die generische Instanz erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9662a-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="9662a-107">Das Token muss den Typ `mdMethodDef` oder aufweisen `mdMemberRef` .</span><span class="sxs-lookup"><span data-stu-id="9662a-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="9662a-108">in Ein Zeiger auf die binäre com+-Signatur der Methode.</span><span class="sxs-lookup"><span data-stu-id="9662a-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="9662a-109">in Die Größe von in Bytes `pvSigBlob` .</span><span class="sxs-lookup"><span data-stu-id="9662a-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="9662a-110">vorgenommen Ein Token für die Metadatensignatur-Definition der Methode.</span><span class="sxs-lookup"><span data-stu-id="9662a-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9662a-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9662a-111">Requirements</span></span>  

 <span data-ttu-id="9662a-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9662a-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9662a-113">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="9662a-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9662a-114">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="9662a-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9662a-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9662a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9662a-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9662a-116">See also</span></span>

- [<span data-ttu-id="9662a-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9662a-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="9662a-118">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9662a-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
