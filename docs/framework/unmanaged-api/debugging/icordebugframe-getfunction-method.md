---
title: ICorDebugFrame::GetFunction-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
ms.openlocfilehash: 7bf73266f0269cfcd5371c5155856800036cc066
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209837"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="7bb51-102">ICorDebugFrame::GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="7bb51-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="7bb51-103">Ruft die Funktion ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7bb51-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bb51-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7bb51-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7bb51-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7bb51-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="7bb51-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugFunction-Objekts, das die Funktion darstellt, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7bb51-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bb51-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7bb51-107">Remarks</span></span>  
 <span data-ttu-id="7bb51-108">Die `GetFunction` Methode schlägt möglicherweise fehl, wenn der Frame keiner bestimmten Funktion zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7bb51-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7bb51-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7bb51-109">Requirements</span></span>  
 <span data-ttu-id="7bb51-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7bb51-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7bb51-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7bb51-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7bb51-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7bb51-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7bb51-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7bb51-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
