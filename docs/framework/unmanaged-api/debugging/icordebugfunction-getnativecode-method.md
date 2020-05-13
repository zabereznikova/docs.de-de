---
title: ICorDebugFunction::GetNativeCode-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
ms.openlocfilehash: 98aee38415709974d84873df50c39263490f2f23
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213269"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="8291d-102">ICorDebugFunction::GetNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="8291d-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="8291d-103">Ruft den systemeigenen Code für die Funktion ab, die von dieser ICorDebugFunction-Instanz dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="8291d-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8291d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8291d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8291d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8291d-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="8291d-106">vorgenommen Ein Zeiger auf die ICorDebugCode-Instanz, die den nativen Code für diese Funktion darstellt, oder NULL, wenn es sich bei dieser Funktion um MSIL-Code (Microsoft Intermediate Language) handelt, der nicht Just-in-time (JIT) kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="8291d-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8291d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8291d-107">Remarks</span></span>  
 <span data-ttu-id="8291d-108">Wenn die Funktion, die durch diese Instanz dargestellt wird `ICorDebugFunction` , mehr als einmal JIT-kompiliert wurde (wie bei generischen Typen), wird `GetNativeCode` ein zufälliges System eigenes Code Objekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8291d-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8291d-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8291d-109">Requirements</span></span>  
 <span data-ttu-id="8291d-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8291d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8291d-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8291d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8291d-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8291d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8291d-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8291d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
