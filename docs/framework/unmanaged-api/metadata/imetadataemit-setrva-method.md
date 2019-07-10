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
ms.openlocfilehash: 02331bb3b0c70b946eaa28c9cd316f109ac927b6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777237"
---
# <a name="imetadataemitsetrva-method"></a><span data-ttu-id="3db3d-102">IMetaDataEmit::SetRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="3db3d-102">IMetaDataEmit::SetRVA Method</span></span>
<span data-ttu-id="3db3d-103">Legt fest, die relative virtuelle Adresse der angegebenen Methode.</span><span class="sxs-lookup"><span data-stu-id="3db3d-103">Sets the relative virtual address of the specified method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3db3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3db3d-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRVA (  
    [in]  mdMethodDef  md,   
    [in]  ULONG        ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3db3d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3db3d-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="3db3d-106">[in] Das Token für die Zielmethode oder die Implementierung der Methode.</span><span class="sxs-lookup"><span data-stu-id="3db3d-106">[in] The token for the target method or method implementation.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="3db3d-107">[in] Die Adresse des Bereichs, Code oder Daten.</span><span class="sxs-lookup"><span data-stu-id="3db3d-107">[in] The address of the code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3db3d-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3db3d-108">Requirements</span></span>  
 <span data-ttu-id="3db3d-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3db3d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3db3d-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3db3d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3db3d-111">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="3db3d-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3db3d-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3db3d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3db3d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3db3d-113">See also</span></span>

- [<span data-ttu-id="3db3d-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3db3d-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="3db3d-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3db3d-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
