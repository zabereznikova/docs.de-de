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
ms.openlocfilehash: 64c70fe0b657047ae35dccb763fa57120403deef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177152"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="85891-102">IMetaDataTables::GetCodedTokenInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="85891-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="85891-103">Ruft einen Zeiger auf ein Array von Token ab, die dem angegebenen Zeilenindex zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="85891-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85891-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="85891-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85891-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="85891-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="85891-106">[in] Die Art des zurückzugebenden codierten Tokens.</span><span class="sxs-lookup"><span data-stu-id="85891-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="85891-107">[out] Ein Zeiger auf die `ppTokens`Länge von .</span><span class="sxs-lookup"><span data-stu-id="85891-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="85891-108">[out] Ein Zeiger auf einen Zeiger auf ein Array, das die Liste der zurückgegebenen Token enthält.</span><span class="sxs-lookup"><span data-stu-id="85891-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="85891-109">[out] Ein Zeiger auf einen Zeiger auf den `ixCdTkn`Namen des Tokens unter .</span><span class="sxs-lookup"><span data-stu-id="85891-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85891-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="85891-110">Requirements</span></span>  
 <span data-ttu-id="85891-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85891-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85891-112">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="85891-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85891-113">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="85891-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="85891-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85891-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85891-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="85891-115">See also</span></span>

- [<span data-ttu-id="85891-116">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85891-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="85891-117">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="85891-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
