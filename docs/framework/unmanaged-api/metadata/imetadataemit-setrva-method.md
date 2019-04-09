---
title: IMetaDataEmit::SetRVA-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetRVA
helpviewer_keywords:
- IMetaDataEmit::SetRVA method [.NET Framework metadata]
- SetRVA method [.NET Framework metadata]
ms.assetid: 4d69fb6d-ee35-4318-8224-5eea2bd16818
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e17a6846ba0276ec7ba423ab25e3f11baf278d03
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59098753"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="8c476-102">IMetaDataEmit::SetRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="8c476-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="8c476-103">Legt fest, die relative virtuelle Adresse der angegebenen Methode.</span><span class="sxs-lookup"><span data-stu-id="8c476-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c476-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c476-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c476-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8c476-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="8c476-106">[in] Das Token für die Zielmethode oder die Implementierung der Methode.</span><span class="sxs-lookup"><span data-stu-id="8c476-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="8c476-107">[in] Die Adresse des Bereichs, Code oder Daten.</span><span class="sxs-lookup"><span data-stu-id="8c476-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c476-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8c476-108">Requirements</span></span>  
 <span data-ttu-id="8c476-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c476-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c476-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8c476-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8c476-111">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="8c476-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8c476-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8c476-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8c476-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c476-113">See also</span></span>

- [<span data-ttu-id="8c476-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c476-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8c476-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8c476-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
