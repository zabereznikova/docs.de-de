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
ms.openlocfilehash: 89475ebc5ef04c8693adb7a83bd1dd07f5774fb9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54544692"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="a591c-102">IMetaDataEmit::SetRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="a591c-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="a591c-103">Legt fest, die relative virtuelle Adresse der angegebenen Methode.</span><span class="sxs-lookup"><span data-stu-id="a591c-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a591c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a591c-104">Syntax</span></span>  
  
```  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a591c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a591c-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="a591c-106">[in] Das Token für die Zielmethode oder die Implementierung der Methode.</span><span class="sxs-lookup"><span data-stu-id="a591c-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="a591c-107">[in] Die Adresse des Bereichs, Code oder Daten.</span><span class="sxs-lookup"><span data-stu-id="a591c-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a591c-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a591c-108">Requirements</span></span>  
 <span data-ttu-id="a591c-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a591c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a591c-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a591c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a591c-111">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="a591c-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a591c-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a591c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a591c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a591c-113">See also</span></span>
- [<span data-ttu-id="a591c-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a591c-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a591c-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a591c-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
