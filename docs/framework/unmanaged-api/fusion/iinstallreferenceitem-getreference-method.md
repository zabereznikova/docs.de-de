---
title: IInstallReferenceItem::GetReference-Methode
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
ms.openlocfilehash: 14286970a4f7093d72b47b780ea880f5ccb1bca5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721074"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="b3feb-102">IInstallReferenceItem::GetReference-Methode</span><span class="sxs-lookup"><span data-stu-id="b3feb-102">IInstallReferenceItem::GetReference Method</span></span>

<span data-ttu-id="b3feb-103">Ruft einen Zeiger auf die [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) -Struktur ab, die durch dieses [IInstallReferenceItem](iinstallreferenceitem-interface.md) -Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b3feb-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3feb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b3feb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3feb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b3feb-105">Parameters</span></span>  

 `ppRefData`  
 <span data-ttu-id="b3feb-106">vorgenommen Der zurückgegebene `FUSION_INSTALL_REFERENCE` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="b3feb-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="b3feb-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="b3feb-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="b3feb-108">`dwFlags` muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="b3feb-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="b3feb-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="b3feb-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="b3feb-110">`pvReserved` muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="b3feb-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3feb-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b3feb-111">Requirements</span></span>  

 <span data-ttu-id="b3feb-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3feb-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3feb-113">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="b3feb-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="b3feb-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3feb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3feb-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3feb-115">See also</span></span>

- [<span data-ttu-id="b3feb-116">IInstallReferenceItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b3feb-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="b3feb-117">FUSION_INSTALL_REFERENCE-Struktur</span><span class="sxs-lookup"><span data-stu-id="b3feb-117">FUSION_INSTALL_REFERENCE Structure</span></span>](fusion-install-reference-structure.md)
