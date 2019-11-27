---
title: IMetaDataAssemblyImport::EnumFiles-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
ms.openlocfilehash: e4549789ea1af584c0850a535d9f6bb54f844ce0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443547"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="6035b-102">IMetaDataAssemblyImport::EnumFiles-Methode</span><span class="sxs-lookup"><span data-stu-id="6035b-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="6035b-103">Listet die Dateien auf, auf die im aktuellen Assemblymanifest verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="6035b-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6035b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6035b-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6035b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6035b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6035b-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="6035b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6035b-107">Dies muss ein NULL-Wert für den ersten-Rückruf dieser Methode sein.</span><span class="sxs-lookup"><span data-stu-id="6035b-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="6035b-108">vorgenommen Das Array, das zum Speichern der `mdFile` Metadatentoken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6035b-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6035b-109">in Die maximale Anzahl von `mdFile` Token, die in `rFiles`platziert werden können.</span><span class="sxs-lookup"><span data-stu-id="6035b-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6035b-110">vorgenommen Die Anzahl der `mdFile` Token, die tatsächlich in `rFiles`platziert wurden.</span><span class="sxs-lookup"><span data-stu-id="6035b-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6035b-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="6035b-111">Return Value</span></span>  
  
|<span data-ttu-id="6035b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6035b-112">HRESULT</span></span>|<span data-ttu-id="6035b-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6035b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6035b-114">`EnumFiles` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6035b-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6035b-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="6035b-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="6035b-116">In diesem Fall wird `pcTokens` auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6035b-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6035b-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6035b-117">Requirements</span></span>  
 <span data-ttu-id="6035b-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6035b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6035b-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6035b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6035b-120">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="6035b-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6035b-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6035b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6035b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6035b-122">See also</span></span>

- [<span data-ttu-id="6035b-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6035b-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
