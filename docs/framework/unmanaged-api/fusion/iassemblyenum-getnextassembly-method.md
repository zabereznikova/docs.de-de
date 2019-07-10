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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57d64096ea693be41359aef63c04674ca77769c6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760976"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="c450f-102">IAssemblyEnum::GetNextAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="c450f-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="c450f-103">Ruft einen Zeiger auf der nächste [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) enthalten [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="c450f-103">Gets a pointer to the next [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) contained in this [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c450f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c450f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c450f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c450f-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="c450f-106">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="c450f-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="c450f-107">`pvReserved` ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="c450f-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="c450f-108">[out] Das zurückgegebene `IAssemblyName` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="c450f-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c450f-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="c450f-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="c450f-110">`dwFlags` 0 (null) muss sein.</span><span class="sxs-lookup"><span data-stu-id="c450f-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c450f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c450f-111">Requirements</span></span>  
 <span data-ttu-id="c450f-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c450f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c450f-113">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="c450f-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c450f-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c450f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c450f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c450f-115">See also</span></span>

- [<span data-ttu-id="c450f-116">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c450f-116">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="c450f-117">IAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c450f-117">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
