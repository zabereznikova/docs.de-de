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
ms.openlocfilehash: 1b9700455da82fc7f4a39d4c208ac0b18ef79722
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009118"
---
# <a name="imetadataassemblyimportenumassemblyrefs-method"></a><span data-ttu-id="611a2-102">IMetaDataAssemblyImport::EnumAssemblyRefs-Methode</span><span class="sxs-lookup"><span data-stu-id="611a2-102">IMetaDataAssemblyImport::EnumAssemblyRefs Method</span></span>
<span data-ttu-id="611a2-103">Listet die `mdAssemblyRef` im Assemblymanifest definierten-Instanzen auf.</span><span class="sxs-lookup"><span data-stu-id="611a2-103">Enumerates the `mdAssemblyRef` instances that are defined in the assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="611a2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="611a2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumAssemblyRefs (  
    [in, out] HCORENUM        *phEnum,
    [out]     mdAssemblyRef   rAssemblyRefs[],
    [in]      ULONG           cMax,
    [out]     ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="611a2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="611a2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="611a2-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="611a2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="611a2-107">Dies muss ein NULL-Wert sein, wenn die- `EnumAssemblyRefs` Methode zum ersten Mal aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="611a2-107">This must be a null value when the `EnumAssemblyRefs` method is called for the first time.</span></span>  
  
 `rAssemblyRefs`  
 <span data-ttu-id="611a2-108">vorgenommen Die Enumeration von `mdAssemblyRef` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="611a2-108">[out] The enumeration of `mdAssemblyRef` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="611a2-109">in Die maximale Anzahl von Token, die in das Array eingefügt werden können `rAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="611a2-109">[in] The maximum number of tokens that can be placed in the `rAssemblyRefs` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="611a2-110">vorgenommen Die Anzahl der Token, die tatsächlich in platziert wurden `rAssemblyRefs` .</span><span class="sxs-lookup"><span data-stu-id="611a2-110">[out] The number of tokens actually placed in `rAssemblyRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="611a2-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="611a2-111">Return Value</span></span>  
  
|<span data-ttu-id="611a2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="611a2-112">HRESULT</span></span>|<span data-ttu-id="611a2-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="611a2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="611a2-114">`EnumAssemblyRefs`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="611a2-114">`EnumAssemblyRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="611a2-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="611a2-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="611a2-116">In diesem Fall `pcTokens` wird auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="611a2-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="611a2-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="611a2-117">Requirements</span></span>  
 <span data-ttu-id="611a2-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="611a2-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="611a2-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="611a2-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="611a2-120">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="611a2-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="611a2-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="611a2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="611a2-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="611a2-122">See also</span></span>

- [<span data-ttu-id="611a2-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="611a2-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
