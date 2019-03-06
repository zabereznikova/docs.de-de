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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ed6570e11008e52d4b1f97c2dc90e2ccbef2e35
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471380"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="11d31-102">ICorDebugClass2::SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="11d31-102">ICorDebugClass2::SetJMCStatus Method</span></span>
<span data-ttu-id="11d31-103">Für jede Methode der Klasse wird einen Wert, der angibt, ob die Methode benutzerdefinierten Code ist.</span><span class="sxs-lookup"><span data-stu-id="11d31-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11d31-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="11d31-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11d31-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="11d31-105">Parameters</span></span>  
 `bIsJustMyCode`  
 <span data-ttu-id="11d31-106">[in] Legen Sie auf `true` , um anzugeben, dass die Methode den benutzerdefinierten code, legen Sie andernfalls auf `false`.</span><span class="sxs-lookup"><span data-stu-id="11d31-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11d31-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="11d31-107">Remarks</span></span>  
 <span data-ttu-id="11d31-108">Eine nur mein Code (JMC) zugeordnetem wird nicht auf eine benutzerdefinierte Code überspringen.</span><span class="sxs-lookup"><span data-stu-id="11d31-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="11d31-109">Benutzerdefinierter Code muss es sich um eine Teilmenge der debugfähiger Code sein.</span><span class="sxs-lookup"><span data-stu-id="11d31-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="11d31-110">`SetJMCStatus` Gibt einen HRESULT-Wert, der S_FALSE zurück, wenn sie zum Festlegen des Werts für eine beliebige Methode, schlägt fehl, selbst wenn der Wert für alle anderen Methoden erfolgreich festgelegt.</span><span class="sxs-lookup"><span data-stu-id="11d31-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11d31-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="11d31-111">Requirements</span></span>  
 <span data-ttu-id="11d31-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11d31-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11d31-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11d31-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11d31-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11d31-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11d31-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11d31-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
