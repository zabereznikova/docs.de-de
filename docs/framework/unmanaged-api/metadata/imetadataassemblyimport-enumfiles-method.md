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
ms.openlocfilehash: ed8bafd67b5d55a5116111b7721fbdc31c52aca6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009094"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="270e2-102">IMetaDataAssemblyImport::EnumFiles-Methode</span><span class="sxs-lookup"><span data-stu-id="270e2-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="270e2-103">Listet die Dateien auf, auf die im aktuellen Assemblymanifest verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="270e2-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="270e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="270e2-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,
    [out] mdFile          rFiles[],
    [in]  ULONG           cMax,
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="270e2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="270e2-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="270e2-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="270e2-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="270e2-107">Dies muss ein NULL-Wert für den ersten-Rückruf dieser Methode sein.</span><span class="sxs-lookup"><span data-stu-id="270e2-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="270e2-108">vorgenommen Das Array, das zum Speichern der `mdFile` Metadatentoken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="270e2-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="270e2-109">in Die maximale Anzahl von `mdFile` Token, die in platziert werden können `rFiles` .</span><span class="sxs-lookup"><span data-stu-id="270e2-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="270e2-110">vorgenommen Die Anzahl der `mdFile` Token, die tatsächlich in platziert wurden `rFiles` .</span><span class="sxs-lookup"><span data-stu-id="270e2-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="270e2-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="270e2-111">Return Value</span></span>  
  
|<span data-ttu-id="270e2-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="270e2-112">HRESULT</span></span>|<span data-ttu-id="270e2-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="270e2-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="270e2-114">`EnumFiles`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="270e2-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="270e2-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="270e2-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="270e2-116">In diesem Fall `pcTokens` wird auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="270e2-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="270e2-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="270e2-117">Requirements</span></span>  
 <span data-ttu-id="270e2-118">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="270e2-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="270e2-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="270e2-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="270e2-120">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="270e2-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="270e2-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="270e2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="270e2-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="270e2-122">See also</span></span>

- [<span data-ttu-id="270e2-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="270e2-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
