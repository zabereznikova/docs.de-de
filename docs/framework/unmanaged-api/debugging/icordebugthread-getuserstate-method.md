---
title: ICorDebugThread::GetUserState-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetUserState
helpviewer_keywords:
- GetUserState method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetUserState method [.NET Framework debugging]
ms.assetid: ae0cfd73-8ead-4d36-9310-dccaac9db0bd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4deaa3ab4b14fbd32d45841966cfac9e33b9f31
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487849"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="84e74-102">ICorDebugThread::GetUserState-Methode</span><span class="sxs-lookup"><span data-stu-id="84e74-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="84e74-103">Ruft den aktuellen Benutzerzustand dieses ICorDebugThread ab.</span><span class="sxs-lookup"><span data-stu-id="84e74-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e74-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84e74-104">Syntax</span></span>  
  
```  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84e74-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84e74-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="84e74-106">[out] Ein Zeiger auf eine bitweise Kombination von CorDebugUserState-Enumerationswerte, die den aktuellen Benutzerzustand dieses Threads beschreiben.</span><span class="sxs-lookup"><span data-stu-id="84e74-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="84e74-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="84e74-107">Remarks</span></span>  
 <span data-ttu-id="84e74-108">Der Benutzerzustand des Threads ist der Zustand des Threads an, wenn er von der Anwendung überprüft wird, der debuggt wird.</span><span class="sxs-lookup"><span data-stu-id="84e74-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="84e74-109">Ein Thread möglicherweise mehrere Statusbits festgelegt.</span><span class="sxs-lookup"><span data-stu-id="84e74-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84e74-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="84e74-110">Requirements</span></span>  
 <span data-ttu-id="84e74-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84e74-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84e74-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84e74-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84e74-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84e74-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84e74-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84e74-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
