---
title: IMetaDataTables::GetCodedTokenInfo-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetCodedTokenInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 72c88751940da16a691a5eae46507986a50904a4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="1d017-102">IMetaDataTables::GetCodedTokenInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="1d017-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="1d017-103">Ruft einen Zeiger auf ein Array von Token, die der Index der angegebenen Zeile zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1d017-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d017-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1d017-104">Syntax</span></span>  
  
```  
HRESULT GetCodedTokenInfo (   
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1d017-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1d017-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="1d017-106">[in] Die Art des codierten Token zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1d017-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="1d017-107">[out] Ein Zeiger auf die Länge des `ppTokens`.</span><span class="sxs-lookup"><span data-stu-id="1d017-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="1d017-108">[out] Ein Zeiger auf einen Zeiger auf ein Array, das die Liste der zurückgegebenen Token enthält.</span><span class="sxs-lookup"><span data-stu-id="1d017-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="1d017-109">[out] Ein Zeiger auf einen Zeiger auf den Namen des Tokens an `ixCdTkn`.</span><span class="sxs-lookup"><span data-stu-id="1d017-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d017-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1d017-110">Requirements</span></span>  
 <span data-ttu-id="1d017-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d017-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d017-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1d017-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d017-113">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="1d017-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d017-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d017-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d017-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1d017-115">See Also</span></span>  
 [<span data-ttu-id="1d017-116">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d017-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="1d017-117">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1d017-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
