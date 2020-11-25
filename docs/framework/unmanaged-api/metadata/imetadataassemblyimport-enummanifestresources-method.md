---
title: IMetaDataAssemblyImport::EnumManifestResources-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumManifestResources
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type:
- apiref
ms.openlocfilehash: c72e5b9544d1d8ae989405ac9bfdb22050b1aaaf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731608"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="3ec7e-102">IMetaDataAssemblyImport::EnumManifestResources-Methode</span><span class="sxs-lookup"><span data-stu-id="3ec7e-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>

<span data-ttu-id="3ec7e-103">Ruft einen Zeiger auf einen Enumerator für die Ressourcen ab, auf die im aktuellen Assemblymanifest verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3ec7e-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ec7e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3ec7e-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,
    [out] mdManifestResource   rManifestResources[],
    [in]  ULONG                cMax,
    [out] ULONG                *pcTokens  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="3ec7e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3ec7e-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="3ec7e-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="3ec7e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3ec7e-107">Dies muss ein NULL-Wert sein, wenn die- `EnumManifestResources` Methode zum ersten Mal aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="3ec7e-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="3ec7e-108">vorgenommen Das Array, das zum Speichern der `mdManifestResource` Metadatentoken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3ec7e-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3ec7e-109">in Die maximale Anzahl von `mdManifestResource` Token, die in platziert werden können `rManifestResources` .</span><span class="sxs-lookup"><span data-stu-id="3ec7e-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="3ec7e-110">vorgenommen Die Anzahl der `mdManifestResource` Token, die tatsächlich in platziert wurden `rManifestResources` .</span><span class="sxs-lookup"><span data-stu-id="3ec7e-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3ec7e-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3ec7e-111">Return Value</span></span>  
  
|<span data-ttu-id="3ec7e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3ec7e-112">HRESULT</span></span>|<span data-ttu-id="3ec7e-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3ec7e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3ec7e-114">`EnumManifestResources` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3ec7e-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3ec7e-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="3ec7e-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="3ec7e-116">In diesem Fall `pcTokens` wird auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="3ec7e-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3ec7e-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3ec7e-117">Requirements</span></span>  

 <span data-ttu-id="3ec7e-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ec7e-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ec7e-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3ec7e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3ec7e-120">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ec7e-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3ec7e-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ec7e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ec7e-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ec7e-122">See also</span></span>

- [<span data-ttu-id="3ec7e-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ec7e-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
