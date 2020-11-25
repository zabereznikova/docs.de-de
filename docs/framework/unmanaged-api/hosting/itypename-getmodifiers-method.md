---
title: ITypeName::GetModifiers-Methode
ms.date: 03/30/2017
api_name:
- ITypeName.GetModifiers
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetModifiers
helpviewer_keywords:
- ITypeName::GetModifiers method [.NET Framework hosting]
- GetModifiers method [.NET Framework hosting]
ms.assetid: 75508c55-3e09-4135-80da-cc811003fa82
topic_type:
- apiref
ms.openlocfilehash: 64751032c017473ffd82248b310b14c087f74129
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727834"
---
# <a name="itypenamegetmodifiers-method"></a><span data-ttu-id="c4714-102">ITypeName::GetModifiers-Methode</span><span class="sxs-lookup"><span data-stu-id="c4714-102">ITypeName::GetModifiers Method</span></span>

<span data-ttu-id="c4714-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="c4714-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4714-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4714-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModifiers (  
    [in] DWORD           count,  
    [out] DWORD*         rgModifiers,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="c4714-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c4714-105">Requirements</span></span>  

 <span data-ttu-id="c4714-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4714-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4714-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="c4714-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c4714-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c4714-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4714-109">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4714-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4714-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c4714-110">See also</span></span>

- [<span data-ttu-id="c4714-111">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c4714-111">Hosting Interfaces</span></span>](hosting-interfaces.md)
