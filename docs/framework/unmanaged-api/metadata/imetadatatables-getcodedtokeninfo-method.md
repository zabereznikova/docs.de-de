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
ms.openlocfilehash: 11ab93e9cb4449ab77e5e9c4da81073aaf432382
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669691"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="a15cd-102">IMetaDataTables::GetCodedTokenInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="a15cd-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="a15cd-103">Ruft einen Zeiger auf ein Array von Token mit dem angegebenen Zeilenindex verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="a15cd-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a15cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a15cd-104">Syntax</span></span>  
  
```  
HRESULT GetCodedTokenInfo (   
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a15cd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a15cd-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="a15cd-106">[in] Die Art des codierten Token zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a15cd-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="a15cd-107">[out] Ein Zeiger auf die Länge des `ppTokens`.</span><span class="sxs-lookup"><span data-stu-id="a15cd-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="a15cd-108">[out] Ein Zeiger auf einen Zeiger auf ein Array, das die Liste der zurückgegebenen Token enthält.</span><span class="sxs-lookup"><span data-stu-id="a15cd-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="a15cd-109">[out] Ein Zeiger auf einen Zeiger auf den Namen des Tokens an `ixCdTkn`.</span><span class="sxs-lookup"><span data-stu-id="a15cd-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a15cd-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a15cd-110">Requirements</span></span>  
 <span data-ttu-id="a15cd-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a15cd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a15cd-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a15cd-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a15cd-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a15cd-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a15cd-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a15cd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a15cd-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a15cd-115">See also</span></span>
- [<span data-ttu-id="a15cd-116">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a15cd-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="a15cd-117">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a15cd-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
