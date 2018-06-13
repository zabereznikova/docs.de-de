---
title: ICorDebugThread::GetAppDomain-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetAppDomain
helpviewer_keywords:
- GetAppDomain method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetAppDomain method [.NET Framework debugging]
ms.assetid: 415b3d34-8b35-4b60-a318-140646cc83f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51878f0334afe52608b60ca540e49c86fded148e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418044"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="0cef9-102">ICorDebugThread::GetAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="0cef9-102">ICorDebugThread::GetAppDomain Method</span></span>
<span data-ttu-id="0cef9-103">Ruft einen Schnittstellenzeiger auf die Anwendungsdomäne, in der dieser ICorDebugThread derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0cef9-103">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cef9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0cef9-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0cef9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0cef9-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="0cef9-106">[out] Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, in der dieser Thread gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="0cef9-106">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cef9-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0cef9-107">Requirements</span></span>  
 <span data-ttu-id="0cef9-108">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cef9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cef9-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cef9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cef9-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cef9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cef9-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cef9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
