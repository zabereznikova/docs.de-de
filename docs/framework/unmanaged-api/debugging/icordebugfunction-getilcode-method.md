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
ms.openlocfilehash: b7d3fbafaab6d43fa89d45855628dbd6b9ab81e2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95696218"
---
# <a name="icordebugfunctiongetilcode-method"></a><span data-ttu-id="83d9f-102">ICorDebugFunction::GetILCode-Methode</span><span class="sxs-lookup"><span data-stu-id="83d9f-102">ICorDebugFunction::GetILCode Method</span></span>

<span data-ttu-id="83d9f-103">Ruft die ICorDebugCode-Instanz ab, die den MSIL-Code (Microsoft Intermediate Language) darstellt, der mit diesem ICorDebugFunction-Objekt verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="83d9f-103">Gets the ICorDebugCode instance that represents the Microsoft intermediate language (MSIL) code associated with this ICorDebugFunction object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83d9f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="83d9f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetILCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="83d9f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="83d9f-105">Parameters</span></span>  

 `ppCode`  
 <span data-ttu-id="83d9f-106">vorgenommen Ein Zeiger auf die- `ICorDebugCode` Instanz oder NULL, wenn die Funktion nicht in MSIL kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="83d9f-106">[out] A pointer to the `ICorDebugCode` instance, or null, if the function was not compiled into MSIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="83d9f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="83d9f-107">Remarks</span></span>  

 <span data-ttu-id="83d9f-108">Wenn "Bearbeiten und Fortfahren" für diese Funktion zulässig ist, erhält die `GetILCode` Methode den MSIL-Code, der der bearbeiteten Version des Codes der Funktion in der Common Language Runtime (CLR) entspricht.</span><span class="sxs-lookup"><span data-stu-id="83d9f-108">If Edit and Continue has been allowed on this function, the `GetILCode` method will get the MSIL code corresponding to this function's edited version of the code in the common language runtime (CLR).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83d9f-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="83d9f-109">Requirements</span></span>  

 <span data-ttu-id="83d9f-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83d9f-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83d9f-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="83d9f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="83d9f-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83d9f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83d9f-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83d9f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
