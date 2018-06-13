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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e22d112d1414b13033f73723821e5e4b5764e1c8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33401978"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="0e91d-102">ICorDebugAssembly::GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="0e91d-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="0e91d-103">Ruft einen Schnittstellenzeiger auf die Anwendungsdomäne, die dieses enthält `ICorDebugAssembly` Instanz.</span><span class="sxs-lookup"><span data-stu-id="0e91d-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e91d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e91d-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0e91d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0e91d-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="0e91d-106">[out] Ein Zeiger auf die Adresse einer ICorDebugAppDomain-Schnittstelle, die die Anwendungsdomäne darstellt.</span><span class="sxs-lookup"><span data-stu-id="0e91d-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e91d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e91d-107">Remarks</span></span>  
 <span data-ttu-id="0e91d-108">Wenn diese Assembly die Systemassembly `GetAppDomain` gibt null zurück.</span><span class="sxs-lookup"><span data-stu-id="0e91d-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e91d-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e91d-109">Requirements</span></span>  
 <span data-ttu-id="0e91d-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e91d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e91d-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e91d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e91d-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e91d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e91d-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e91d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
