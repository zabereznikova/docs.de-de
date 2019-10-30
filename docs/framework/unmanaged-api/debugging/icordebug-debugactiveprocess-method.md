---
title: ICorDebug::DebugActiveProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebug.DebugActiveProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::DebugActiveProcess
helpviewer_keywords:
- DebugActiveProcess method [.NET Framework debugging]
- ICorDebug::DebugActiveProcess method [.NET Framework debugging]
ms.assetid: fdab0ade-7f56-4fa2-b3ef-f7a1d2852bba
topic_type:
- apiref
ms.openlocfilehash: 5b988b110100cd159b8e262573df409847d635c6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134124"
---
# <a name="icordebugdebugactiveprocess-method"></a><span data-ttu-id="8bd35-102">ICorDebug::DebugActiveProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="8bd35-102">ICorDebug::DebugActiveProcess Method</span></span>
<span data-ttu-id="8bd35-103">Fügt den Debugger an einen vorhandenen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="8bd35-103">Attaches the debugger to an existing process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bd35-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8bd35-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcess (  
    [in]  DWORD               id,  
    [in]  BOOL                win32Attach,  
    [out] ICorDebugProcess    **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bd35-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8bd35-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="8bd35-106">in Die ID des Prozesses, an den der Debugger angefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8bd35-106">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="8bd35-107">in Boolescher Wert, der auf `true` festgelegt wird, wenn sich der Debugger als Win32-Debugger für den Prozessverhalten soll und die nicht verwalteten Rückrufe versendet. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="8bd35-107">[in] Boolean value that is set to `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="8bd35-108">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Objekts, das den Prozess darstellt, dem der Debugger angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="8bd35-108">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bd35-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8bd35-109">Remarks</span></span>  
 <span data-ttu-id="8bd35-110">Interop-Debuggen wird auf Win9x-und nicht-x86-Plattformen wie IA-64-basierten und AMD64-basierten Plattformen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8bd35-110">Interop debugging is not supported on Win9x and non-x86 platforms, such as IA-64-based and AMD64-based platforms.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bd35-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8bd35-111">Requirements</span></span>  
 <span data-ttu-id="8bd35-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bd35-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bd35-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bd35-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bd35-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bd35-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bd35-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bd35-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd35-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8bd35-116">See also</span></span>

- [<span data-ttu-id="8bd35-117">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8bd35-117">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
