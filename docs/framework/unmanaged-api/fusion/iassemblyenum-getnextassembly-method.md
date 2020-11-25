---
title: IAssemblyEnum::GetNextAssembly-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyEnum.GetNextAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyEnum::GetNextAssembly
helpviewer_keywords:
- GetNextAssembly method [.NET Framework fusion]
- IAssemblyEnum::GetNextAssembly method [.NET Framework fusion]
ms.assetid: 5d7a4ca2-5f46-4ef1-a9a2-257884e9dc11
topic_type:
- apiref
ms.openlocfilehash: af43d9cf4d5aa790036a13d060fc6ccf113f335d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719891"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="e05c9-102">IAssemblyEnum::GetNextAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="e05c9-102">IAssemblyEnum::GetNextAssembly Method</span></span>

<span data-ttu-id="e05c9-103">Ruft einen Zeiger auf den nächsten [IAssemblyName](iassemblyname-interface.md) ab, der in diesem [IAssemblyEnum](iassemblyenum-interface.md) -Objekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="e05c9-103">Gets a pointer to the next [IAssemblyName](iassemblyname-interface.md) contained in this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e05c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e05c9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e05c9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e05c9-105">Parameters</span></span>  

 `pvReserved`  
 <span data-ttu-id="e05c9-106">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="e05c9-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e05c9-107">`pvReserved` muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="e05c9-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="e05c9-108">vorgenommen Der zurückgegebene `IAssemblyName` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="e05c9-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="e05c9-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="e05c9-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="e05c9-110">`dwFlags` muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="e05c9-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e05c9-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e05c9-111">Requirements</span></span>  

 <span data-ttu-id="e05c9-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e05c9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e05c9-113">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="e05c9-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="e05c9-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e05c9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e05c9-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e05c9-115">See also</span></span>

- [<span data-ttu-id="e05c9-116">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e05c9-116">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="e05c9-117">IAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e05c9-117">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
