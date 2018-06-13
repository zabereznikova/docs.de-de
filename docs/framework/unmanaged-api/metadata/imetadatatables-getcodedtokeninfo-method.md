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
ms.openlocfilehash: a7a36d14b67efb3934089dc16de41a3b80ea0c0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447989"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="0bf4a-102">IMetaDataTables::GetCodedTokenInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="0bf4a-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="0bf4a-103">Ruft einen Zeiger auf ein Array von Token, die der Index der angegebenen Zeile zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="0bf4a-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0bf4a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0bf4a-104">Syntax</span></span>  
  
```  
HRESULT GetCodedTokenInfo (   
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0bf4a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0bf4a-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="0bf4a-106">[in] Die Art des codierten Token zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0bf4a-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="0bf4a-107">[out] Ein Zeiger auf die Länge des `ppTokens`.</span><span class="sxs-lookup"><span data-stu-id="0bf4a-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="0bf4a-108">[out] Ein Zeiger auf einen Zeiger auf ein Array, das die Liste der zurückgegebenen Token enthält.</span><span class="sxs-lookup"><span data-stu-id="0bf4a-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="0bf4a-109">[out] Ein Zeiger auf einen Zeiger auf den Namen des Tokens an `ixCdTkn`.</span><span class="sxs-lookup"><span data-stu-id="0bf4a-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0bf4a-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0bf4a-110">Requirements</span></span>  
 <span data-ttu-id="0bf4a-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0bf4a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0bf4a-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0bf4a-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0bf4a-113">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="0bf4a-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0bf4a-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0bf4a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf4a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0bf4a-115">See Also</span></span>  
 [<span data-ttu-id="0bf4a-116">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0bf4a-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="0bf4a-117">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0bf4a-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
