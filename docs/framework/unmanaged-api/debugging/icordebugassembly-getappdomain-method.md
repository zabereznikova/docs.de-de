---
title: ICorDebugAssembly::GetAppDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetAppDomain
helpviewer_keywords:
- ICorDebugAssembly::GetAppDomain method [.NET Framework debugging]
- GetAppDomain method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 14e18510-23ac-4cba-9f96-c86147a2df9d
topic_type:
- apiref
ms.openlocfilehash: 55a798bcc575aee3f309c35eb454a0675e0cbd97
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734074"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="67c5f-102">ICorDebugAssembly::GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="67c5f-102">ICorDebugAssembly::GetAppDomain Method</span></span>

<span data-ttu-id="67c5f-103">Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, die diese `ICorDebugAssembly` Instanz enthält.</span><span class="sxs-lookup"><span data-stu-id="67c5f-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67c5f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67c5f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67c5f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="67c5f-105">Parameters</span></span>  

 `ppAppDomain`  
 <span data-ttu-id="67c5f-106">vorgenommen Ein Zeiger auf die Adresse einer ICorDebugAppDomain-Schnittstelle, die die Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="67c5f-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67c5f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="67c5f-107">Remarks</span></span>  

 <span data-ttu-id="67c5f-108">Wenn diese Assembly die Systemassembly ist, `GetAppDomain` gibt NULL zurück.</span><span class="sxs-lookup"><span data-stu-id="67c5f-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67c5f-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="67c5f-109">Requirements</span></span>  

 <span data-ttu-id="67c5f-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67c5f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67c5f-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67c5f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67c5f-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67c5f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67c5f-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67c5f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
