---
title: ICorDebugNativeFrame::CanSetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.CanSetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::CanSetIP
helpviewer_keywords:
- ICorDebugNativeFrame::CanSetIP method [.NET Framework debugging]
- CanSetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 13258ac6-f4e4-4f66-8fc3-f1244417a3c3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 93a8c8650822c5d986e21a456d58b2dc0327f05b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479519"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="0e7db-102">ICorDebugNativeFrame::CanSetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="0e7db-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="0e7db-103">Ruft ein HRESULT, der angibt, ob den Anweisungszeiger (IP) auf die angegebenen Offsetposition im nativen Code festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0e7db-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e7db-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e7db-104">Syntax</span></span>  
  
```  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e7db-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0e7db-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="0e7db-106">[in] Die gewünschte Einstellung für den Anweisungszeiger.</span><span class="sxs-lookup"><span data-stu-id="0e7db-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e7db-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0e7db-107">Remarks</span></span>  
 <span data-ttu-id="0e7db-108">Verwenden der `CanSetIP` aufrufen, bevor die [ICorDebugNativeFrame:: SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="0e7db-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="0e7db-109">Wenn `CanSetIP` gibt ein HRESULT S_OK, können Sie weiterhin aufrufen `ICorDebugNativeFrame::SetIP`, aber es gibt keine Garantie, dass der Debugger die ordnungsgemäße und sichere Ausführung des debuggten Codes weiterhin.</span><span class="sxs-lookup"><span data-stu-id="0e7db-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e7db-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0e7db-110">Requirements</span></span>  
 <span data-ttu-id="0e7db-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e7db-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e7db-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0e7db-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0e7db-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e7db-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e7db-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e7db-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e7db-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0e7db-115">See also</span></span>

