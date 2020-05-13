---
title: ICorDebugProcess::IsTransitionStub-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.IsTransitionStub
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::IsTransitionStub
helpviewer_keywords:
- ICorDebugProcess::IsTransitionStub method [.NET Framework debugging]
- IsTransitionStub method [.NET Framework debugging]
ms.assetid: f7653317-7e48-4163-be03-f50f1a4b0f70
topic_type:
- apiref
ms.openlocfilehash: ab2121605f974fdf3f9053214a4d29d8b0dd72db
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210976"
---
# <a name="icordebugprocessistransitionstub-method"></a><span data-ttu-id="b4040-102">ICorDebugProcess::IsTransitionStub-Methode</span><span class="sxs-lookup"><span data-stu-id="b4040-102">ICorDebugProcess::IsTransitionStub Method</span></span>
<span data-ttu-id="b4040-103">Ruft einen Wert ab, der angibt, ob sich eine Adresse in einem Stub befindet, der einen Übergang in verwalteten Code verursacht.</span><span class="sxs-lookup"><span data-stu-id="b4040-103">Gets a value that indicates whether an address is inside a stub that will cause a transition to managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4040-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4040-104">Syntax</span></span>  
  
```cpp  
HRESULT IsTransitionStub(  
    [in]  CORDB_ADDRESS address,  
    [out] BOOL *pbTransitionStub);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4040-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b4040-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="b4040-106">in Ein- `CORDB_ADDRESS` Wert, der die betreffende Adresse angibt.</span><span class="sxs-lookup"><span data-stu-id="b4040-106">[in] A `CORDB_ADDRESS` value that specifies the address in question.</span></span>  
  
 `pbTransitionStub`  
 <span data-ttu-id="b4040-107">vorgenommen Ein Zeiger auf einen booleschen Wert, der ist, `true` Wenn sich die angegebene Adresse in einem Stub befindet, der einen Übergang in verwalteten Code verursacht; andernfalls \* `pbTransitionStub` ist `false` .</span><span class="sxs-lookup"><span data-stu-id="b4040-107">[out] A pointer to a Boolean value that is `true` if the specified address is inside a stub that will cause a transition to managed code; otherwise \*`pbTransitionStub` is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4040-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b4040-108">Remarks</span></span>  
 <span data-ttu-id="b4040-109">Die- `IsTransitionStub` Methode kann von nicht verwaltetem Schritt Code verwendet werden, um zu entscheiden, wann die schrittweise Steuerung an den verwalteten Stepper zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b4040-109">The `IsTransitionStub` method can be used by unmanaged stepping code to decide when to return stepping control to the managed stepper.</span></span>  
  
 <span data-ttu-id="b4040-110">Sie können auch die übergangsstubübereinstisstubweise überprüfen, indem Sie die Informationen in der Datei "Portable</span><span class="sxs-lookup"><span data-stu-id="b4040-110">You can also identity transition stubs by looking at information in the portable executable (PE) file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4040-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b4040-111">Requirements</span></span>  
 <span data-ttu-id="b4040-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4040-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4040-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4040-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4040-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4040-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4040-115">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4040-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
