---
title: ICorDebugILFrame::CanSetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::CanSetIP
helpviewer_keywords:
- CanSetIP method, ICorDebugILFrame interface [.NET Framework debugging]
- ICorDebugILFrame::CanSetIP method [.NET Framework debugging]
ms.assetid: 16caf02f-c71e-486c-90b0-f0e54357d8f0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49cef22e88613fe4c4dfb3fb35a92977977b1827
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61988636"
---
# <a name="icordebugilframecansetip-method"></a><span data-ttu-id="81045-102">ICorDebugILFrame::CanSetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="81045-102">ICorDebugILFrame::CanSetIP Method</span></span>
<span data-ttu-id="81045-103">Ruft ein HRESULT, der angibt, ob den Anweisungszeiger auf der angegebenen Offsetposition im Microsoft Intermediate Language (MSIL)-Code festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="81045-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer to the specified offset location in Microsoft Intermediate Language (MSIL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81045-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="81045-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32   nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81045-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="81045-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="81045-106">[in] Die gewünschte Einstellung für den Anweisungszeiger.</span><span class="sxs-lookup"><span data-stu-id="81045-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81045-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81045-107">Remarks</span></span>  
 <span data-ttu-id="81045-108">Verwenden der `CanSetIP` Methode vor dem Aufruf der [ICorDebugILFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="81045-108">Use the `CanSetIP` method before calling the [ICorDebugILFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md) method.</span></span> <span data-ttu-id="81045-109">Wenn `CanSetIP` gibt ein HRESULT S_OK, können Sie weiterhin aufrufen `ICorDebugILFrame::SetIP`, aber es gibt keine Garantie, dass der Debugger die ordnungsgemäße und sichere Ausführung des debuggten Codes weiterhin.</span><span class="sxs-lookup"><span data-stu-id="81045-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugILFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81045-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="81045-110">Requirements</span></span>  
 <span data-ttu-id="81045-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81045-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81045-112">**Header:** CorDebug.idl, CorDebug,h</span><span class="sxs-lookup"><span data-stu-id="81045-112">**Header:** CorDebug.idl, CorDebug,h</span></span>  
  
 <span data-ttu-id="81045-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81045-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81045-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81045-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
