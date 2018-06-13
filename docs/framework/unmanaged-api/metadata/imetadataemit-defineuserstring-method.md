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
ms.openlocfilehash: 09f2e166072d140fe00fe8ecaee318051953939d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444652"
---
# <a name="imetadataemitdefineuserstring-method"></a><span data-ttu-id="95659-102">IMetaDataEmit::DefineUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="95659-102">IMetaDataEmit::DefineUserString Method</span></span>
<span data-ttu-id="95659-103">Ruft ein Metadatentoken für das angegebene Zeichenfolgenliteral.</span><span class="sxs-lookup"><span data-stu-id="95659-103">Gets a metadata token for the specified literal string.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95659-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95659-104">Syntax</span></span>  
  
```  
HRESULT DefineUserString (   
    [in]  LPCWSTR     szString,   
    [in]  ULONG       cchString,   
    [out] mdString    *pstk   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="95659-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="95659-105">Parameters</span></span>  
 `szString`  
 <span data-ttu-id="95659-106">[in] Die Benutzerzeichenfolge zu speichern.</span><span class="sxs-lookup"><span data-stu-id="95659-106">[in] The user string to store.</span></span>  
  
 `cchString`  
 <span data-ttu-id="95659-107">[in] Die Anzahl der Breitzeichen in `szString`.</span><span class="sxs-lookup"><span data-stu-id="95659-107">[in] The count of wide characters in `szString`.</span></span>  
  
 `pstk`  
 <span data-ttu-id="95659-108">[out] Das Zeichenfolgentoken, das zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="95659-108">[out] The string token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95659-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95659-109">Requirements</span></span>  
 <span data-ttu-id="95659-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95659-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95659-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="95659-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="95659-112">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="95659-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="95659-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95659-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95659-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="95659-114">See Also</span></span>  
 [<span data-ttu-id="95659-115">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95659-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="95659-116">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="95659-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
