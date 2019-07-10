---
title: ICorDebugFunction2::SetJMCStatus-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67959b2ebbfb62b47a1b2a770e278d043fc66d21
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754918"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="716c5-102">ICorDebugFunction2::SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="716c5-102">ICorDebugFunction2::SetJMCStatus Method</span></span>
<span data-ttu-id="716c5-103">Markiert die Funktion, die von dieser ICorDebugFunction2 dargestellt für nur mein Code schrittweise ausführen.</span><span class="sxs-lookup"><span data-stu-id="716c5-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="716c5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="716c5-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="716c5-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="716c5-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="716c5-106">[in] Legen Sie auf `true` , markieren Sie die Funktion als Benutzercode; legen Sie andernfalls auf `false`.</span><span class="sxs-lookup"><span data-stu-id="716c5-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="716c5-107">Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="716c5-107">Return Values</span></span>  
  
|<span data-ttu-id="716c5-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="716c5-108">HRESULT</span></span>|<span data-ttu-id="716c5-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="716c5-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="716c5-110">Die Funktion wurde erfolgreich markiert.</span><span class="sxs-lookup"><span data-stu-id="716c5-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="716c5-111">Die Funktion konnte nicht als Benutzercode gekennzeichnet werden, da es nicht gedebuggt werden kann.</span><span class="sxs-lookup"><span data-stu-id="716c5-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="716c5-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="716c5-112">Remarks</span></span>  
 <span data-ttu-id="716c5-113">Eine zugeordnetem nur mein Code wird nicht benutzerseitiger Code überspringen.</span><span class="sxs-lookup"><span data-stu-id="716c5-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="716c5-114">Benutzercode muss es sich um eine Teilmenge der debugfähiger Code sein.</span><span class="sxs-lookup"><span data-stu-id="716c5-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="716c5-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="716c5-115">Requirements</span></span>  
 <span data-ttu-id="716c5-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="716c5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="716c5-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="716c5-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="716c5-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="716c5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="716c5-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="716c5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
