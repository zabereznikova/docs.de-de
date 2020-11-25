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
ms.openlocfilehash: 55f219b5b834f365b87440e69bfa7d2c4e519235
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696090"
---
# <a name="icordebugfunction2setjmcstatus-method"></a><span data-ttu-id="68eeb-102">ICorDebugFunction2::SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="68eeb-102">ICorDebugFunction2::SetJMCStatus Method</span></span>

<span data-ttu-id="68eeb-103">Markiert die durch dieses ICorDebugFunction2 dargestellte Funktion für nur eigenen Code schrittweise.</span><span class="sxs-lookup"><span data-stu-id="68eeb-103">Marks the function represented by this ICorDebugFunction2 for Just My Code stepping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68eeb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="68eeb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="68eeb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="68eeb-105">Parameters</span></span>  

 `bIsJustMyCode`  
 <span data-ttu-id="68eeb-106">in Legen Sie auf fest, `true` um die Funktion als Benutzercode zu markieren; andernfalls legen Sie auf fest `false` .</span><span class="sxs-lookup"><span data-stu-id="68eeb-106">[in] Set to `true` to mark the function as user code; otherwise, set to `false`.</span></span>  
  
## <a name="return-values"></a><span data-ttu-id="68eeb-107">Rückgabewerte</span><span class="sxs-lookup"><span data-stu-id="68eeb-107">Return Values</span></span>  
  
|<span data-ttu-id="68eeb-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="68eeb-108">HRESULT</span></span>|<span data-ttu-id="68eeb-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="68eeb-109">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="68eeb-110">Die Funktion wurde erfolgreich gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="68eeb-110">The function was successfully marked.</span></span>|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|<span data-ttu-id="68eeb-111">Die Funktion konnte nicht als Benutzercode gekennzeichnet werden, da Sie nicht deentschlbelt werden kann.</span><span class="sxs-lookup"><span data-stu-id="68eeb-111">The function could not be marked as user code because it cannot be debugged.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68eeb-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68eeb-112">Remarks</span></span>  

 <span data-ttu-id="68eeb-113">Ein nur eigenen Code Stepper überspringt Nichtbenutzer Code.</span><span class="sxs-lookup"><span data-stu-id="68eeb-113">A Just My Code stepper will skip non-user code.</span></span> <span data-ttu-id="68eeb-114">Der Benutzercode muss eine Teilmenge des debugfähigen Codes sein.</span><span class="sxs-lookup"><span data-stu-id="68eeb-114">User code must be a subset of debuggable code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68eeb-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="68eeb-115">Requirements</span></span>  

 <span data-ttu-id="68eeb-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="68eeb-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68eeb-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="68eeb-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="68eeb-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="68eeb-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="68eeb-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68eeb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
