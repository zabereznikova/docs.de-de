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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3424646337c3f90f15d991f3f669a296bf11d8ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413006"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="b2691-102">ICorDebugILFrame::GetLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="b2691-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="b2691-103">Ruft den Wert der angegebenen lokalen Variablen in Microsoft intermediate Language (MSIL)-Stapelrahmen ab.</span><span class="sxs-lookup"><span data-stu-id="b2691-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2691-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2691-104">Syntax</span></span>  
  
```  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2691-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b2691-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="b2691-106">[in] Der Index der lokalen Variablen im Stapelrahmen MSIL.</span><span class="sxs-lookup"><span data-stu-id="b2691-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b2691-107">[out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den abgerufenen Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="b2691-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2691-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b2691-108">Remarks</span></span>  
 <span data-ttu-id="b2691-109">Die `GetLocalVariable` Methode kann verwendet werden, in einem Stapelrahmen des MSIL oder in einem Just-in-Time (JIT) kompilierten Frame.</span><span class="sxs-lookup"><span data-stu-id="b2691-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2691-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b2691-110">Requirements</span></span>  
 <span data-ttu-id="b2691-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2691-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2691-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b2691-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b2691-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b2691-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b2691-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2691-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
