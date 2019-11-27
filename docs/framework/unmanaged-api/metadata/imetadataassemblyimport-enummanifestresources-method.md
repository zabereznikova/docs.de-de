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
ms.openlocfilehash: 2748460826deb422a3851713db11343209fe449a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449552"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="c09f4-102">IMetaDataAssemblyImport::EnumManifestResources-Methode</span><span class="sxs-lookup"><span data-stu-id="c09f4-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="c09f4-103">Ruft einen Zeiger auf einen Enumerator für die Ressourcen ab, auf die im aktuellen Assemblymanifest verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c09f4-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c09f4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c09f4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="c09f4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c09f4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c09f4-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="c09f4-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c09f4-107">Dies muss ein NULL-Wert sein, wenn die `EnumManifestResources`-Methode zum ersten Mal aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="c09f4-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="c09f4-108">vorgenommen Das Array, das zum Speichern der `mdManifestResource` Metadatentoken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c09f4-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c09f4-109">in Die maximale Anzahl von `mdManifestResource` Token, die in `rManifestResources`platziert werden können.</span><span class="sxs-lookup"><span data-stu-id="c09f4-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c09f4-110">vorgenommen Die Anzahl der `mdManifestResource` Token, die tatsächlich in `rManifestResources`platziert wurden.</span><span class="sxs-lookup"><span data-stu-id="c09f4-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c09f4-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c09f4-111">Return Value</span></span>  
  
|<span data-ttu-id="c09f4-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c09f4-112">HRESULT</span></span>|<span data-ttu-id="c09f4-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c09f4-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c09f4-114">`EnumManifestResources` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c09f4-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c09f4-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="c09f4-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="c09f4-116">In diesem Fall wird `pcTokens` auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c09f4-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c09f4-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c09f4-117">Requirements</span></span>  
 <span data-ttu-id="c09f4-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c09f4-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c09f4-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c09f4-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c09f4-120">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="c09f4-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c09f4-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c09f4-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c09f4-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c09f4-122">See also</span></span>

- [<span data-ttu-id="c09f4-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c09f4-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
