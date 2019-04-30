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
ms.openlocfilehash: b2ab06419491093a2de41d2ef25d16c01c03ebaf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905332"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="09d50-102">IMetaDataAssemblyImport::EnumFiles-Methode</span><span class="sxs-lookup"><span data-stu-id="09d50-102">IMetaDataAssemblyImport::EnumFiles Method</span></span>
<span data-ttu-id="09d50-103">Listet die Dateien, die in der aktuellen Assemblymanifest verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="09d50-103">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09d50-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="09d50-104">Syntax</span></span>  
  
```  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,   
    [out] mdFile          rFiles[],   
    [in]  ULONG           cMax,   
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09d50-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="09d50-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="09d50-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="09d50-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="09d50-107">Dies muss für den ersten Aufruf dieser Methode einen null-Wert sein.</span><span class="sxs-lookup"><span data-stu-id="09d50-107">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="09d50-108">[out] Das Array zum Speichern der `mdFile` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="09d50-108">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="09d50-109">[in] Die maximale Anzahl von `mdFile` Token, die in eingefügt werden können `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="09d50-109">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="09d50-110">[out] Die Anzahl der `mdFile` Token, die tatsächlich in `rFiles`.</span><span class="sxs-lookup"><span data-stu-id="09d50-110">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09d50-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="09d50-111">Return Value</span></span>  
  
|<span data-ttu-id="09d50-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="09d50-112">HRESULT</span></span>|<span data-ttu-id="09d50-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09d50-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="09d50-114">`EnumFiles` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="09d50-114">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="09d50-115">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="09d50-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="09d50-116">In diesem Fall `pcTokens` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="09d50-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09d50-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="09d50-117">Requirements</span></span>  
 <span data-ttu-id="09d50-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09d50-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09d50-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="09d50-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="09d50-120">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="09d50-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="09d50-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09d50-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09d50-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09d50-122">See also</span></span>

- [<span data-ttu-id="09d50-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="09d50-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
