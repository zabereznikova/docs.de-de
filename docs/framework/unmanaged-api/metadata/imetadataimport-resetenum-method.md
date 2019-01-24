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
ms.openlocfilehash: 04bdd41e884caa5ed39dff4f4f1e027cde1fec53
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568009"
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="84bde-102">IMetaDataImport::ResetEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="84bde-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="84bde-103">Setzt den angegebenen Enumerator auf die der angegebene Position zurück.</span><span class="sxs-lookup"><span data-stu-id="84bde-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84bde-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84bde-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="84bde-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84bde-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="84bde-106">[in] Der Enumerator zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="84bde-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="84bde-107">[in] Die neue Position, an dem den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="84bde-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84bde-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84bde-108">Requirements</span></span>  
 <span data-ttu-id="84bde-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84bde-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84bde-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="84bde-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="84bde-111">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="84bde-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="84bde-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84bde-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84bde-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84bde-113">See also</span></span>
- [<span data-ttu-id="84bde-114">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84bde-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="84bde-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84bde-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
