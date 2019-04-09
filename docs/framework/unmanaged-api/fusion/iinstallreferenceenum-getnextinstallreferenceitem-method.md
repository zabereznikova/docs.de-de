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
ms.openlocfilehash: bc04bb12e4271a3237ebef140c481620fc01ad7e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59202377"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="b555b-102">IInstallReferenceEnum::GetNextInstallReferenceItem-Methode</span><span class="sxs-lookup"><span data-stu-id="b555b-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="b555b-103">Ruft einen Zeiger auf der nächste [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) Objekt enthalten, die in diesem [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="b555b-103">Gets a pointer to the next [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b555b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b555b-104">Syntax</span></span>  
  
```  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b555b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b555b-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="b555b-106">[out] Das zurückgegebene `IInstallReferenceItem` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="b555b-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b555b-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="b555b-107">[in] Reserved for future extensibility.</span></span> `dwFlags` <span data-ttu-id="b555b-108">0 (null) muss sein.</span><span class="sxs-lookup"><span data-stu-id="b555b-108">must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="b555b-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="b555b-109">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="b555b-110">ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="b555b-110">must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b555b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b555b-111">Requirements</span></span>  
 <span data-ttu-id="b555b-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b555b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b555b-113">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="b555b-113">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="b555b-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="b555b-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b555b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b555b-115">See also</span></span>

- [<span data-ttu-id="b555b-116">IInstallReferenceItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b555b-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="b555b-117">IInstallReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b555b-117">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
