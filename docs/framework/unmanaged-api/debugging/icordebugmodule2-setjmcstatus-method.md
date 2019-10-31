---
title: ICorDebugModule2::SetJMCStatus-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
ms.openlocfilehash: a0b70078dee88b270d8361aa9bddcb7d80df1db1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129469"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="72659-102">ICorDebugModule2::SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="72659-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="72659-103">Legt den nur eigenen Code (JMC)-Status aller Methoden aller Klassen in diesem ICorDebugModule2 auf den angegebenen Wert fest, mit Ausnahme derjenigen im `pTokens` Array, die auf den umgekehrten Wert festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="72659-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72659-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="72659-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72659-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="72659-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="72659-106">in Auf `true` festgelegt, wenn der Code deentschlgt werden soll. Legen Sie andernfalls auf `false`fest.</span><span class="sxs-lookup"><span data-stu-id="72659-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="72659-107">[in] Die Größe des `pTokens`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="72659-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="72659-108">in Ein Array von `mdToken`-Werten, von denen jede auf eine Methode verweist, deren JMC-Status auf festgelegt wird.`bIsJustMycode`.</span><span class="sxs-lookup"><span data-stu-id="72659-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="72659-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="72659-109">Remarks</span></span>  
 <span data-ttu-id="72659-110">Der JMC-Status jeder Methode, die im `pTokens` Array angegeben ist, wird auf das Gegenteil des `bIsJustMycode` Werts festgelegt.</span><span class="sxs-lookup"><span data-stu-id="72659-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="72659-111">Der Status aller anderen Methoden in diesem Modul ist auf den `bIsJustMycode` Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="72659-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="72659-112">Die `SetJMCStatus`-Methode löscht alle vorherigen JMC-Einstellungen in diesem Modul.</span><span class="sxs-lookup"><span data-stu-id="72659-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="72659-113">Die `SetJMCStatus`-Methode gibt ein S_OK HRESULT zurück, wenn alle Funktionen erfolgreich festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="72659-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="72659-114">Es wird ein CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT zurückgegeben, wenn einige Funktionen, die als `true` gekennzeichnet sind, nicht debuggt werden können.</span><span class="sxs-lookup"><span data-stu-id="72659-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72659-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="72659-115">Requirements</span></span>  
 <span data-ttu-id="72659-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="72659-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72659-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="72659-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="72659-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="72659-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="72659-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72659-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
