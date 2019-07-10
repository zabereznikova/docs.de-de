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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6eb93b84baf9dcd82d89bb1a4711a91d97c52779
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754787"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="5b04a-102">ICorDebugFunction::CreateBreakpoint-Methode</span><span class="sxs-lookup"><span data-stu-id="5b04a-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="5b04a-103">Erstellt einen Haltepunkt am Anfang dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="5b04a-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b04a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b04a-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b04a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5b04a-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="5b04a-106">[out] Ein Zeiger auf die Adresse des ICorDebugFunctionBreakpoint-Objekts, das den neuen Haltepunkt für die Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="5b04a-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b04a-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5b04a-107">Requirements</span></span>  
 <span data-ttu-id="5b04a-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b04a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b04a-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b04a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b04a-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b04a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b04a-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b04a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
