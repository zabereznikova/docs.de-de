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
ms.openlocfilehash: 45e2348b4726447548544d975e60b93e464fb402
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450331"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="b180a-102">IMetaDataAssemblyImport::EnumExportedTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="b180a-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="b180a-103">Listet die exportierten Typen auf, auf die im Assemblymanifest im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b180a-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b180a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b180a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b180a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b180a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="b180a-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="b180a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b180a-107">Dies muss ein NULL-Wert sein, wenn die `EnumExportedTypes`-Methode zum ersten Mal aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="b180a-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="b180a-108">vorgenommen Die Enumeration von `mdExportedType` Metadatentokens.</span><span class="sxs-lookup"><span data-stu-id="b180a-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b180a-109">in Die maximale Anzahl von `mdExportedType` Token, die im `rExportedTypes` Array platziert werden können.</span><span class="sxs-lookup"><span data-stu-id="b180a-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b180a-110">vorgenommen Die Anzahl der `mdExportedType` Token, die tatsächlich in `rExportedTypes`platziert wurden.</span><span class="sxs-lookup"><span data-stu-id="b180a-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b180a-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b180a-111">Return Value</span></span>  
  
|<span data-ttu-id="b180a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b180a-112">HRESULT</span></span>|<span data-ttu-id="b180a-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b180a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b180a-114">`EnumExportedTypes` erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b180a-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b180a-115">Es sind keine Token zum Auflisten vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b180a-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="b180a-116">In diesem Fall wird `pcTokens` auf 0 (null) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b180a-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b180a-117">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b180a-117">Requirements</span></span>  
 <span data-ttu-id="b180a-118">**Plattform:** Siehe [System Anforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b180a-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b180a-119">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b180a-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b180a-120">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="b180a-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b180a-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b180a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b180a-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b180a-122">See also</span></span>

- [<span data-ttu-id="b180a-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b180a-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
