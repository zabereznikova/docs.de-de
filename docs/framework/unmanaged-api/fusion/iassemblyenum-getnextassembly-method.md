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
ms.openlocfilehash: 73c531378355100fdfca264ea9f96ff4d7c7ceda
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796684"
---
# <a name="iassemblyenumgetnextassembly-method"></a><span data-ttu-id="c0760-102">IAssemblyEnum::GetNextAssembly-Methode</span><span class="sxs-lookup"><span data-stu-id="c0760-102">IAssemblyEnum::GetNextAssembly Method</span></span>
<span data-ttu-id="c0760-103">Ruft einen Zeiger auf den nächsten [IAssemblyName](iassemblyname-interface.md) ab, der in diesem [IAssemblyEnum](iassemblyenum-interface.md) -Objekt enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c0760-103">Gets a pointer to the next [IAssemblyName](iassemblyname-interface.md) contained in this [IAssemblyEnum](iassemblyenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0760-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0760-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextAssembly (  
    [in]  LPVOID          pvReserved,  
    [out] IAssemblyName   **ppName,  
    [in]  DWORD           dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0760-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c0760-105">Parameters</span></span>  
 `pvReserved`  
 <span data-ttu-id="c0760-106">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="c0760-106">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="c0760-107">`pvReserved`muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="c0760-107">`pvReserved` must be a null reference.</span></span>  
  
 `ppName`  
 <span data-ttu-id="c0760-108">vorgenommen Der zurück `IAssemblyName` gegebene Zeiger.</span><span class="sxs-lookup"><span data-stu-id="c0760-108">[out] The returned `IAssemblyName` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c0760-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="c0760-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="c0760-110">`dwFlags`muss 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="c0760-110">`dwFlags` must be 0 (zero).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0760-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0760-111">Requirements</span></span>  
 <span data-ttu-id="c0760-112">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0760-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0760-113">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="c0760-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c0760-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0760-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0760-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0760-115">See also</span></span>

- [<span data-ttu-id="c0760-116">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0760-116">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="c0760-117">IAssemblyEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c0760-117">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
