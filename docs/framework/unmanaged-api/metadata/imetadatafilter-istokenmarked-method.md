---
title: IMetaDataFilter::IsTokenMarked-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataFilter.IsTokenMarked
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataFilter::IsTokenMarked
helpviewer_keywords:
- IMetaDataFilter::IsTokenMarked method [.NET Framework metadata]
- IsTokenMarked method [.NET Framework metadata]
ms.assetid: 7d90dcee-0206-4540-807b-06982fe65f1a
topic_type:
- apiref
ms.openlocfilehash: 10f31d56a9727e99157f49038c19781f12cd9958
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440431"
---
# <a name="imetadatafilteristokenmarked-method"></a><span data-ttu-id="39127-102">IMetaDataFilter::IsTokenMarked-Methode</span><span class="sxs-lookup"><span data-stu-id="39127-102">IMetaDataFilter::IsTokenMarked Method</span></span>
<span data-ttu-id="39127-103">Ruft einen Wert ab, der angibt, ob das angegebene Metadatentoken als verarbeitet gekennzeichnet wurde.</span><span class="sxs-lookup"><span data-stu-id="39127-103">Gets a value indicating whether the specified metadata token has been marked as processed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39127-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="39127-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTokenMarked (  
    [in]  mdToken  tk,   
    [out] BOOL     *pIsMarked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="39127-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="39127-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="39127-106">in Das Token, das auf eine Verarbeitungs Markierung überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="39127-106">[in] The token to examine for a processing mark.</span></span>  
  
 `pIsMarked`  
 <span data-ttu-id="39127-107">vorgenommen Ein-Wert, der `true` wird, wenn `tk` verarbeitet wurde. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="39127-107">[out] A value that is `true` if `tk` has been processed; otherwise `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39127-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="39127-108">Requirements</span></span>  
 <span data-ttu-id="39127-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39127-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39127-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="39127-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="39127-111">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="39127-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="39127-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39127-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39127-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39127-113">See also</span></span>

- [<span data-ttu-id="39127-114">IMetaDataFilter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="39127-114">IMetaDataFilter Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatafilter-interface.md)
