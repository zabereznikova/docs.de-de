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
ms.openlocfilehash: b3758ac1a84092b8bf2678f9cc2c19c9d9961690
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137324"
---
# <a name="icordebugnativeframecansetip-method"></a><span data-ttu-id="5aa7b-102">ICorDebugNativeFrame::CanSetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="5aa7b-102">ICorDebugNativeFrame::CanSetIP Method</span></span>
<span data-ttu-id="5aa7b-103">Ruft ein HRESULT ab, das angibt, ob es sicher ist, den Anweisungs Zeiger (IP) an die angegebene Offset Position im systemeigenen Code festzulegen.</span><span class="sxs-lookup"><span data-stu-id="5aa7b-103">Gets an HRESULT that indicates whether it is safe to set the instruction pointer (IP) to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5aa7b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5aa7b-104">Syntax</span></span>  
  
```cpp  
HRESULT CanSetIP (  
    [in] ULONG32            nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5aa7b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5aa7b-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="5aa7b-106">in Die gewünschte Einstellung für den Anweisungs Zeiger.</span><span class="sxs-lookup"><span data-stu-id="5aa7b-106">[in] The desired setting for the instruction pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5aa7b-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5aa7b-107">Remarks</span></span>  
 <span data-ttu-id="5aa7b-108">Verwenden Sie die `CanSetIP`-Methode vor dem Aufrufen der [ICorDebugNativeFrame:: settip](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) -Methode.</span><span class="sxs-lookup"><span data-stu-id="5aa7b-108">Use the `CanSetIP` method prior to calling the [ICorDebugNativeFrame::SetIP](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe-setip-method.md) method.</span></span> <span data-ttu-id="5aa7b-109">Wenn `CanSetIP` ein anderes HRESULT als S_OK zurückgibt, können Sie weiterhin `ICorDebugNativeFrame::SetIP`aufrufen, aber es gibt keine Garantie dafür, dass der Debugger die sichere und korrekte Ausführung des debuggten Codes fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="5aa7b-109">If `CanSetIP` returns any HRESULT other than S_OK, you can still invoke `ICorDebugNativeFrame::SetIP`, but there is no guarantee that the debugger will continue the safe and correct execution of the code being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5aa7b-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5aa7b-110">Requirements</span></span>  
 <span data-ttu-id="5aa7b-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5aa7b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5aa7b-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5aa7b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5aa7b-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5aa7b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5aa7b-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5aa7b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5aa7b-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5aa7b-115">See also</span></span>
