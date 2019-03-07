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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 039dc0d9befb038e643abc4e2524c133234f460b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492074"
---
# <a name="icordebugprocessisossuspended-method"></a><span data-ttu-id="ac088-102">ICorDebugProcess::IsOSSuspended-Methode</span><span class="sxs-lookup"><span data-stu-id="ac088-102">ICorDebugProcess::IsOSSuspended Method</span></span>
<span data-ttu-id="ac088-103">Ruft einen Wert, der angibt, ob der angegebene Thread durch den Debugger Beenden dieses Prozesses angehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="ac088-103">Gets a value that indicates whether the specified thread has been suspended as a result of the debugger stopping this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac088-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ac088-104">Syntax</span></span>  
  
```  
HRESULT IsOSSuspended(  
    [in]  DWORD threadID,  
    [out] BOOL  *pbSuspended);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac088-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ac088-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="ac088-106">[in] Die ID des betreffenden Threads.</span><span class="sxs-lookup"><span data-stu-id="ac088-106">[in] The ID of thread in question.</span></span>  
  
 `pbSuspended`  
 <span data-ttu-id="ac088-107">[out] Ein Zeiger auf einen booleschen Wert, der `true` , wenn der angegebene Thread angehalten, andernfalls wurde \*`pbSuspended` ist `false`.</span><span class="sxs-lookup"><span data-stu-id="ac088-107">[out] A pointer to a Boolean value that is `true` if the specified thread has been suspended; otherwise \*`pbSuspended` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac088-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ac088-108">Remarks</span></span>  
 <span data-ttu-id="ac088-109">Wenn der angegebene Thread durch den Debugger Beenden dieses Prozesses angehalten wurde, den angegebenen Thread Win32 Unterbrechungszähler um eins erhöht.</span><span class="sxs-lookup"><span data-stu-id="ac088-109">When the specified thread has been suspended as a result of the debugger stopping this process, the specified thread's Win32 suspend count is incremented by one.</span></span> <span data-ttu-id="ac088-110">Die Debugger-Benutzeroberfläche (UI) sollten diese Informationen berücksichtigt werden, wenn angezeigt wird das Betriebssystem (OS) Unterbrechungszähler des Threads für den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ac088-110">The debugger user interface (UI) may want to take this information into account if it displays the operating system (OS) suspend count of the thread to the user.</span></span>  
  
 <span data-ttu-id="ac088-111">Die `IsOSSuspended` Methode ist sinnvoll, nur im Kontext nicht verwaltetes debugging.</span><span class="sxs-lookup"><span data-stu-id="ac088-111">The `IsOSSuspended` method makes sense only in the context of unmanaged debugging.</span></span> <span data-ttu-id="ac088-112">Sind während des Debuggens verwalteten Threads kooperativ und nicht-Betriebssystem-angehalten.</span><span class="sxs-lookup"><span data-stu-id="ac088-112">During managed debugging, threads are cooperatively suspended rather than OS-suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac088-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ac088-113">Requirements</span></span>  
 <span data-ttu-id="ac088-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac088-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac088-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac088-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac088-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac088-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac088-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac088-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
