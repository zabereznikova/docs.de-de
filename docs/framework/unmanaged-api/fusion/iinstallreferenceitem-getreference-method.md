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
ms.openlocfilehash: 014bd4f2b12c84790065f76a67765aaf35e8b2d8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131683"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="de086-102">IInstallReferenceItem::GetReference-Methode</span><span class="sxs-lookup"><span data-stu-id="de086-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="de086-103">Ruft einen Zeiger auf die [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) -Struktur ab, die durch dieses [IInstallReferenceItem](iinstallreferenceitem-interface.md) -Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="de086-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de086-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="de086-104">Syntax</span></span>  
  
```cpp  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de086-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="de086-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="de086-106">vorgenommen Der zurückgegebene `FUSION_INSTALL_REFERENCE` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="de086-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="de086-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="de086-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="de086-108">`dwFlags` muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="de086-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="de086-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="de086-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="de086-110">`pvReserved` muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="de086-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de086-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="de086-111">Requirements</span></span>  
 <span data-ttu-id="de086-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de086-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de086-113">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="de086-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="de086-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de086-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de086-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="de086-115">See also</span></span>

- [<span data-ttu-id="de086-116">IInstallReferenceItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="de086-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="de086-117">FUSION_INSTALL_REFERENCE-Struktur</span><span class="sxs-lookup"><span data-stu-id="de086-117">FUSION_INSTALL_REFERENCE Structure</span></span>](fusion-install-reference-structure.md)
