---
title: IInstallReferenceEnum::GetNextInstallReferenceItem-Methode
ms.date: 03/30/2017
api_name:
- IInstallReferenceEnum.GetNextInstallReferenceItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem
helpviewer_keywords:
- IInstallReferenceEnum::GetNextInstallReferenceItem method [.NET Framework fusion]
- GetNextInstallReferenceItem method [.NET Framework fusion]
ms.assetid: ce969c9d-6538-4c34-8784-148ffd99fe7a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b756cdcbbc852280e88fef2d1a2bf5f0125cbd73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429210"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="fefaa-102">IInstallReferenceEnum::GetNextInstallReferenceItem-Methode</span><span class="sxs-lookup"><span data-stu-id="fefaa-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="fefaa-103">Ruft einen Zeiger auf dem nächsten [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) enthalten, die in diesem Objekt [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="fefaa-103">Gets a pointer to the next [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fefaa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fefaa-104">Syntax</span></span>  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fefaa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fefaa-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="fefaa-106">[out] Das zurückgegebene `IInstallReferenceItem` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="fefaa-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="fefaa-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="fefaa-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="fefaa-108">`dwFlags` 0 (null) muss sein.</span><span class="sxs-lookup"><span data-stu-id="fefaa-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="fefaa-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="fefaa-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="fefaa-110">`pvReserved` ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="fefaa-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fefaa-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fefaa-111">Requirements</span></span>  
 <span data-ttu-id="fefaa-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fefaa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fefaa-113">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="fefaa-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="fefaa-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fefaa-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fefaa-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fefaa-115">See Also</span></span>  
 [<span data-ttu-id="fefaa-116">IInstallReferenceItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fefaa-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 [<span data-ttu-id="fefaa-117">IInstallReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fefaa-117">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
