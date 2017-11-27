---
title: IInstallReferenceItem::GetReference-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IInstallReferenceItem.GetReference
api_location: fusion.dll
api_type: COM
f1_keywords: IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8686e27e63d7363e61bf4c8f1898b71d21fda52b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="af93a-102">IInstallReferenceItem::GetReference-Methode</span><span class="sxs-lookup"><span data-stu-id="af93a-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="af93a-103">Ruft einen Zeiger auf die [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) Struktur dargestellt, die von diesem [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="af93a-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af93a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="af93a-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="af93a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="af93a-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="af93a-106">[out] Das zurückgegebene `FUSION_INSTALL_REFERENCE` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="af93a-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="af93a-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="af93a-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="af93a-108">`dwFlags`0 (null) muss sein.</span><span class="sxs-lookup"><span data-stu-id="af93a-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="af93a-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="af93a-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="af93a-110">`pvReserved`ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="af93a-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af93a-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="af93a-111">Requirements</span></span>  
 <span data-ttu-id="af93a-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af93a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af93a-113">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="af93a-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="af93a-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af93a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af93a-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af93a-115">See Also</span></span>  
 [<span data-ttu-id="af93a-116">IInstallReferenceItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="af93a-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)  
 [<span data-ttu-id="af93a-117">FUSION_INSTALL_REFERENCE-Struktur</span><span class="sxs-lookup"><span data-stu-id="af93a-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
