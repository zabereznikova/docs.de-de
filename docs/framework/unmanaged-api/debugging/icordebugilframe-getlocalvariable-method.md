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
ms.openlocfilehash: 85f06b49aab1f1d1745bd7e359ed311c2ba1e44d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130984"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="dc5a8-102">ICorDebugILFrame::GetLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="dc5a8-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="dc5a8-103">Ruft den Wert der angegebenen lokalen Variablen in diesem MSIL-Stapel Rahmen (Microsoft Intermediate Language) ab.</span><span class="sxs-lookup"><span data-stu-id="dc5a8-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc5a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc5a8-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc5a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dc5a8-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="dc5a8-106">in Der Index der lokalen Variablen in diesem MSIL-Stapel Rahmen.</span><span class="sxs-lookup"><span data-stu-id="dc5a8-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="dc5a8-107">vorgenommen Ein Zeiger auf die Adresse eines icorentbugvalue-Objekts, das den abgerufenen Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="dc5a8-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dc5a8-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dc5a8-108">Remarks</span></span>  
 <span data-ttu-id="dc5a8-109">Die `GetLocalVariable`-Methode kann entweder in einem MSIL-Stapel Rahmen oder in einem JIT-kompilierten Frame (Just-in-Time) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc5a8-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc5a8-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dc5a8-110">Requirements</span></span>  
 <span data-ttu-id="dc5a8-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc5a8-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc5a8-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dc5a8-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dc5a8-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dc5a8-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dc5a8-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc5a8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
