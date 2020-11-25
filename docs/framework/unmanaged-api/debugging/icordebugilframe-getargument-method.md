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
ms.openlocfilehash: d17179dbeb9564b16c0c95a43502a53a67d3b9b8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703160"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="1eae9-102">ICorDebugILFrame::GetArgument-Methode</span><span class="sxs-lookup"><span data-stu-id="1eae9-102">ICorDebugILFrame::GetArgument Method</span></span>

<span data-ttu-id="1eae9-103">Ruft den Wert des angegebenen Arguments in diesem MSIL-Stapel Rahmen (Microsoft Intermediate Language) ab.</span><span class="sxs-lookup"><span data-stu-id="1eae9-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eae9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1eae9-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1eae9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1eae9-105">Parameters</span></span>  

 `dwIndex`  
 <span data-ttu-id="1eae9-106">in Der Index des Arguments in diesem MSIL-Stapel Rahmen.</span><span class="sxs-lookup"><span data-stu-id="1eae9-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="1eae9-107">[out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts für den abgerufenen Wert.</span><span class="sxs-lookup"><span data-stu-id="1eae9-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1eae9-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1eae9-108">Remarks</span></span>  

 <span data-ttu-id="1eae9-109">Die- `GetArgument` Methode kann entweder in einem MSIL-Stapel Rahmen oder in einem JIT-kompilierten Frame (Just-in-Time) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1eae9-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1eae9-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="1eae9-110">Requirements</span></span>  

 <span data-ttu-id="1eae9-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1eae9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1eae9-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1eae9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1eae9-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1eae9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1eae9-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1eae9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
