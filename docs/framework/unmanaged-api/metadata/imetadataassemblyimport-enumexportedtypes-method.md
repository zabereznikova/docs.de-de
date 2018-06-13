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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9aef8c40be2456532bd6df6feb8d286cdaeefa7f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445630"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="81789-102">IMetaDataAssemblyImport::EnumExportedTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="81789-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="81789-103">Listet die exportierten Typen, die im Assemblymanifest im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="81789-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81789-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="81789-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81789-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="81789-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="81789-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="81789-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="81789-107">Dies muss ein NULL-Wert sein Wert der `EnumExportedTypes` Methode zum ersten Mal aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="81789-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="81789-108">[out] Die Enumeration von `mdExportedType` Metadatentoken verwendet.</span><span class="sxs-lookup"><span data-stu-id="81789-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="81789-109">[in] Die maximale Anzahl von `mdExportedType` Token, die in platziert werden, können die `rExportedTypes` Array.</span><span class="sxs-lookup"><span data-stu-id="81789-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="81789-110">[out] Die Anzahl der `mdExportedType` Token, die tatsächlich in `rExportedTypes`.</span><span class="sxs-lookup"><span data-stu-id="81789-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81789-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="81789-111">Return Value</span></span>  
  
|<span data-ttu-id="81789-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="81789-112">HRESULT</span></span>|<span data-ttu-id="81789-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81789-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="81789-114">`EnumExportedTypes` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="81789-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="81789-115">Es sind keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="81789-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="81789-116">In diesem Fall `pcTokens` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="81789-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81789-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="81789-117">Requirements</span></span>  
 <span data-ttu-id="81789-118">**Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81789-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81789-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="81789-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="81789-120">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="81789-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="81789-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81789-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81789-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81789-122">See Also</span></span>  
 [<span data-ttu-id="81789-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="81789-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
