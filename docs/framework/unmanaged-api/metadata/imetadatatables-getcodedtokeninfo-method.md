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
ms.openlocfilehash: 8ab16ad5b2b2838125e07511ef47be737f40671c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501208"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="05bab-102">IMetaDataTables::GetCodedTokenInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="05bab-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="05bab-103">Ruft einen Zeiger auf ein Array von Token ab, die dem angegebenen Zeilen Index zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="05bab-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05bab-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="05bab-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05bab-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="05bab-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="05bab-106">in Die Art des zurück zugebende codierten Tokens.</span><span class="sxs-lookup"><span data-stu-id="05bab-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="05bab-107">vorgenommen Ein Zeiger auf die Länge von `ppTokens` .</span><span class="sxs-lookup"><span data-stu-id="05bab-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="05bab-108">vorgenommen Ein Zeiger auf einen Zeiger auf ein Array, das die Liste der zurückgegebenen Token enthält.</span><span class="sxs-lookup"><span data-stu-id="05bab-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="05bab-109">vorgenommen Ein Zeiger auf einen Zeiger auf den Namen des Tokens bei `ixCdTkn` .</span><span class="sxs-lookup"><span data-stu-id="05bab-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05bab-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="05bab-110">Requirements</span></span>  
 <span data-ttu-id="05bab-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="05bab-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05bab-112">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="05bab-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05bab-113">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="05bab-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="05bab-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05bab-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05bab-115">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="05bab-115">See also</span></span>

- [<span data-ttu-id="05bab-116">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05bab-116">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="05bab-117">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="05bab-117">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
