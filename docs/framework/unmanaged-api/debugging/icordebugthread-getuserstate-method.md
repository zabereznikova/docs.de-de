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
ms.openlocfilehash: f7d3325c8aee44849ff1fb7a6cc06a0ed7c2c6f8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67769101"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="ee71b-102">ICorDebugThread::GetUserState-Methode</span><span class="sxs-lookup"><span data-stu-id="ee71b-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="ee71b-103">Ruft den aktuellen Benutzerzustand dieses ICorDebugThread ab.</span><span class="sxs-lookup"><span data-stu-id="ee71b-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee71b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee71b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ee71b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ee71b-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="ee71b-106">[out] Ein Zeiger auf eine bitweise Kombination von CorDebugUserState-Enumerationswerte, die den aktuellen Benutzerzustand dieses Threads beschreiben.</span><span class="sxs-lookup"><span data-stu-id="ee71b-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee71b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ee71b-107">Remarks</span></span>  
 <span data-ttu-id="ee71b-108">Der Benutzerzustand des Threads ist der Zustand des Threads an, wenn er von der Anwendung überprüft wird, der debuggt wird.</span><span class="sxs-lookup"><span data-stu-id="ee71b-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="ee71b-109">Ein Thread möglicherweise mehrere Statusbits festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ee71b-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee71b-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee71b-110">Requirements</span></span>  
 <span data-ttu-id="ee71b-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee71b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee71b-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ee71b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ee71b-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ee71b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ee71b-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee71b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
