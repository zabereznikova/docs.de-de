---
title: IMetaDataAssemblyImport::EnumExportedTypes-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumExportedTypes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumExportedTypes
helpviewer_keywords:
- EnumExportedTypes method [.NET Framework metadata]
- IMetaDataAssemblyImport::EnumExportedTypes method [.NET Framework metadata]
ms.assetid: e5912ed8-e4ce-438b-8ea3-d9e4c288d109
topic_type:
- apiref
ms.openlocfilehash: a8b2377c48331ff9f0e69876c51fb78c7190f694
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708893"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="93372-102">IMetaDataAssemblyImport::EnumExportedTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="93372-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>

<span data-ttu-id="93372-103">Listet die exportierten Typen auf, auf die im Assemblymanifest im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="93372-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93372-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="93372-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,
    [out] mdExportedType   rExportedTypes[],
    [in]  ULONG            cMax,
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="93372-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="93372-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="93372-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="93372-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="93372-107">Dies muss ein NULL-Wert sein, wenn die- `EnumExportedTypes` Methode zum ersten Mal aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="93372-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="93372-108">vorgenommen Die Enumeration von `mdExportedType` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="93372-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="93372-109">in Die maximale Anzahl von `mdExportedType` Token, die in das Array eingefügt werden können `rExportedTypes` .</span><span class="sxs-lookup"><span data-stu-id="93372-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="93372-110">vorgenommen Die Anzahl der `mdExportedType` Token, die tatsächlich in platziert wurden `rExportedTypes` .</span><span class="sxs-lookup"><span data-stu-id="93372-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="93372-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="93372-111">Return Value</span></span>  
  
|<span data-ttu-id="93372-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="93372-112">HRESULT</span></span>|<span data-ttu-id="93372-113">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="93372-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="93372-114">`EnumExportedTypes` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="93372-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="93372-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="93372-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="93372-116">In diesem Fall `pcTokens` wird auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="93372-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="93372-117">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="93372-117">Requirements</span></span>  

 <span data-ttu-id="93372-118">**Plattform:** Siehe [System Anforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93372-118">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93372-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="93372-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="93372-120">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="93372-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="93372-121">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93372-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93372-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="93372-122">See also</span></span>

- [<span data-ttu-id="93372-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="93372-123">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
