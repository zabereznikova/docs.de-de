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
ms.openlocfilehash: 29fc1b491aa4e340c3d8ad6f761d0d6d901649ac
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758551"
---
# <a name="icordebugilframegetlocalvariable-method"></a><span data-ttu-id="b6543-102">ICorDebugILFrame::GetLocalVariable-Methode</span><span class="sxs-lookup"><span data-stu-id="b6543-102">ICorDebugILFrame::GetLocalVariable Method</span></span>
<span data-ttu-id="b6543-103">Ruft den Wert der angegebenen lokalen Variable in Microsoft intermediate Language (MSIL) Stapelrahmens ab.</span><span class="sxs-lookup"><span data-stu-id="b6543-103">Gets the value of the specified local variable in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6543-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6543-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLocalVariable (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6543-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b6543-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="b6543-106">[in] Der Index der lokalen Variablen in diesen Stapelrahmen des MSIL.</span><span class="sxs-lookup"><span data-stu-id="b6543-106">[in] The index of the local variable in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="b6543-107">[out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den abgerufenen Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="b6543-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6543-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6543-108">Remarks</span></span>  
 <span data-ttu-id="b6543-109">Die `GetLocalVariable` Methode kann verwendet werden, entweder in einem Stapelrahmen des MSIL oder in einem just-in-Time (JIT) kompilierten Rahmen.</span><span class="sxs-lookup"><span data-stu-id="b6543-109">The `GetLocalVariable` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6543-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b6543-110">Requirements</span></span>  
 <span data-ttu-id="b6543-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6543-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6543-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6543-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6543-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6543-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6543-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6543-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
