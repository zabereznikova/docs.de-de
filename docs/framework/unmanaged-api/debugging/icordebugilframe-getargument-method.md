---
title: ICorDebugILFrame::GetArgument-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46852ed8ac53c3a7720edff4833f3dc3cce42bbb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475787"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="16352-102">ICorDebugILFrame::GetArgument-Methode</span><span class="sxs-lookup"><span data-stu-id="16352-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="16352-103">Ruft den Wert des angegebenen Arguments in Microsoft intermediate Language (MSIL) Stapelrahmens ab.</span><span class="sxs-lookup"><span data-stu-id="16352-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16352-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="16352-104">Syntax</span></span>  
  
```  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="16352-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="16352-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="16352-106">[in] Der Index des Arguments in den MSIL-Stapelrahmens.</span><span class="sxs-lookup"><span data-stu-id="16352-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="16352-107">[out] Ein Zeiger auf die Adresse eines ICorDebugValue-Objekts, das den abgerufenen Wert darstellt.</span><span class="sxs-lookup"><span data-stu-id="16352-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16352-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16352-108">Remarks</span></span>  
 <span data-ttu-id="16352-109">Die `GetArgument` Methode kann verwendet werden, entweder in einem Stapelrahmen des MSIL oder in einem just-in-Time (JIT) kompilierten Rahmen.</span><span class="sxs-lookup"><span data-stu-id="16352-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16352-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="16352-110">Requirements</span></span>  
 <span data-ttu-id="16352-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16352-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16352-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="16352-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="16352-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="16352-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="16352-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16352-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
