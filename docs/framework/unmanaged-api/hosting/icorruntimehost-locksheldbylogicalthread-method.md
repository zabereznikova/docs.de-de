---
title: ICorRuntimeHost::LocksHeldByLogicalThread-Methode
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.LocksHeldByLogicalThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread
helpviewer_keywords:
- ICorRuntimeHost::LocksHeldByLogicalThread method [.NET Framework hosting]
- LocksHeldByLogicalThread method [.NET Framework hosting]
ms.assetid: c3601255-d894-4d7c-b1df-c31334551700
topic_type:
- apiref
ms.openlocfilehash: 16f34d91861f9fcae51691ab13549bdf1ef333a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671498"
---
# <a name="icorruntimehostlocksheldbylogicalthread-method"></a><span data-ttu-id="8788f-102">ICorRuntimeHost::LocksHeldByLogicalThread-Methode</span><span class="sxs-lookup"><span data-stu-id="8788f-102">ICorRuntimeHost::LocksHeldByLogicalThread Method</span></span>

<span data-ttu-id="8788f-103">Ruft die Anzahl der Sperren ab, die der aktuelle Thread enthält.</span><span class="sxs-lookup"><span data-stu-id="8788f-103">Retrieves the number of locks that current thread holds.</span></span>  
  
 <span data-ttu-id="8788f-104">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8788f-104">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8788f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8788f-105">Syntax</span></span>  
  
```cpp  
HRESULT LocksHeldByLogicalThread(  
    [out] DWORD *pCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8788f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="8788f-106">Parameters</span></span>  

 `pCount`  
 <span data-ttu-id="8788f-107">vorgenommen Ein Zeiger auf die Anzahl der Sperren, die der aktuelle Thread enthält.</span><span class="sxs-lookup"><span data-stu-id="8788f-107">[out] A pointer to the number of locks that the current thread holds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8788f-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8788f-108">Requirements</span></span>  

 <span data-ttu-id="8788f-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8788f-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8788f-110">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8788f-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8788f-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8788f-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8788f-112">**.NET Framework Versionen:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="8788f-112">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8788f-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8788f-113">See also</span></span>

- [<span data-ttu-id="8788f-114">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8788f-114">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
