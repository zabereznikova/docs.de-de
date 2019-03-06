---
title: IMetaDataTables::GetCodedTokenInfo-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1a9eb51643271fd27a6d4795fc1729766b44b239
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468792"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="5d304-102">IMetaDataTables::GetCodedTokenInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="5d304-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="5d304-103">Ruft einen Zeiger auf ein Array von Token mit dem angegebenen Zeilenindex verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="5d304-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d304-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d304-104">Syntax</span></span>  
  
```  
HRESULT GetCodedTokenInfo (   
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d304-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5d304-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="5d304-106">[in] Die Art des codierten Token zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5d304-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="5d304-107">[out] Ein Zeiger auf die Länge des `ppTokens`.</span><span class="sxs-lookup"><span data-stu-id="5d304-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="5d304-108">[out] Ein Zeiger auf einen Zeiger auf ein Array, das die Liste der zurückgegebenen Token enthält.</span><span class="sxs-lookup"><span data-stu-id="5d304-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="5d304-109">[out] Ein Zeiger auf einen Zeiger auf den Namen des Tokens an `ixCdTkn`.</span><span class="sxs-lookup"><span data-stu-id="5d304-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d304-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5d304-110">Requirements</span></span>  
 <span data-ttu-id="5d304-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d304-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d304-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5d304-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d304-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="5d304-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5d304-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d304-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d304-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d304-115">See also</span></span>
- [<span data-ttu-id="5d304-116">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d304-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="5d304-117">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5d304-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
