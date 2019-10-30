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
ms.openlocfilehash: 0dad50f1acac38f8cdc505026e88d42882deb580
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131724"
---
# <a name="iinstallreferenceenumgetnextinstallreferenceitem-method"></a><span data-ttu-id="dba7c-102">IInstallReferenceEnum::GetNextInstallReferenceItem-Methode</span><span class="sxs-lookup"><span data-stu-id="dba7c-102">IInstallReferenceEnum::GetNextInstallReferenceItem Method</span></span>
<span data-ttu-id="dba7c-103">Ruft einen Zeiger auf das nächste [IInstallReferenceItem](iinstallreferenceitem-interface.md) -Objekt ab, das in diesem [IInstallReferenceEnum](iinstallreferenceenum-interface.md) -Objekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="dba7c-103">Gets a pointer to the next [IInstallReferenceItem](iinstallreferenceitem-interface.md) object contained in this [IInstallReferenceEnum](iinstallreferenceenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dba7c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dba7c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextInstallReferenceItem (  
    [out] IInstallReferenceItem **ppRefItem,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dba7c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dba7c-105">Parameters</span></span>  
 `ppRefItem`  
 <span data-ttu-id="dba7c-106">vorgenommen Der zurückgegebene `IInstallReferenceItem` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="dba7c-106">[out] The returned `IInstallReferenceItem` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="dba7c-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="dba7c-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="dba7c-108">`dwFlags` muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="dba7c-108">`dwFlags` must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="dba7c-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="dba7c-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="dba7c-110">`pvReserved` muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="dba7c-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dba7c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dba7c-111">Requirements</span></span>  
 <span data-ttu-id="dba7c-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dba7c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dba7c-113">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="dba7c-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="dba7c-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dba7c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dba7c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dba7c-115">See also</span></span>

- [<span data-ttu-id="dba7c-116">IInstallReferenceItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dba7c-116">IInstallReferenceItem Interface</span></span>](iinstallreferenceitem-interface.md)
- [<span data-ttu-id="dba7c-117">IInstallReferenceEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dba7c-117">IInstallReferenceEnum Interface</span></span>](iinstallreferenceenum-interface.md)
