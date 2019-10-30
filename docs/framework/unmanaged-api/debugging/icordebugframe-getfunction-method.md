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
ms.openlocfilehash: 39175e338e4fd98dd4af1325138da732ed81c764
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137919"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="b5754-102">ICorDebugFrame::GetFunction-Methode</span><span class="sxs-lookup"><span data-stu-id="b5754-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="b5754-103">Ruft die Funktion ab, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b5754-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5754-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b5754-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5754-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b5754-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="b5754-106">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugFunction-Objekts, das die Funktion darstellt, die den Code enthält, der diesem Stapel Rahmen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b5754-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b5754-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b5754-107">Remarks</span></span>  
 <span data-ttu-id="b5754-108">Bei der `GetFunction`-Methode tritt möglicherweise ein Fehler auf, wenn der Frame keiner bestimmten Funktion zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b5754-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5754-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b5754-109">Requirements</span></span>  
 <span data-ttu-id="b5754-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5754-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5754-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5754-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5754-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5754-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5754-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5754-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
