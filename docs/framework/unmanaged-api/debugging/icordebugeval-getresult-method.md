---
title: ICorDebugEval::GetResult-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
ms.openlocfilehash: 2d065d956319076d3b92eddafd4a2c25ffbfbac1
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976264"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="43f01-102">ICorDebugEval::GetResult-Methode</span><span class="sxs-lookup"><span data-stu-id="43f01-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="43f01-103">Ruft die Ergebnisse dieser Auswertung ab.</span><span class="sxs-lookup"><span data-stu-id="43f01-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43f01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="43f01-104">Syntax</span></span>  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43f01-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="43f01-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="43f01-106">vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das die Ergebnisse dieser Auswertung darstellt, wenn die Auswertung normal abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="43f01-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43f01-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="43f01-107">Remarks</span></span>  
 <span data-ttu-id="43f01-108">Die `GetResult` -Methode ist nur gültig, wenn die Auswertung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="43f01-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="43f01-109">Wenn die Auswertung normal abgeschlossen wird `ppResult` , gibt die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="43f01-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="43f01-110">Wenn Sie mit einer Ausnahme beendet wird, ist das Ergebnis die ausgelöste Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="43f01-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="43f01-111">Wenn die Auswertung für ein neues Objekt erfolgte, ist das Ergebnis der Verweis auf das neue-Objekt.</span><span class="sxs-lookup"><span data-stu-id="43f01-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43f01-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="43f01-112">Requirements</span></span>  
 <span data-ttu-id="43f01-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43f01-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43f01-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43f01-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43f01-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43f01-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43f01-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43f01-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
