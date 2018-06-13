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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e160eddf667b542929c8dd3790de666a8e8bb77
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413058"
---
# <a name="icordebugevalgetresult-method"></a><span data-ttu-id="ec251-102">ICorDebugEval::GetResult-Methode</span><span class="sxs-lookup"><span data-stu-id="ec251-102">ICorDebugEval::GetResult Method</span></span>
<span data-ttu-id="ec251-103">Ruft den Ergebnissen dieser Auswertung ab.</span><span class="sxs-lookup"><span data-stu-id="ec251-103">Gets the results of this evaluation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec251-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ec251-104">Syntax</span></span>  
  
```  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec251-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ec251-105">Parameters</span></span>  
 `ppResult`  
 <span data-ttu-id="ec251-106">[out] Zeiger auf die Adresse eines ICorDebugValue-Objekts, das die Ergebnissen dieser Auswertung darstellt, wenn die Auswertung normal abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="ec251-106">[out] Pointer to the address of an ICorDebugValue object that represents the results of this evaluation, if the evaluation completes normally.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec251-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ec251-107">Remarks</span></span>  
 <span data-ttu-id="ec251-108">Die `GetResult` Methode gilt nur, nachdem die Auswertung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="ec251-108">The `GetResult` method is valid only after the evaluation is completed.</span></span>  
  
 <span data-ttu-id="ec251-109">Wenn in der Regel wird die Auswertung abgeschlossen `ppResult` gibt die Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="ec251-109">If the evaluation completes normally, `ppResult` specifies the results.</span></span> <span data-ttu-id="ec251-110">Wenn sie mit einer Ausnahme beendet wird, ist das Ergebnis die ausgelöste Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="ec251-110">If it terminates with an exception, the result is the exception thrown.</span></span> <span data-ttu-id="ec251-111">Wenn die Auswertung für ein neues Objekt war, ist das Ergebnis der Verweis auf das neue Objekt.</span><span class="sxs-lookup"><span data-stu-id="ec251-111">If the evaluation was for a new object, the result is the reference to the new object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec251-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ec251-112">Requirements</span></span>  
 <span data-ttu-id="ec251-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec251-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec251-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec251-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec251-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec251-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec251-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec251-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
