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
ms.openlocfilehash: 1beb76012d5f0351ee644c8dea89cabdbe2c8970
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555023"
---
# <a name="imetadataassemblyimportenumexportedtypes-method"></a><span data-ttu-id="a9d4b-102">IMetaDataAssemblyImport::EnumExportedTypes-Methode</span><span class="sxs-lookup"><span data-stu-id="a9d4b-102">IMetaDataAssemblyImport::EnumExportedTypes Method</span></span>
<span data-ttu-id="a9d4b-103">Listet die exportierten Typen in das Assemblymanifest im aktuellen Metadatenbereich verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a9d4b-103">Enumerates the exported types referenced in the assembly manifest in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9d4b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a9d4b-104">Syntax</span></span>  
  
```  
HRESULT EnumExportedTypes (  
    [in, out] HCORENUM     *phEnum,   
    [out] mdExportedType   rExportedTypes[],   
    [in]  ULONG            cMax,   
    [out] ULONG            *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9d4b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a9d4b-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="a9d4b-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="a9d4b-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="a9d4b-107">Dies muss ein NULL-Wert sein Wert fest, wenn die `EnumExportedTypes` Methode zum ersten Mal aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="a9d4b-107">This must be a null value when the `EnumExportedTypes` method is called for the first time.</span></span>  
  
 `rExportedTypes`  
 <span data-ttu-id="a9d4b-108">[out] Die Enumeration von `mdExportedType` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="a9d4b-108">[out] The enumeration of `mdExportedType` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="a9d4b-109">[in] Die maximale Anzahl von `mdExportedType` Token, die in platziert werden, können die `rExportedTypes` Array.</span><span class="sxs-lookup"><span data-stu-id="a9d4b-109">[in] The maximum number of `mdExportedType` tokens that can be placed in the `rExportedTypes` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a9d4b-110">[out] Die Anzahl der `mdExportedType` Token, die tatsächlich in `rExportedTypes`.</span><span class="sxs-lookup"><span data-stu-id="a9d4b-110">[out] The number of `mdExportedType` tokens actually placed in `rExportedTypes`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a9d4b-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a9d4b-111">Return Value</span></span>  
  
|<span data-ttu-id="a9d4b-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a9d4b-112">HRESULT</span></span>|<span data-ttu-id="a9d4b-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a9d4b-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="a9d4b-114">`EnumExportedTypes` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a9d4b-114">`EnumExportedTypes` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="a9d4b-115">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="a9d4b-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="a9d4b-116">In diesem Fall `pcTokens` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="a9d4b-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9d4b-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a9d4b-117">Requirements</span></span>  
 <span data-ttu-id="a9d4b-118">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9d4b-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9d4b-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a9d4b-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a9d4b-120">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a9d4b-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a9d4b-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9d4b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9d4b-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9d4b-122">See also</span></span>
- [<span data-ttu-id="a9d4b-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a9d4b-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
