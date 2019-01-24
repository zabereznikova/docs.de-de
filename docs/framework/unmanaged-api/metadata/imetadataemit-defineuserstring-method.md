---
title: IMetaDataEmit::DefineUserString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineUserString
helpviewer_keywords:
- DefineUserString method [.NET Framework metadata]
- IMetaDataEmit::DefineUserString method [.NET Framework metadata]
ms.assetid: 88fb7ef3-bbdf-429c-b678-c9c153456461
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb08bad82400523d82e4b8589acb2e74fbbd17d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603725"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="d9593-102">IMetaDataEmit::DefineUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="d9593-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="d9593-103">Ruft Metadaten für die angegebene Zeichenfolge ab.</span><span class="sxs-lookup"><span data-stu-id="d9593-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9593-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d9593-104">Syntax</span></span>  
  
```  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9593-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d9593-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="d9593-106">[in] Der zu speichernde Benutzerzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="d9593-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="d9593-107">[in] Die Anzahl von Breitzeichen in `szString`.</span><span class="sxs-lookup"><span data-stu-id="d9593-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="d9593-108">[out] Das Zeichenfolgentoken, das zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="d9593-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d9593-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d9593-109">Requirements</span></span>  
 <span data-ttu-id="d9593-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9593-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9593-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d9593-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d9593-112">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d9593-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d9593-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9593-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9593-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d9593-114">See also</span></span>
- [<span data-ttu-id="d9593-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9593-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="d9593-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d9593-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
