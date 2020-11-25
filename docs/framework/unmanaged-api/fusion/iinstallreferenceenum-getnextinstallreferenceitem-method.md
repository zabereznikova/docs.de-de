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
ms.openlocfilehash: e093de7d2c2388274cbe9ebbe46084ee6ae3ff8c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721100"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="7f3a0-102">IInstallReferenceEnum::GetNextInstallReferenceItem-Methode</span><span class="sxs-lookup"><span data-stu-id="7f3a0-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>

<span data-ttu-id="7f3a0-103">Ruft einen Zeiger auf das nächste [IInstallReferenceItem](iinstallreferenceitem-interface.md) -Objekt ab, das in diesem [IInstallReferenceEnum](iinstallreferenceenum-interface.md) -Objekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="7f3a0-103">Gets a pointer to the next [IInstallReferenceItem](iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f3a0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f3a0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f3a0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7f3a0-105">Parameters</span></span>  

 `ppRefItem`  
 <span data-ttu-id="7f3a0-106">vorgenommen Der zurückgegebene `IInstallReferenceItem` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="7f3a0-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7f3a0-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="7f3a0-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="7f3a0-108">`dwFlags` muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="7f3a0-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="7f3a0-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="7f3a0-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="7f3a0-110">`pvReserved` muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="7f3a0-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f3a0-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7f3a0-111">Requirements</span></span>  

 <span data-ttu-id="7f3a0-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f3a0-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f3a0-113">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="7f3a0-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7f3a0-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f3a0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f3a0-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f3a0-115">See also</span></span>

- [<span data-ttu-id="7f3a0-116">IInstallReferenceItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f3a0-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="7f3a0-117">IInstallReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f3a0-117">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
