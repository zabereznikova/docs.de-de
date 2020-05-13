---
title: ICorDebugProcess::IsOSSuspended-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsOSSuspended
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsOSSuspended
helpviewer_keywords:
- IsOSSuspended method [.NET Framework debugging]
- ICorDebugProcess::IsOSSuspended method [.NET Framework debugging]
ms.assetid: 83406cb2-5797-4402-872d-89c9516aefec
topic_type:
- apiref
ms.openlocfilehash: 9452f238bd84c9c185ca8e007acac563474d29df
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212060"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="3adf6-102">ICorDebugProcess::IsOSSuspended-Methode</span><span class="sxs-lookup"><span data-stu-id="3adf6-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="3adf6-103">Ruft einen Wert ab, der angibt, ob der angegebene Thread angehalten wurde, weil der Debugger diesen Prozess beendet hat.</span><span class="sxs-lookup"><span data-stu-id="3adf6-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3adf6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3adf6-104">Syntax</span></span>  
  
```cpp  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3adf6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3adf6-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="3adf6-106">in Die ID des fraglichen Threads.</span><span class="sxs-lookup"><span data-stu-id="3adf6-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="3adf6-107">vorgenommen Ein Zeiger auf einen booleschen Wert, der ist, `true` Wenn der angegebene Thread angehalten wurde, andernfalls \* `pbSuspended` ist `false` .</span><span class="sxs-lookup"><span data-stu-id="3adf6-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3adf6-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3adf6-108">Remarks</span></span>  
 <span data-ttu-id="3adf6-109">Wenn der angegebene Thread durch den Debugger angehalten wurde, der diesen Prozess beendet, wird die Win32-anhalteanzahl des angegebenen Threads um 1 erhöht.</span><span class="sxs-lookup"><span data-stu-id="3adf6-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="3adf6-110">Diese Informationen können von der Benutzeroberfläche des Debuggers berücksichtigt werden, wenn das Betriebssystem (OS) der Thread Anzahl für den Benutzer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3adf6-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="3adf6-111">Die- `IsOSSuspended` Methode ist nur im Kontext des nicht verwalteten Debuggens sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="3adf6-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="3adf6-112">Während des verwalteten Debuggens werden Threads gemeinsam angehalten und nicht als Betriebssystem angehalten.</span><span class="sxs-lookup"><span data-stu-id="3adf6-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3adf6-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3adf6-113">Requirements</span></span>  
 <span data-ttu-id="3adf6-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3adf6-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3adf6-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3adf6-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3adf6-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3adf6-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3adf6-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3adf6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
