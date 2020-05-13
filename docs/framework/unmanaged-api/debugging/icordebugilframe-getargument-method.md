---
title: ICorDebugILFrame::GetArgument-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
ms.openlocfilehash: d715f5842bb7f75da5311d34bf7d4596f0801a92
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210279"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="7a57d-102">ICorDebugILFrame::GetArgument-Methode</span><span class="sxs-lookup"><span data-stu-id="7a57d-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="7a57d-103">Ruft den Wert des angegebenen Arguments in diesem MSIL-Stapel Rahmen (Microsoft Intermediate Language) ab.</span><span class="sxs-lookup"><span data-stu-id="7a57d-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a57d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7a57d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a57d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7a57d-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="7a57d-106">in Der Index des Arguments in diesem MSIL-Stapel Rahmen.</span><span class="sxs-lookup"><span data-stu-id="7a57d-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="7a57d-107">[out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts für den abgerufenen Wert.</span><span class="sxs-lookup"><span data-stu-id="7a57d-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7a57d-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7a57d-108">Remarks</span></span>  
 <span data-ttu-id="7a57d-109">Die- `GetArgument` Methode kann entweder in einem MSIL-Stapel Rahmen oder in einem JIT-kompilierten Frame (Just-in-Time) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7a57d-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7a57d-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7a57d-110">Requirements</span></span>  
 <span data-ttu-id="7a57d-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a57d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a57d-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7a57d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7a57d-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7a57d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7a57d-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a57d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
