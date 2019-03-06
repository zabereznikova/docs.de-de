---
title: IMetaDataEmit::SetFieldRVA-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a38de994575bf0191ff2ab5ce1c7b047540289f
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470587"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="c4772-102">IMetaDataEmit::SetFieldRVA-Methode</span><span class="sxs-lookup"><span data-stu-id="c4772-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="c4772-103">Legt einen Wert der globalen Variablen für die relative virtuelle Adresse des Felds auf die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c4772-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4772-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4772-104">Syntax</span></span>  
  
```  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4772-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c4772-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="c4772-106">[in] Das Token für das Feld "Ziel".</span><span class="sxs-lookup"><span data-stu-id="c4772-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="c4772-107">[in] Die Adresse eines Bereichs Code- oder Datenmenge.</span><span class="sxs-lookup"><span data-stu-id="c4772-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4772-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c4772-108">Requirements</span></span>  
 <span data-ttu-id="c4772-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4772-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4772-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c4772-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c4772-111">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c4772-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4772-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4772-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4772-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4772-113">See also</span></span>
- [<span data-ttu-id="c4772-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4772-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c4772-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c4772-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
