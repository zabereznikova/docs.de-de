---
title: IMetaDataImport::ResetEnum-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.ResetEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 56fc0273fb2c1b77c74d7a1d853886f47170497e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33447927"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="ea1f3-102">IMetaDataImport::ResetEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="ea1f3-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="ea1f3-103">Setzt den angegebenen Enumerator auf die der angegebene Position zurück.</span><span class="sxs-lookup"><span data-stu-id="ea1f3-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea1f3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea1f3-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea1f3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ea1f3-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="ea1f3-106">[in] Der Enumerator zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="ea1f3-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="ea1f3-107">[in] Die neue Position, an der den Enumerator platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ea1f3-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea1f3-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ea1f3-108">Requirements</span></span>  
 <span data-ttu-id="ea1f3-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea1f3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea1f3-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ea1f3-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea1f3-111">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ea1f3-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea1f3-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea1f3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea1f3-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea1f3-113">See Also</span></span>  
 [<span data-ttu-id="ea1f3-114">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea1f3-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ea1f3-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea1f3-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
