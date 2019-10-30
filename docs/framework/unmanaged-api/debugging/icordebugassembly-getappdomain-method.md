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
ms.openlocfilehash: 53042e722809a6574396648529c677d749154716
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132730"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="e6f44-102">ICorDebugAssembly::GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="e6f44-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="e6f44-103">Ruft einen Schnittstellen Zeiger auf die Anwendungsdomäne ab, die diese `ICorDebugAssembly` Instanz enthält.</span><span class="sxs-lookup"><span data-stu-id="e6f44-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6f44-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6f44-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6f44-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e6f44-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="e6f44-106">vorgenommen Ein Zeiger auf die Adresse einer ICorDebugAppDomain-Schnittstelle, die die Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="e6f44-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e6f44-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e6f44-107">Remarks</span></span>  
 <span data-ttu-id="e6f44-108">Wenn diese Assembly die Systemassembly ist, gibt `GetAppDomain` NULL zurück.</span><span class="sxs-lookup"><span data-stu-id="e6f44-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6f44-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e6f44-109">Requirements</span></span>  
 <span data-ttu-id="e6f44-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6f44-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6f44-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e6f44-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e6f44-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6f44-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e6f44-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6f44-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
