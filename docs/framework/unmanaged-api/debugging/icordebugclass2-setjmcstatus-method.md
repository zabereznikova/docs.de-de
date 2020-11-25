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
ms.openlocfilehash: 1db2c9b5e65ae150f05242172f5ea16db433bbb5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717824"
---
# <a name="icordebugclass2setjmcstatus-method"></a><span data-ttu-id="b2989-102">ICorDebugClass2::SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="b2989-102">ICorDebugClass2::SetJMCStatus Method</span></span>

<span data-ttu-id="b2989-103">Legt für jede Methode der Klasse einen Wert fest, der angibt, ob es sich bei der Methode um benutzerdefinierten Code handelt.</span><span class="sxs-lookup"><span data-stu-id="b2989-103">For each method of the class, sets a value that indicates whether the method is user-defined code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2989-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2989-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b2989-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b2989-105">Parameters</span></span>  

 `bIsJustMyCode`  
 <span data-ttu-id="b2989-106">in Legen Sie auf fest, `true` um anzugeben, dass es sich bei der Methode um benutzerdefinierten Code handelt, andernfalls auf `false` .</span><span class="sxs-lookup"><span data-stu-id="b2989-106">[in] Set to `true` to indicate that the method is user-defined code; otherwise, set to `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2989-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b2989-107">Remarks</span></span>  

 <span data-ttu-id="b2989-108">Ein JMC-Stepper (Just-my-Code) überspringt Nichtbenutzer definierten Code.</span><span class="sxs-lookup"><span data-stu-id="b2989-108">A just-my-code (JMC) stepper will skip non-user-defined code.</span></span> <span data-ttu-id="b2989-109">Der benutzerdefinierte Code muss eine Teilmenge des debugfähigen Codes sein.</span><span class="sxs-lookup"><span data-stu-id="b2989-109">User-defined code must be a subset of debuggable code.</span></span>  
  
 <span data-ttu-id="b2989-110">`SetJMCStatus` Gibt einen HRESULT-Wert von S_FALSE zurück, wenn der Wert für keine Methode festgelegt werden kann, auch wenn der Wert für alle anderen Methoden erfolgreich festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="b2989-110">`SetJMCStatus` returns an HRESULT value of S_FALSE if it fails to set the value for any method, even if it successfully sets the value for all other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2989-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b2989-111">Requirements</span></span>  

 <span data-ttu-id="b2989-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2989-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2989-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2989-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2989-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2989-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2989-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2989-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
