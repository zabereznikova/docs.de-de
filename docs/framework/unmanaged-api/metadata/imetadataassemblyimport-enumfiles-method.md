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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 43a895446e0070476bde3d15d332f010265176e7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515036"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="7264e-102">IMetaDataAssemblyImport::EnumFiles-Methode</span><span class="sxs-lookup"><span data-stu-id="7264e-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="7264e-103">Listet die Dateien, die in der aktuellen Assemblymanifest verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="7264e-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7264e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7264e-104">Syntax</span></span>  
  
```  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7264e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7264e-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7264e-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="7264e-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7264e-107">Dies muss für den ersten Aufruf dieser Methode einen null-Wert sein.</span><span class="sxs-lookup"><span data-stu-id="7264e-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="7264e-108">[out] Das Array zum Speichern der `mdFile` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="7264e-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7264e-109">[in] Die maximale Anzahl von `mdFile` Token, die in eingefügt werden können `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="7264e-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="7264e-110">[out] Die Anzahl der `mdFile` Token, die tatsächlich in `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="7264e-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7264e-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7264e-111">Return Value</span></span>  
  
|<span data-ttu-id="7264e-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7264e-112">HRESULT</span></span>|<span data-ttu-id="7264e-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7264e-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7264e-114">`EnumFiles` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7264e-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7264e-115">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="7264e-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="7264e-116">In diesem Fall `pcTokens` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="7264e-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7264e-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7264e-117">Requirements</span></span>  
 <span data-ttu-id="7264e-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7264e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7264e-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7264e-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7264e-120">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="7264e-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7264e-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7264e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7264e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7264e-122">See also</span></span>
- [<span data-ttu-id="7264e-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7264e-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
