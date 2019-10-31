---
title: ICorDebugClass2::SetJMCStatus-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugClass2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2::SetJMCStatus
helpviewer_keywords:
- ICorDebugClass2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 077e6c7f-f857-480c-bebb-76ee1de4e8fc
topic_type:
- apiref
ms.openlocfilehash: a862dd3f6a9c10c6b3a5a0bb41208d351c4ca9f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125691"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="df1e6-102">ICorDebugClass2::SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="df1e6-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="df1e6-103">Legt für jede Methode der Klasse einen Wert fest, der angibt, ob es sich bei der Methode um benutzerdefinierten Code handelt.</span><span class="sxs-lookup"><span data-stu-id="df1e6-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df1e6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="df1e6-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df1e6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="df1e6-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="df1e6-106">in Auf `true` festgelegt, um anzugeben, dass es sich bei der Methode um benutzerdefinierten Code handelt. Legen Sie andernfalls auf `false`fest.</span><span class="sxs-lookup"><span data-stu-id="df1e6-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df1e6-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="df1e6-107">Remarks</span></span>  
 <span data-ttu-id="df1e6-108">Ein JMC-Stepper (Just-my-Code) überspringt Nichtbenutzer definierten Code.</span><span class="sxs-lookup"><span data-stu-id="df1e6-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="df1e6-109">Der benutzerdefinierte Code muss eine Teilmenge des debugfähigen Codes sein.</span><span class="sxs-lookup"><span data-stu-id="df1e6-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="df1e6-110">`SetJMCStatus` gibt einen HRESULT-Wert von S_FALSE zurück, wenn der Wert für keine Methode festgelegt werden kann, auch wenn der Wert für alle anderen Methoden erfolgreich festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="df1e6-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df1e6-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="df1e6-111">Requirements</span></span>  
 <span data-ttu-id="df1e6-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df1e6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df1e6-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="df1e6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="df1e6-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="df1e6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="df1e6-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df1e6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
