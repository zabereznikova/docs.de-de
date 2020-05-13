---
title: ICorDebugILFrame::GetLocalVariable-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetLocalVariable
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetLocalVariable
helpviewer_keywords:
- ICorDebugILFrame::GetLocalVariable method [.NET Framework debugging]
- GetLocalVariable method [.NET Framework debugging]
ms.assetid: c8706356-d50b-4f87-a40c-39c3b7f4fd38
topic_type:
- apiref
ms.openlocfilehash: d6ce5a5cc64a5eb805faa5bb17a42a662940affe
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210253"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="0f38b-102">ICorDebugILFrame::GetLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="0f38b-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="0f38b-103">Ruft den Wert der angegebenen lokalen Variablen in diesem MSIL-Stapel Rahmen (Microsoft Intermediate Language) ab.</span><span class="sxs-lookup"><span data-stu-id="0f38b-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f38b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f38b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0f38b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0f38b-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="0f38b-106">in Der Index der lokalen Variablen in diesem MSIL-Stapel Rahmen.</span><span class="sxs-lookup"><span data-stu-id="0f38b-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="0f38b-107">[out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts für den abgerufenen Wert.</span><span class="sxs-lookup"><span data-stu-id="0f38b-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f38b-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f38b-108">Remarks</span></span>  
 <span data-ttu-id="0f38b-109">Die- `GetLocalVariable` Methode kann entweder in einem MSIL-Stapel Rahmen oder in einem JIT-kompilierten Frame (Just-in-Time) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0f38b-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f38b-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0f38b-110">Requirements</span></span>  
 <span data-ttu-id="0f38b-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f38b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f38b-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0f38b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0f38b-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f38b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f38b-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f38b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
