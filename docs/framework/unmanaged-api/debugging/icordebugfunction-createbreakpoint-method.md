---
title: ICorDebugFunction::CreateBreakpoint-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::CreateBreakpoint
helpviewer_keywords:
- ICorDebugFunction::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: ffd0f708-0d21-4fae-a395-63b6c45828fa
topic_type:
- apiref
ms.openlocfilehash: 64304b671532325bdc2f8841a2702d537d143330
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124039"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="d45a9-102">ICorDebugFunction::CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="d45a9-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="d45a9-103">Erstellt am Anfang dieser Funktion einen Haltepunkt.</span><span class="sxs-lookup"><span data-stu-id="d45a9-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d45a9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d45a9-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d45a9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d45a9-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="d45a9-106">vorgenommen Ein Zeiger auf die Adresse eines icorentbugfunctionbreakpoint-Objekts, das den neuen Breakpoint für die Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="d45a9-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d45a9-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d45a9-107">Requirements</span></span>  
 <span data-ttu-id="d45a9-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d45a9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d45a9-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d45a9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d45a9-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d45a9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d45a9-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d45a9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
