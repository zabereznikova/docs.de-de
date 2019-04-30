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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d20c640d6a6a43b7bde4c7d46df470c7bc8c5aa2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942507"
---
# <a name="icordebugmodule2setjmcstatus-method"></a><span data-ttu-id="b80a7-102">ICorDebugModule2::SetJMCStatus-Methode</span><span class="sxs-lookup"><span data-stu-id="b80a7-102">ICorDebugModule2::SetJMCStatus Method</span></span>
<span data-ttu-id="b80a7-103">Legt den Zustand nur mein Code (JMC) alle Methoden von der alle Klassen, die in dieses ICorDebugModule2 auf den angegebenen Wert, mit Ausnahme derjenigen in der `pTokens` Array, das auf den entgegengesetzten Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b80a7-103">Sets the Just My Code (JMC) status of all methods of all the classes in this ICorDebugModule2 to the specified value, except those in the `pTokens` array, which it sets to the opposite value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b80a7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b80a7-104">Syntax</span></span>  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b80a7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b80a7-105">Parameters</span></span>  
 `bIsJustMycode`  
 <span data-ttu-id="b80a7-106">[in] Legen Sie auf `true` , wenn der Code ist, werden andernfalls debuggten, legen Sie auf `false`.</span><span class="sxs-lookup"><span data-stu-id="b80a7-106">[in] Set to `true` if the code is to be debugged; otherwise, set to `false`.</span></span>  
  
 `cTokens`  
 <span data-ttu-id="b80a7-107">[in] Die Größe des `pTokens`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="b80a7-107">[in] The size of the `pTokens` array.</span></span>  
  
 `pTokens`  
 <span data-ttu-id="b80a7-108">[in] Ein Array von `mdToken` Werte, von denen jede bezieht sich auf eine Methode, die den JMC Status hat!`bIsJustMycode`.</span><span class="sxs-lookup"><span data-stu-id="b80a7-108">[in] An array of `mdToken` values, each of which refers to a method that will have its JMC status set to !`bIsJustMycode`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b80a7-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b80a7-109">Remarks</span></span>  
 <span data-ttu-id="b80a7-110">Die JMC Status jeder einzelnen Methode, die im angegebenen die `pTokens` Array festgelegt ist, auf das Gegenteil von der `bIsJustMycode` Wert.</span><span class="sxs-lookup"><span data-stu-id="b80a7-110">The JMC status of each method that is specified in the `pTokens` array is set to the opposite of the `bIsJustMycode` value.</span></span> <span data-ttu-id="b80a7-111">Der Status aller anderen Methoden in diesem Modul wird festgelegt, um die `bIsJustMycode` Wert.</span><span class="sxs-lookup"><span data-stu-id="b80a7-111">The status of all other methods in this module is set to the `bIsJustMycode` value.</span></span>  
  
 <span data-ttu-id="b80a7-112">Die `SetJMCStatus` Methode löscht alle vorherige JMC-Einstellungen in diesem Modul.</span><span class="sxs-lookup"><span data-stu-id="b80a7-112">The `SetJMCStatus` method erases all previous JMC settings in this module.</span></span>  
  
 <span data-ttu-id="b80a7-113">Die `SetJMCStatus` Methode gibt ein S_OK HRESULT zurück, wenn alle Funktionen erfolgreich festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="b80a7-113">The `SetJMCStatus` method returns an S_OK HRESULT if all functions were set successfully.</span></span> <span data-ttu-id="b80a7-114">Gibt ein HRESULT CORDBG_E_FUNCTION_NOT_DEBUGGABLE, wenn einige Funktionen, die markiert sind `true` nicht debuggt werden.</span><span class="sxs-lookup"><span data-stu-id="b80a7-114">It returns a CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT if some functions that are marked `true` are not debuggable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b80a7-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b80a7-115">Requirements</span></span>  
 <span data-ttu-id="b80a7-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b80a7-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b80a7-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b80a7-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b80a7-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b80a7-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b80a7-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b80a7-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
