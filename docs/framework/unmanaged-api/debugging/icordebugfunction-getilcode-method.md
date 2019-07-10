---
title: ICorDebugFunction::GetILCode-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetILCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetILCode
helpviewer_keywords:
- ICorDebugFunction::GetILCode method [.NET Framework debugging]
- GetILCode method [.NET Framework debugging]
ms.assetid: f794dd47-a7cd-47f6-96e9-a41a4dae8e72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e32ce10b708afa5741d83cbd05f14accb4b2014f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754680"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="90496-102">ICorDebugFunction::GetILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="90496-102">ICorDebugFunction::GetILCode Method</span></span>
<span data-ttu-id="90496-103">Ruft die ICorDebugCode-Instanz, die diesem ICorDebugFunction-Objekt zugeordneten Codes Microsoft intermediate Language (MSIL) darstellt.</span><span class="sxs-lookup"><span data-stu-id="90496-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90496-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90496-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90496-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="90496-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="90496-106">[out] Ein Zeiger auf die `ICorDebugCode` -Instanz oder null, wenn die Funktion nicht in MSIL kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="90496-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90496-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90496-107">Remarks</span></span>  
 <span data-ttu-id="90496-108">Wenn Bearbeiten und Fortfahren wurde zugelassen. auf diese Funktion, die `GetILCode` Methode den MSIL-Code für diese Funktion die bearbeitete Version des Codes in der common Language Runtime (CLR) erhalten.</span><span class="sxs-lookup"><span data-stu-id="90496-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90496-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90496-109">Requirements</span></span>  
 <span data-ttu-id="90496-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90496-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90496-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90496-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90496-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90496-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90496-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90496-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
