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
ms.openlocfilehash: 18cd9dd14e615a7e76bfff30c9ae584305bd1907
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708937"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="06231-102">IMetaDataAssemblyImport::EnumAssemblyRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="06231-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>

<span data-ttu-id="06231-103">Listet die `mdAssemblyRef` im Assemblymanifest definierten-Instanzen auf.</span><span class="sxs-lookup"><span data-stu-id="06231-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06231-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="06231-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06231-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="06231-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="06231-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="06231-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="06231-107">Dies muss ein NULL-Wert sein, wenn die- `EnumAssemblyRefs` Methode zum ersten Mal aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="06231-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="06231-108">vorgenommen Die Enumeration von `mdAssemblyRef` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="06231-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="06231-109">in Die maximale Anzahl von Token, die in das Array eingefügt werden können `rAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="06231-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="06231-110">vorgenommen Die Anzahl der Token, die tatsächlich in platziert wurden `rAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="06231-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="06231-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="06231-111">Return Value</span></span>  
  
|<span data-ttu-id="06231-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="06231-112">HRESULT</span></span>|<span data-ttu-id="06231-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="06231-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="06231-114">`EnumAssemblyRefs` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="06231-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="06231-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="06231-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="06231-116">In diesem Fall `pcTokens` wird auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="06231-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06231-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="06231-117">Requirements</span></span>  

 <span data-ttu-id="06231-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06231-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06231-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="06231-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="06231-120">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="06231-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="06231-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06231-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06231-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="06231-122">See also</span></span>

- [<span data-ttu-id="06231-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="06231-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
