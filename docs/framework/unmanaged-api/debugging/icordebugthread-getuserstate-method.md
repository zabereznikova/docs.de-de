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
ms.openlocfilehash: d1ff3427feb5dc8395bbb2fda78e3e93e1a1a8f0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378858"
---
# <a name="icordebugthreadgetuserstate-method"></a><span data-ttu-id="cc3df-102">ICorDebugThread::GetUserState-Methode</span><span class="sxs-lookup"><span data-stu-id="cc3df-102">ICorDebugThread::GetUserState Method</span></span>
<span data-ttu-id="cc3df-103">Ruft den aktuellen Benutzer Zustand dieses ICorDebugThread ab.</span><span class="sxs-lookup"><span data-stu-id="cc3df-103">Gets the current user state of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc3df-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cc3df-104">Syntax</span></span>  
  
```cpp  
HRESULT GetUserState (  
    [out] CorDebugUserState   *pState  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc3df-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cc3df-105">Parameters</span></span>  
 `pState`  
 <span data-ttu-id="cc3df-106">vorgenommen Ein Zeiger auf eine bitweise Kombination von CorDebugUserState-Enumerationswerten, die den aktuellen Benutzer Zustand dieses Threads beschreiben.</span><span class="sxs-lookup"><span data-stu-id="cc3df-106">[out] A pointer to a bitwise combination of CorDebugUserState enumeration values that describe the current user state of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc3df-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cc3df-107">Remarks</span></span>  
 <span data-ttu-id="cc3df-108">Der Benutzer Zustand des Threads ist der Zustand des Threads, wenn er von dem Programm überprüft wird, das gerade deentschlgt wird.</span><span class="sxs-lookup"><span data-stu-id="cc3df-108">The user state of the thread is the state of the thread when it is examined by the program that is being debugged.</span></span> <span data-ttu-id="cc3df-109">Für einen Thread sind möglicherweise mehrere State-Bits festgelegt.</span><span class="sxs-lookup"><span data-stu-id="cc3df-109">A thread may have multiple state bits set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc3df-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cc3df-110">Requirements</span></span>  
 <span data-ttu-id="cc3df-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc3df-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc3df-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="cc3df-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cc3df-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cc3df-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cc3df-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc3df-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
